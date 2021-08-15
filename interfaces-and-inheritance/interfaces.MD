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
To avoid the scenario where implementing classes need to change because of the additions to the implemented interface:
1. Create a new interface that extends to the changed interface. In this way, implementing classes only need to change what interface to implement, whether the child or the parent. Now users of the code can choose to continue to use the old interface or to upgrade to the new interface.
2. Alternatively, new methods can be defined as default methods. Since implementations are provided for default methods,  users who have classes that implement interfaces enhanced with default or static methods do not have to modify or recompile them to accomodate the additional methods.

### Default Methods
Default methods enable one to add new functionality to the interfaces of the library to ensure binary compatibility with code written for older versions of that interfaces.
1. A default method in an interface is defined with the `default` keyword at the beginning of the method signature. All method declarations in an interface, including default methods are implicityly public so the `public` modifier can be omitted.

#### Extending Interfaces that Contain Default Methods
When an interface with a default method is extended, 
1. There is no need to mention the default method at all, which lets the extended interface inherit the default method
2. The default method can be redeclared which makes it abstract
3. The default method can be redefined by overriding it

### Static Methods
A static method can also be defined in an interface. It is a method that is associated with the class in which it is defined rather than with any object. Every instance of the class shares its static methods. Now this helps in organizing helper methods.

### Integrating Default Methods into Existing Libraries
Default methods enable the addition of new functionality to existing interfaces and ensure binary compatibilty with code written for older versions of those interfaces. In particular, default methods enable the addition of methods that accept lambda expressions as parameters to existing interfaces.

### Summary 
1. An interface declaration can contain method signatures, default methods, static methods and constant definitions. The only methods that have implementations are default and static methods
2. A class that implements an interface must implement all the mothods declared in the interface.
3. An interface name can be used anywhere a type can be used.
