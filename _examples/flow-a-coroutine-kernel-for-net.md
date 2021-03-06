---
layout: article
title: "Flow - A Coroutine Kernel For .Net"
author: Christian Schladetsch
source: http://www.gamasutra.com/view/news/177397/Indepth_Flow__A_coroutine_kernel_for_Net.php
category: Programming
---

# Introduction
This post will present a small library called __Flow__ that abuses .Net's IEnumerable functionality, providing a Kernel for cooperative multitasking based on the concept of [coroutines](http://en.wikipedia.org/wiki/Coroutine).

The concepts of Timer, Future\<T\>, Channel\<T\>, Barrier and Trigger, are introduced as well as process Nodes and Groups.

All these ideas are wrapped within the context of a real-time cooperative Kernel.

Coroutines here are first-class objects that can be passed as arguments and returned as results.

No [Singletons](http://en.wikipedia.org/wiki/Singleton_pattern) were harmed, or used, in the creation of this library.

The library is tiny at 30k, and builds when targeting .Net 2.0.

Complete [source code and test suites](http://github.com/cschladetsch/Flow) are available on Github. The code is free to modify and use for any purpose, commercial or otherwise. It is released under the [Boost License](http://www.boost.org/users/license.html).

Please send any bugs or feature requests to the [author](http://www.gamasutra.com/view/news/177397/Indepth_Flow__A_coroutine_kernel_for_Net.phpmailto:christian.schladetsch@gmail.com?subject=Flow-Request).

# Motivational example
To get started, let's have a look at some code that uses the Flow library.

See also the test [source code](https://github.com/cschladetsch/Flow/blob/master/TestFlow/TestChannel.cs) for this example:

~~~ csharp
public IEnumerator Consumer(IGenerator self, IChannel<int> channel) {
    while (true) {
        IFuture<int> next = channel.Extract();
        // get a future value from the channel

        yield return self.ResumeAfter(next);
        // wait for the future to exist, or fail

        if (!next.Available) {
            yield break;
            // there was no value, Complete
        }

        Sum += next.Value;
        // consume it and continue
    }
}
~~~

Here we have the classic consumer/producer flow. We will get to the details later, but for now let's get acquainted with the look and feel. Note that IGenerator, IChannel\<T\> and IFuture\<T\> are all in namespace Flow.

The consumer is the Coroutine passed as the first argument, and the producer is modelled as a Channel of integers passed as the second argument. The consumer repeatedly extracts the next element from the Channel until the Channel is Completed.

This is done by using the `yield` command. Line 6: "`yield return self.ResumeAfter(next)`" is to be read as "wait here until we get a value, or the channel is deleted".

After flow returns to the Coroutine, we test to see if the Future has been set by testing its Available property. If the Future is not Available, the flow is halted and the Coroutine is Completed by the `yield break` statement.

Otherwise, we consume the new value by summing it with all previous values, then the flow continues.

If this seems very strange, don't worry, there's a lot of new concepts introduced here. We will be discussing these concepts in depth in the following sections, but first we will talk a little about the overall structure of the library and the core ideas.

# Architecture
Before we delve into the implementation, we will take a birds-eye view of the library and how it is organised. It is quite straight-forward.

All of the publicly visible elements of the library are exposed as interfaces. The implementations are internal to the library. This decouples the client code from the implementation, and will make future changes easier to roll out. More importantly however, the use of interfaces allows us to designate a precise level of constraint for objects as they are passed around the system and as process flows merge and diverge.

# Core concepts
At its heart, the system is based on the core idea of a [Transient](http://github.com/cschladetsch/Flow/blob/master/Interface/ITransient.cs) object. A Transient object is Active as soon as it is created, and remains so until it is Completed. When we Complete a Transient object, the object will fire its Completed event and set its Active property to `false`. A Transient that has been Completed will do no more work of its own accord. It will remain in effective limbo until collected by the .Net runtime.

We can chain the completion of two Transient objects A and B by writing `A.CompleteAfter(B)`. We can also delay completion of a Transient by writing `A.CompleteAfter(TimeSpan)`.

Almost all objects in the library implement ITransient, including [IFuture\<T\>](http://github.com/cschladetsch/Flow/blob/master/Interface/IFuture.cs). This interface represents a potential Future value that has not Arrived yet. When the value is eventually set, the future will fire its Arrived event, then Complete itself. This is what was going on in Line 6 in the first example, where the consumer Coroutine was waiting for the Future to be Completed. Completing a Transient object multiple times does nothing – only the first completion will fire the Completed event.

Another key concept is [Generator](http://github.com/cschladetsch/Flow/blob/master/Interface/IGenerator.cs), which is also a Transient. A Generator can be Suspended and Resumed. Generators do some work every time their Step method is called, unless it is Suspended or Completed. The result of that work is stored in its Value property.

[Coroutine](http://github.com/cschladetsch/Flow/blob/master/Interface/ICoroutine.cs) and [Subroutine](http://github.com/cschladetsch/Flow/blob/master/Interface/ISubroutine.cs) derive from Generator. The key difference between them is how work is done during the Step. For a Subroutine, the work is simply a method call. For a Coroutine, the work is to resume the Coroutine from the point of its last yield – or from the start of its method if it hasn't been Stepped before.

## Groups and nodes
So far we have spoken about Transients, Futures, and Generators, but to manage them we need a few more concepts. First we have the idea of a [Group](http://github.com/cschladetsch/Flow/blob/master/Interface/IGroup.cs), which contains a collection of other Transients, and fires events (Added, Removed) when the contents of the group changes.

A Group is also a Generator, and when the Group is Suspended, it Suspends all Generators that it contains. Similarly, when a Group is Resumed, it Resumes all Generators within it. Stepping a Group does no work.

Then we have a [Node](http://github.com/cschladetsch/Flow/blob/master/Interface/INode.cs), which is a Group. The key difference here is that when a Node is Stepped in the [implementation](https://github.com/cschladetsch/Flow/blob/master/Node.cs), it also Steps all Generators within it. Note that Nodes are themselves Transients, so they can form a process flow hierarchy.

We also have [Barriers](https://github.com/cschladetsch/Flow/blob/master/Barrier.cs) and [Triggers](https://github.com/cschladetsch/Flow/blob/master/Trigger.cs), both of which are also Groups. A Barrier is a Group that Completes itself when all added Transients have been Completed. A Trigger Completes itself when any of the objects in it are Completed.

You would use a Barrier when you want to pause execution until a collection of Transients have been Completed. An example may be waiting to start a game:

~~~ csharp
IEnumerator<bool> StartGame(IGenerator self, IEnumerable players, TimeSpan waitTime) {
    ITimedBarrier barrier = self.Factory.NewTimedBarrier(waitTime);

    var acceptance = new List<IFuture>();

    // add each players' acceptance into a barrier
    foreach (var player in players) {
        IFuture<bool> accept = player.RequestAccept(self);
        // send a request up to the UI

        acceptance.Add(accept);
        // keep a record of the future

        barrier.Add(accept);
        // add it to the barrier
    }

    // wait for the barrier to Complete: this may be due to a timeout, or all elements being Completed
    yield return self.ResumeAfter(barrier);

    // if the barrier timed out, not all players accepted in time
    if (barrier.HasTimedOut)
        yield break;

    // if any player did not accept, do not start
    foreach (var accept in acceptance)
        if (!accept.Available || !accept.Value)
            yield break;

    // run the game
    yield return self.ResumeAfter(RunGame());

    // end the game
    yield return self.ResumeAfter(EndGame());

    // reset game for next start
    Reset();
}
~~~

Say you want to pause game flow until any player presses a button:

~~~ csharp
IEnumerator<bool> WaitForAnyPlayerPress(IGenerator self, IEnumerable players) {
    var trigger = self.Factory.NewTrigger();

    foreach (var player in players) {
        trigger.Add(player.RequestPress());
        // push request to present and push button up to the user interface
    }

    yield return self.ResumeAfter(trigger);
    // wait until any player presses a button

    var firstPlayer = trigger.Reason;
    // do something with knowledge that 'firstPlayer' was the first to press the button
}
~~~

## Timers
Then we have a one-shot [Timer](https://github.com/cschladetsch/Flow/blob/master/Interface/ITimer.cs) that will fire its Elapsed event, and then Complete itself after a fixed time Interval, and a [Periodic](https://github.com/cschladetsch/Flow/blob/master/Interface/IPeriodic.cs) Timer that regularly fires its Elapsed event.

## Summary
There are other little bits and pieces, but these are the core concepts in the framework. I realise that's a lot of information, but some examples are coming! In the meantime, you can always just read the [test suite](https://github.com/cschladetsch/Flow/tree/master/TestFlow).

In summary so far, the Flow Library consists of a set of interfaces based on ITransient. From this we have Generators that can be Suspended and Resumed (Coroutines and Subroutines), Groups that contain other Transients (Barriers, Triggers and Nodes), and two timers: a one-shot and a periodic.

# Communications
A [Channel](http://github.com/cschladetsch/Flow/blob/master/Interface/IChannel.cs) represents a stream of values that can be inserted into and extracted from. See also the [implementation](http://github.com/cschladetsch/Flow/blob/master/Channel.cs).

Channels are used for inter-Coroutine communication. See the [test suites for Channels](http://github.com/cschladetsch/Flow/blob/master/TestFlow/TestChannel.cs) for more details.

# At the Top
This is all wrapped up in a top-level [Kernel](https://github.com/cschladetsch/Flow/blob/master/Kernel.cs) that contains a [Factory](https://github.com/cschladetsch/Flow/blob/master/Interface/IFactory.cs) for making new objects, and a Root Node that is Stepped when the Kernel is Stepped.

To make a new Kernel, use `var kernel = Flow.Create.NewKernel();`

From there, the Factory is available via `kernel.Factory`. Each ITransient also has access to the Kernel and Factory that made it.

To tick things over, simply call `kernel.Step()`. This will give every Generator that has been created by the Kernel a chance to do some work.

# Why bother?
Transients, generators, nodes, barriers, channels… Oh my! Is all this stuff really needed?

Programming real-time systems such as games or distributed networked object models requires dealing with asynchronous events. These events may be user input, the result of other software processes, network input, or other hardware-based events. This is probably a good time to plug a previous article of mine on [C++ events](http://www.altdevblogaday.com/2011/10/30/c-events/).

However, it's not just spontaneous events that we are interested in. In order to reduce complexity and improve readability, we also need to be able to defer continuation of the current flow until some other process has completed. Here's another motivational example, this time completely hypothetical:

~~~ csharp
IEnumerator RollDice(IGenerator self, IPlayer player) {
    IFuture<int> roll = player.RequestRoll();
    // push the request up to the user interface - the result is a future value

    yield return self.ResumeAfter(roll);
    // wait for result

    if (!roll.Available) yield break;
    // player cancelled the roll, or otherwise the roll didn't happen

    var action = game.ProcessRoll(player, roll.Value);
    // business logic on the roll result - return value is possibly another corotuine

    yield return self.ResumeAfter(action);
    // wait for action to complete- maybe other players can interject, play other cards, who knows

    if (!action.Available) yield break;
    // action was cancelled

    if (action.Value.Processed) RedrawCards();
    // if the action was processed, then redraw the ui
}
~~~

This example shows the general gist of how the Flow library is intended to be used. If you need something external to happen, you resume after it has been completed.

You do not have to preserve state between Update calls because there is no Update. You do not need switch statements to find out what state you were in when you left the last Update. The process just… flows.

Have you noticed that a lot of work in your Update() methods is done just to determine where you were when you last left the Update method? Tired of managing what 'State' you are in?

Here's another example, this time for a hypothetical network model:

~~~ csharp
private IEnumerator AbortJob(IGenerator self, string machine, int jobNumber) {
    ITimedFuture<IPeer> peer = _peer.Connect(machine);
    // connect to remote machine.

    yield return self.ResumeAfter(peer);
    // wait till we connect to the remote machine, or time-out

    if (!peer.Available || !peer.Value.Connected)
        yield break;
        // we failed to connect

    IFuture<IWorkerProxy> worker = peer.Value.CreateProxy<IWorkerProxy>("Worker");
    // get a local proxy to a remote instance

    yield return self.ResumeAfter(worker);
    // wait for a response

    IFuture<IJobProxy> job = worker.Value.GetJob(jobNumber);
    // query on job number

    yield return self.ResumeAfter(job);
    // wait for a response

    job.Value.Abort();
    // kill the remote job
}
~~~

Basically, this connects to a remote machine, queries it for an instance called 'Worker' of type IWorkerProxy, and uses that proxy to find a job with a given number, and then aborts that job.

As an exercise to the reader, I ask that you imagine what this would look like using threads.

You may be wondering 'yeah but I'm not making a distributed game' – well, perhaps that's true, but even so the idea of retaining context between asynchronous calls, or between successive calls to Update(), is very expressive and makes code far easier to write and read.

# What about Threads?
Writing non-trivial multi-threaded applications is hard. They are hard to write, read, test and maintain. Again, try to imagine what the previous examples would look like without the ability to suspend local flow until a remote process or event completes.

Threads do not scale to tens of thousands. You may have 12 cores, but you can't successfully deploy a system that has tens of thousands of threads. There is too much overhead per thread.

Threads can be inefficient – because you need to guard against resource contention, any shared data is expensive.

Have I mentioned that writing a non-trivial multi-threaded application that works is really hard?

Now, I realise that some of you will just think "yeah well, Christian just doesn't understand how to write multi-threaded applications! It's not all that hard".

Yes, it really is hard to write correct multi-threaded applications. In any case, if you have a system such as a game that has thousands of entities, you cannot put each on its own thread, so you are stuck with convoluted flow-control and manual state management between Update calls.

Sure, you can use callbacks and state machines and so on, but they become gnarly very quickly, and brittle, and error prone. And at best, what you will end up with is a poor-man's Coroutine-based Kernel, even if you don't realise it. [As they say](http://en.wikipedia.org/wiki/Greenspun&apos;s_tenth_rule), within every large C program is a poorly written Lisp interpreter. And similarly, I claim that within any large interactive application is a poorly written Coroutine Kernel.

Coroutines are not a replacement for threads. One of the main advantages of coroutines is that they allow writing entity-logic as if each entity was on a thread – much state is stored in local variables, instead of storing/restoring state between update calls. But they avoid the race conditions that come with threads.

Paraphrased from Bruce Dawson, Cygnus Software, in the author list for #AltDev in a thread on this article:

>"I'd previously said that the reason to avoid threads was to avoid their cost, and this is part of the reason, but probably not the main one. The fact that coroutines are not threaded, and therefore don't need to worry about race conditions, locks, concurrent access, etc., is a significant part of their benefit. It's really enormously huge. Unfortunately that means that if you put coroutines on multiple threads (to get more throughput) you lose one of their main advantages."

If you are happy using threads, I wish you well on your way.

For those of us that seek sanity, readability, testability, repeatability and efficiency, let's have a look at how a first-class coroutine library can be implemented in .Net.

# Implementation
The implementation of the library is quite simple. I encourage you to pull a copy of the source and just browse around the test suites and read some of the code. It is quite small and readable. The best way to understand it really is to just read the code.

Here's Transient.cs:

~~~ csharp
internal class Transient : ITransient {
    public event TransientHandler Completed;

    public IKernel Kernel { get; internal set; }

    public IFactory Factory  { get { return Kernel.Factory; } }

    public bool Active { get; private set; }

    internal Transient() {
        Active = true;
    }

    public void Complete() {
        if (!Active)
            return;

        if (Completed != null)
            Completed(this);

        Active = false;
    }

    public void CompleteAfter(ITransient other) {
        if (!Active || other == null)
            return;

        if (!other.Active) {
            Complete();
            return;
        }

        other.Completed += tr => Complete();
    }

    public void CompleteAfter(TimeSpan span) {
        CompleteAfter(Factory.NewTimer(span));
    }
}
~~~

I hope this is all very obvious. Pay attention however to the CompleteAfter method. Here, if we are given a non-null Transient that has already been Completed, then we immediately Complete ourself and move on. Otherwise, we add a hook into the other's Completed event, which when fired will Complete this Transient as well.

Basically, not very interesting and I hope almost boring. There are very few tricks in the library in general, just a build up of core concepts within a solid framework. It may be alien at first, but rest assured if something goes wrong, since you have the source, it will be easy to debug.

Note though that you may well need to add a Debug Trace system to the raw source. I didn't do so for brevity and clarity, but despite what I said above, when you have nested Nodes and Barriers and Futures, unwinding an error can be tedious without logging information. If I was going to extend this library further, the very next thing I would add would be a logging system.

As another example, here's the default implementation for a Future\<T\> value:

~~~ csharp
internal class Future<T> : Transient, IFuture<T> {
    public event FutureHandler<T> Arrived;

    public bool Available { get; private set; }

    public T Value {
        get {
            if (!Available)
                throw new FutureNotSetException();

            return _value;
        }
        set {
            if (Available)
                throw new FutureAlreadySetException();

            _value = value;
            Available = true;

            if (Arrived != null)
                Arrived(this);

            Complete();
        }
    }

    private T _value;
}
~~~

It is what it is, I am not sure how I can add anything by talking about it. Perhaps the implementation of Coroutine will be juicier?

# Making coroutines

This is the implementation for Coroutines (see [source](http://github.com/cschladetsch/Flow/blob/master/Coroutine.cs)):

~~~ csharp
internal class Coroutine : Generator, ICoroutine {
    public override void Step() {
        if (!Running || !Active)
            return;

        if (_enumerator == null) {
            if (Start == null)
                CannotStart();

            _enumerator = Start();

            if (_enumerator == null)
                CannotStart();
        }

        if (!_enumerator.MoveNext()) {
            Complete();
            return;
        }

        Value = _enumerator.Current;

        base.Step();
    }

    void CannotStart() {
        throw new Exception("Coroutine cannot start");
    }

    private IEnumerator_enumerator;

    internal Func<IEnumerator> Start;
}
~~~

Ok so let's try to understand what is going on in the Step method. First, we do nothing if the Coroutine doesn't Exist. This means that it has been previously Completed. We also do nothing if we are not Running, that is, if the Coroutine has been Suspended. So far so good.

Then we test if we have an `_enumerator`. This is like a program counter for coroutines. It manages the state we are in when we yield. If we do not have one, we see if we can make one from the strange-looking Start member field.

Its type is Func\<IEnumerator\>, which is a delegate that when invoked with no arguments returns an IEnumerator. This is then used to do work in the Coroutine.

An obvious question is where is this Start member set? It's not here, in the Coroutine class. So, let's see what the [Factory](https://github.com/cschladetsch/Flow/blob/master/Interface/IFactory.cs) does when asked to make a new Coroutine. Go ahead, open the [source for Factory.cs](https://github.com/cschladetsch/Flow/blob/master/Factory.cs). Here's one case, of a Coroutine with an extra argument:

~~~ csharp
public ICoroutine<TR> NewCoroutine<TR>(Func<IGenerator, T0, IEnumerator<TR>> fun, T0 t0) {
    var coro = new Coroutine<TR>();

    coro.Start = () => fun(coro, t0);

    return Prepare(coro);
}
~~~

Now we are getting somewhere – we see that the Factory sets the Start field of the Coroutine to be a function object that invokes the function passed to the Factory, and also passing the arguments that will be pushed through to the Coroutine instance when it sets its _enumerator = Start();

Note also the pattern for all Coroutine signatures:

~~~ csharp
Func<IGenerator, T0, T1, ..., Tn, IEnumerator<TR>>
~~~

All Coroutine methods take as their first argument the Coroutine instance itself. It may be surprising that this is an IGenerator and not an ICoroutine\<T\> – the reason for this is ease of use. IGenerator does not include the return type information T, but otherwise contains all the functionality we need to control [Coroutines](https://github.com/cschladetsch/Flow/blob/master/Interface/ICoroutine.cs), such as Suspend, Resume, SuspendAfter, ResumeAfter methods, etc. These are common with [Subroutines](https://github.com/cschladetsch/Flow/blob/master/Interface/ISubroutine.cs) as well.

It's just easier to use IGenerator as the 'self' argument to both Subroutines and Coroutines, without having to also include the return type, such as:

~~~ csharp
IEnumerator<string> Coro(ICoroutine<string> self) { ... }
~~~

# Examples
The best place to see some examples is the [test suite](https://github.com/cschladetsch/Flow/tree/master/TestFlow).

# Future Work
During the writing of this article, it became clear that there is more to these ideas and this library than can be successfully covered in a single post.

So, while typically here I would point out future work to be done on the library itself, I will instead promise to write more about Coroutines and this library in the future. Pun intended.
Conclusion

This article presented a Coroutine-based Kernel for .Net, including a number of useful concepts for flow control, including:

- Transient
- Future\<T\>
- Barrier
- Channel\<T\>
- Kernel

The source code is freely available and can be used without permission in commercial products.