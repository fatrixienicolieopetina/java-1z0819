### 📌 Static Initialization Blocks
1. A static initialization block is a normal block of code enclosed in braces {}, and preceded by the static keyword. 
```java
static {
//code here
}
```
2. A class can have any number of static initialization blocks and they can appear anywhere in the class body. The runtime system guarantees that static initialization blocks are called in the order that they appear in the source code. 
3. To provide initialization of class variables which requires complex logic, Java included static initialization blocks.
4. There is an alternative to static blocks - the use of private static methods to initialize the variables. The advantage of private static methods is that they can be reused later if you need to reinitialize the class variable.

#### 📌 Initializing Instance Members
1. There are two alternatives in initializing instance variables aside from the use of constructors: **initializer blocks** and **final methods**.
2. Initializer blocks for instance variables look just like static initializer blocks, but without the static keyword. The Java compiler copies initializer blocks into every constructor. Therefore, this approach can be used to share a block of code between multiple constructors.
```java
{
 // initialize here
}
```
3. A `final` method cannot be overridden in a subclass. This is especially useful if subclasses might want to reuse the initialization method. The method is final because calling nonfinal methods during instance initialization can cause problems.
