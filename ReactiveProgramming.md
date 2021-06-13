Reactor is an implementation of the Reactive Programming paradigm. 

* Reactive streams are push based.
* it is the Publisher that notifies the Subscriber of newly available values as they come, and this push aspect is the key to being reactive

<p>
Modern applications can reach huge numbers of concurrent users, and, even though the capabilities of modern hardware have continued to improve, performance of modern software is still a key concern.

There are, broadly, two ways one can improve a program’s performance:
* parallelize to use more threads and more hardware resources.
* seek more efficiency in how current resources are used.

Usually, Java developers write programs by using blocking code. This practice is fine until there is a performance bottleneck. Then it is time to introduce additional threads, running similar blocking code. But this scaling in resource utilization can quickly introduce contention and concurrency problems.
<p>
Worse still, blocking wastes resources. If you look closely, as soon as a program involves some latency (notably I/O, such as a database request or a network call), resources are wasted because threads (possibly many threads) now sit idle, waiting for data.
<p>
So the parallelization approach is not a silver bullet. It is necessary to access the full power of the hardware, but it is also complex to reason about and susceptible to resource wasting.
<p>
The second approach mentioned earlier, seeking more efficiency, can be a solution to the resource wasting problem. By writing asynchronous, non-blocking code, you let the execution switch to another active task that uses the same underlying resources and later comes back to the current process when the asynchronous processing has finished.
<p>
But how can you produce asynchronous code on the JVM? Java offers two models of asynchronous programming:

* Callbacks: Asynchronous methods do not have a return value but take an extra callback parameter (a lambda or anonymous class) that gets called when the result is available. A well known example is Swing’s EventListener hierarchy.

* Futures: Asynchronous methods immediately return a Future<T>. The asynchronous process computes a T value, but the Future object wraps access to it. The value is not immediately available, and the object can be polled until the value is available. For instance, an ExecutorService running Callable<T> tasks use Future objects.

Are these techniques good enough? Not for every use case, and both approaches have limitations.

* Callbacks are hard to compose together, quickly leading to code that is difficult to read and maintain (known as “Callback Hell”).

Future is better than callback, has been better since java 8 with CompletableFuture. But still some problems
* Composing multiple future objects still not easy
* We can end up with blocking situation with future object by calling get() method
* Do not support lazy computation
* They lack support for multiple values and advanced error handling

## From Imperative to Reactive Programming
Reactive libraries, such as Reactor, aim to address these drawbacks of “classic” asynchronous approaches on the JVM while also focusing on a few additional aspects:

* Composability and readability
* Data as a flow manipulated with a rich vocabulary of operators
* Nothing happens until you subscribe
* Backpressure or the ability for the consumer to signal the producer that the rate of emission is too high
* High level but high value abstraction that is concurrency-agnostic

Composability and Readability
> By “composability”, we mean the ability to orchestrate multiple asynchronous tasks, in which we use results from previous tasks to feed input to subsequent ones. The ability to orchestrate tasks is tightly coupled to the readability and maintainability of code. As the layers of asynchronous processes increase in both number and complexity, being able to compose and read code becomes increasingly difficult. As we saw, the callback model is simple, but one of its main drawbacks is that, for complex processes, you need to have a callback executed from a callback, itself nested inside another callback, and so on. That mess is known as “Callback Hell”. As you can guess (or know from experience), such code is pretty hard to go back to and reason about.


While the Reactive Streams specification does not specify operators at all, one of the best added values of reactive libraries, such as Reactor, is the rich vocabulary of operators that they provide. These cover a lot of ground, from simple transformation and filtering to complex orchestration and error handling.

## Nothing Happens Until You subscribe()
In Reactor, when you write a Publisher chain, data does not start pumping into it by default. Instead, you create an abstract description of your asynchronous process (which can help with reusability and composition).

## Subsription has several methods

```
subscribe(); 

subscribe(Consumer<? super T> consumer); 

subscribe(Consumer<? super T> consumer,
          Consumer<? super Throwable> errorConsumer); 

subscribe(Consumer<? super T> consumer,
          Consumer<? super Throwable> errorConsumer,
          Runnable completeConsumer); 

subscribe(Consumer<? super T> consumer,
          Consumer<? super Throwable> errorConsumer,
          Runnable completeConsumer,
          Consumer<? super Subscription> subscriptionConsumer); 
```

As you see we use lambdas. 

## An Alternative to Lambdas: BaseSubscriber