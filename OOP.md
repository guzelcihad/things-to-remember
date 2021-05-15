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
The goal is to prevent this bound data from any unwanted access by the code outside this class. This way,
at some point of time, if you want to change the implementation details of the class EmployeeCount, you can freely do so without affecting the classes that are using it.

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

# Inheritance
Inheritance provides a way to create a new class from an existing class. The new class is a specialized version of the existing class such that it inherits all the non-private fields (variables) and methods of the existing class. The existing class is used as a starting point or as a base to create the new class.

Creates is a relationship. Square is a shape.

## Super 
Note: The call to the SuperClass constructor using super() is usually the first line of code inside the constructor of the SubClass. If we do not call super() in the SubClass constructor, the default no-argument constructor of SuperClass is called automatically. The super(parameters) call has to be used if we want to call a parameterized constructor of the SuperClass.

Note: In a constructor we can include a call to super() or this() but not both. Also, these calls can only be used inside the constructors.

## Diaomon Problem
We will discuss this problem with the help of the diagram below: which shows multiple inheritance as Class D extends both classes B & C. Now lets assume we have a method in class A and class B & C overrides that method in their own way. Wait!! here the problem comes – Because D is extending both B & C so if D wants to use the same method which method would be called (the overridden method of B or the overridden method of C). Ambiguity. That’s the main reason why Java doesn’t support multiple inheritance.
<br>
Can we implement more than one interface in a class

> As you can see that the class implemented two interfaces. A class can implement any number of interfaces. In this case there is no ambiguity even though both the interfaces are having same method. Why? Because methods in an interface are always abstract by default, which doesn’t let them give their implementation (or method definition ) in interface itself.

Advantages of inheritance
* Re-usability
* Avoiding duplicate code
* Extensibility
> Using inheritance, one can extend the base class logic as per the business logic of the derived class. This is an easy way to upgrade or enhance specific parts of a product without changing the core attributes. An existing class can act as a base class to derive a new class having upgraded features.
* Data hiding 

# Polymporphism
So far, we have learned that we can add new data and methods to a class through inheritance. But what if we want our derived class to inherit a method from the base class and have a different implementation for it? That is when polymorphism, a fundamental concept in the OOP paradigm, comes into play.

## Override
In other words, if a subclass provides the specific implementation of a method that has been declared by one of its parent classes, it is known as method overriding.

<br>
Advantages
* The derived classes can give their own specific implementations to inherited methods without modifying the parent class methods.
* For any method, a child class can use the implementation in the parent class or make its own implementation.

> Derived class/es must have the same declaration, i.e., access modifier, name, same parameters and same return type of the method as of the base class.
> Base class/method must not be declared as the Final class.

Overloading | Overriding
--- | --- |
Overloading happens at compile time | Overriding happens at runtime | 283 |
Private and final methods can be overloaded. | Private and final methods can not be overridden. | 283 |
Return type of method does not matter in case of method overloading. | Return type of method must be the same in the case of overriding | 283 |
Arguments must be different in the case of overloading. | Arguments must be the same in the case of overriding. | 283 |
It is being done in the same class. | Base and derived classes are required here. | 283 |
Mostly used to increase the readability of the code.. | Mostly used to provide the implementation of the method that is already provided by its base class. | 283 |

<br>
Always use shape, rectangle, circle example

## Dynamic Polymorphism
Dynamic polymorphism is the mechanism by which methods can be defined with the same name, return type, and parameters in the base class and derived classes.

```
Shape obj1 = new Circle(3); 
Shape obj2 = new Rectangle(2, 3);

//.
//.
//.

obj1.getArea();
obj2.getArea();
```
Here, the reference variables obj1 and obj2 are of the Shape class, but they are pointing to the Circle and Rectangle respectively.

* obj1.getArea() will execute getArea() method of the subclass Circle class.
* obj2.getArea() will execute getArea() method of the subclass Rectangle class.

This is decided during runtime and is, therefore, called dynamic or runtime polymorphism.

![alt text](images\14.PNG)

# Abstraction
Abstraction in Object-Oriented Programming refers to showing only the essential features of an object to the user and hiding the inner details to reduce complexity. It can be put this way that the user only has to know “what an object does?” rather than “how it does?”.

## ADT
An abstract data type (or class) is a type that only defines ‘what operations are to be performed?’ rather than ‘how to be performed?’
<br>
An example of abstract data type can be a built-in stack class in Java for which the user knows that it has the push(), pop(), size() e.t.c. methods but doesn’t know how these are implemented.
<br>
How to Achieve Abstraction

> Abstract class
> Interface 

# Interface
An interface is just like a class and specifies the behavior that a class must implement.
* All the methods declared or implemented in an interface are by default public and all the variables are by default public static final.
* An interface cannot have constructor(s) in it.
* An interface cannot be declared private or protected.

Advantages
* Interfaces can be used to achieve loose coupling in an application. This means that a change in one class doesn’t affect the implementation of the other class.
* By the use of interfaces, one can break up complex designs and clear the dependencies between objects.
* Interfaces can be used to achieve multiple inheritance

Interface | Abstract Class
--- | --- |
Support multiple inheritance | Don’t support multiple inheritance | 283 |
All members are public | Can have private, protected and public members | 283 |
All data members are static and final | Can have non-static and non-final members too | 283 |
Can’t have constructors | Constructors can be defined | 283 |

# Interaction Between Objects
While inheritance represents a relationship between classes, there are situations where there are relationships between objects.

## Has A
This is a slightly less concrete relationship between two classes. Class A and class B have a has-a relationship if one or both need the other’s object to perform an operation, but both class objects can exist independently of each other.

This implies that a class has-a reference to an object of the other class but does not decide the lifetime of the other class’s referenced object.
<br>
Association

> In object-oriented programming, association is the common term used for both the has-a and part-of relationships but is not limited to these. When we say that two objects are in an association relationship, this is a generic statement which means that we don’t worry about the lifetime dependency between the objects. In the next couple of lessons, we will dive into the specialized forms of association: Aggregation and Composition. 

## Aggregation
It's a directional association, which means it is strictly a one way association.
Aggregation follows the has-A model. This creates a parent-child relationship between two classes, with one class owning the object of another.

In aggregation, the lifetime of the owned object does not depend on the lifetime of the owner.
<br>
The owner object could get deleted, but the owned object can continue to exist in the program. In aggregation, the parent only contains a reference to the child, which removes the child’s dependency.
<br>
Think that Country and User example. Each user associated with a country, but country can exist without 
that user.
<br>
Advantages of aggregation is reusability. We don't need to create define country 
every time in user.


## Composition
Composition is the practice of creating other class objects in your class. In such a scenario, the class which creates the object of the other class is known as the owner and is responsible for the lifetime of that object.
<br>
In composition, the lifetime of the owned object depends on the lifetime of the owner.
<br>
A car is composed of an engine, tires, and doors. In this case, a Car owns these objects so a Car is an Owner class and tires,doors and engine classes are Owned classes.

![alt text](images\15.PNG)
![alt text](images\16.PNG)

## 