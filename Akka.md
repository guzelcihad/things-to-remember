## Problem with Thread Model
OOP encapsulation is only valid in single threaded model.
> Can be solved by synchronization, but it creates another problems like deadlocks, livelocks.

> We need a data structure that is fully encapsulate in a multi threaded or distributed environment,
without use of locking.

- Tracing and dealing with errors in a multithreaded env. is pain
- Messaging or signaling between threads are error prone and hard

## Actors
With traditional objects:
- we store their state as data
- we call their methods

With Actors:
- we store their state as data
- we send messages to them, asynchronously

Actors are objects we cant access directly but only send messages.

## Actors Programming
First we create ActorSystem, this is like a pool of thread
<br>
Then we define actors in this system. 
- Actors are uniquely identified.
- Messages are asynchronous
- Each actor may respond differently
- Actors are encapsulated

### Message Types
Messages can be of any type
> but must be immutable and serializable. In practice we use case classes and case object