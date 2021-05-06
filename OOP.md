Why non-static variables or methods can not invoke from static method like main?
> The very basic thing is static variables or static methods are at class level. Class level variables or methods gets loaded prior to instance level methods or variables.And obviously the thing which is not loaded can not be used. So java compiler not letting the things to be handled at run time resolves at compile time. That's why it is giving you error non-static things can not be referred from static context. You just need to read about Class Level Scope, Instance Level Scope and Local Scope.

Research for classloader, JVM, JRE, JDk

## Overloading
> In overloading it is must that the both methods have same name.
different parameters (different type or, different number or both).
The return type doesn’t matter. If they don’t have different parameters, they both are still considered as same method and a compile time error will be generated.

> An obvious benefit is that the code becomes simple and clean. We don’t have to keep track of different methods.
> Polymorphism is a very important concept in object-oriented programming. It will come up later on in the course, but method overloading plays a vital role in its implementation.

Summarization:
> Overloading, makes code cleaner and readable. Allows implementation of polymorphism.

## This
The this keyword refers to the current object in a method or constructor.
The most common use of the this keyword is to eliminate the confusion between class attributes and parameters with the same name

## Data hiding
To make this object-oriented system more reliable and error free, it is a good practice to limit access to the class members.

In layman’s terms, data hiding refers to the concept of hiding the inner workings of a class and simply providing an interface through which the outside world can interact with the class without knowing what’s going on inside.
<br>
Components of data hiding

* Encapsulation
* Abstraction

Encapsulation is a fundamental programming technique in OOP used to achieve data hiding.
Encapsulation hides the state of the data.
The goal is to prevent this bound data from any unwanted access by the code outside this class.

Advantes:
> Classes are easier to change and maintain.
> We can specify which data member we want to keep hidden or accessible.
> We decide which variables have read/write privileges (increases flexibility).

User class, username and pass example.

* Effective java
> The single most important factor that distinguishes a well-designed component
from a poorly designed one is the degree to which the component hides its internal
data and other implementation details from other components. A well-designed
component hides all its implementation details, cleanly separating its API from its
implementation. Components then communicate only through their APIs and are
oblivious to each others’ inner workings. This concept, known as information
hiding or encapsulation, is a fundamental tenet of software design

> Information hiding is important for many reasons, most of which stem from
the fact that it decouples the components that comprise a system, allowing them to
be developed, tested, optimized, used, understood, and modified in isolation. This
speeds up system development because components can be developed in parallel.
It eases the burden of maintenance because components can be understood more
quickly and debugged or replaced with little fear of harming other components.

## Inheritance
Inheritance provides a way to create a new class from an existing class. The new class is a specialized version of the existing class such that it inherits all the non-private fields (variables) and methods of the existing class. The existing class is used as a starting point or as a base to create the new class.

Creates is a relationship. Square is a shape.