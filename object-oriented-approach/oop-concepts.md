# Object-Oriented Programming Concepts

### 📌 What are Objects
1. Real world observations all translate into the world of object-oriented programming. Real-world objects share two characteristics, they all have _state_ and _behavior_.
2. Software objects are conceptually similar to real-world objects; they too consist of state and related behavior. An object stores its state in **fields** and exposes its behavior through **methods**. 
3. **Methods** operate on an object's internal state and serve as the primary mechanism for object-to-object communication.
4. Hiding internal state and requiring all interaction to be performed through an object's method is known as **data ecapsulation**. 
5. By attributing state and providing methods for changing that state, the object remains in control of how the outside world is allowed to use it.
6. Building code into individual software objects provide a number of benefits, including:
    * **Modularity** : The source code for an object can be written and maintained independently of the source code for other projects. Once created, an object can be easily passed around inside the system.
    * **Information Hiding**. By interacting only with an object's methods, the details of its internal implementaion remain hidden from the outside world.
    * **Code reuse** : If an object already exists (might have been written by another programmer), that can be used in the program. This allows specialists to implement/test/debug complex, task-specific objects, which can then be trusted in your own code.
    * **Pluggability and Debugging Ease** . If a particular object turns out to be problematic, it can simply be removed from the application and plug in a different object as a replacement. Similar to fixing a mechanical problem in the real world, if a bolt breaks, it can be replaced, but not the entire machine.


### 📌 What are Classes
1. In real world, many individual objects have the same kind, i.e. they are built from the same set of blueprints and therefore contains the same components.
2. In object-oriented terms, a `class` is the blueprint from which individual objects are created.

### 📌 What is Inheritance.
1. Different kinds of objects often have a certain amount in common with each other. Yet, each also defines additional features that make them different. 
2. OOP allows classes to inherit commonly used state and behavior from other classes. 
3. In Java, each class is allowed to have **one direct superclass** and each superclass has the potential for an **unlimited number of subclasses**.

### 📌 What is an Interface
1. Methods form the object's interface with the outside world. 
2. In its most common form, an interface is a group of related methods with empty bodies.
3. Implementing an interface allows a class to become more formal about the behavior it promises to provide. 
4. Interfaces form a **contract** between the class and the outside world and this contract is enforced at **build time by the compiler**.
5. If the class claims to implement an interface, all methods defined by that interface must appear in its source code before the class will successfully compile.

### 📌 What are Packages
1. A package is a namespace that organizes a set of related classes and interfaces. Conceptually they are similar to folders in a computer. 
2. Because the prgram might be composed of hundreds and thousands of individual classes, it makes sense to keep things organized by placing related classes and interfaces into packages.
3. The java platform provides an enormous class library (a set of packages) suitable for use in applications. This library is known as the **"Applicaton Programming Interface (API)"**. Its packages represent tasks most commonly associated with general-purpose programming. The [Java Platform API Specification](https://docs.oracle.com/javase/8/docs/api/index.html) contains the complete listing for all packages, interfaces, classes, fields and methods supplied by the Java SE plaform.
