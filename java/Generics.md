## Advantages
The Java Generics programming is introduced in J2SE 5 to deal with type-safe objects. It makes the code stable by detecting the bugs at compile time.
<br>
Before generics, we can store any type of objects in the collection, i.e., non-generic. Now generics force the java programmer to store a specific type of objects.

- Type-safety: We can hold only a single type of objects in generics. It doesn?t allow to store other objects.
- Type casting is not required: There is no need to typecast the object.
- Compile-Time Checking: It is checked at compile time so problem will not occur at runtime. The good programming strategy says it is far better to handle the problem at compile time than runtime.

## Wildcards
The ? (question mark) symbol represents the wildcard element. It means any type.
- Upper bounded `List<? extends Cls>`
- Lower bounded `List<? super Cls>`
- Unbounded `List<?>`

## Raw Types and Compatibility
