# Interfaces

## 📌 Interfaces in Java
1. An interface is a reference type, similar to a class that can contain **only** constants, method signatures, default methods, static methods and nested types. 
2. Interfaces cannot be instantiated - they can only be implemented by classes and extended by ohter interfaces.
3. Note that an interface can extend any number of interfaces. The interface declaration can include a comma-separated list of all the interfaces that it extends.

### The Interface Body
The interface body can contain **abstract methods, default methods and static methods**. All of these methods in an interface are **implicitly** `public`, `static`, and `final`.

#### Implementing an Interface
A class can implement more than one interface. The `implements` keyword is followed by a comma-separated list of the interfaces implemented by the class.

### Using an Interface as a Type
When a new interface is defined, a new reference data type is defined. The interface names can be used anywhere a data type can be used. If a variable is assigned an interface type, any object assigned to it must be an instance of a class that implements the interface.

### Evolving Interfaces
https://docs.oracle.com/javase/tutorial/java/IandI/nogrow.html
