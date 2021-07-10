# 📌 Nested Classes
1. A nested class is a class within another class.
2. Nested classes are divided into two categories: non-static and static.
3. Non-static nested class are called **_inner classes_**
4. Nested classes that are declared static are called **_static nested classes_**.
5. A nested class is a member of its enclosing class. **Non-static nested classes (inner classes) have access to other members of the enclosing class, even if they are declared private. Static nested classes DO NOT have access to other members of the enclosing class.** As a member of the ouer class, a nested class can be declared `private`, `public`, `protected` or `package-private`.
6. Note that outer classes can only be declared public or package-private.

### 📌 Why Use Nested Classes
1. It is a way of logically grouping classes that are only used in one place.
2. It increases encapsulation.
3. It can lead to more readable and maintainable code. 

### 📌 Inner Classes
1. An inner class is associated with an instance of its enclosing class and has direct access to that object's methods and fields. 
2. As an inner class is associated with an instance, **IT CANNOT DEFINE ANY STATIC MEMBERS ITSELF.**. 
3. Objects that are instances of an inner class exist within an instance of the outer class. Thus an instance of an inner class can only exist within an instance of the outer class and has direct access to the methods and fields of the enclosing instance.
4. To instantiate an inner class, the outer class must first be instantiated. 
5. There are two special kinds of inner classes: **local classes** and **anonymous classes**.

### 📌 Static Nested Classes
1. As with class methods, a static nested class is assoiciated with its outer class. 
2. A static nested class cannot refer directly to instance variables or methods defined in its enclosing class. It can use them only through an object reference.
3. A static nested class interacts with the instance members of its outer class and other classes just like any other top level class. **Thus a static nested class is behaviorally a top-level class that has been nested in another top-level class for packaging convenience.**

### 📌 Shadowing
1. If a declaration of a type in a particular scope has the same name as another declaration in the enclosing scope, then the declaration shadows the declaration of the enclosing scope.
2. The shadowed declaration cannot be referec by its name alone. Note, you can actually do this : `ShadowTest.this.x`. Check this cole [Go to shadowing section of this link](https://docs.oracle.com/javase/tutorial/java/javaOO/nested.html).
3. Refer to member variables that enclose larger scopes by the class name to which they belong. For example, the ff. statement accesses the member variable of the class `ShadowTest` from the method.
`System.out.println("ShadowTest.this.x = " + ShadowTest.this.x);`

### 📌 Serialization
1. Serialization of inner classes, including local and anonymous classes is strongly discouraged. When the Java compiler compiles certain constructs such as inner classes, it creates _synthetic constructs_; these are classes, methods, fields and other constructs that do not have a corresponding construct in the source code. Synthetic constructs enable Java compilers to implement new Java language features without changes to the JVM. However, they may vay among different implementations.
2. Might have compatibility issues if an inner class is serialized and then deserialize it with a different JRE implementation.
3. Read more at the Serialization section of this [link](https://docs.oracle.com/javase/tutorial/java/javaOO/nested.html)

### 📌 Local and Anonymous Classes
1. There are two types of inner classes : local and anonymous. Inner class within the body of a method is called a local class. An **inner class** can also be declared inside the body of a method without naming them, i.e. an **anonymous**.
2. The same modifiers used for other members of the outer class can be used for an inner class. For instance the access modifers `private`, `public`, `package-private` `protected` can be used in an inner class just like how they are used for the instance fields of the outer class.

#### 📌 [More on Local Classes](https://docs.oracle.com/javase/tutorial/java/javaOO/localclasses.html)
1. Local classes are classes defined in a block, which is a group of zero or more statements. 
2. Local classes can be defined inside any block, i.e. in a method body, a for loop or an if clause.
3. A local class has access to the members of its enclosing class. It also has access to local variables.
4. **IMPORTANT: A local class can only access localvariables that are declared final.** When a local class accesses a local variable or parameter of the enclosing block, it **_captures_** the variable or parameter.
5. Starting Java 8, a local class can access local variables and parameters of the enclosing block that are final or effectively final. A variable or parameter whose value is never changed after it is initialized is **effectively final**.
6. Starting also in Java SE 8, if you declare the local class in a method, it can access the ,ethod's parameters.
7. Local classes are similar to inner classes because they cannot define or declare any static members.
8. Local classes in static methods, can only refer static members of the enclosing classes.
9. Local classes are non-stattic because they have access to instance members of the enclosing block. Consequently they cannot contain most kinds of static declarations.
10. An interface cannot be declared inside a block. Interfaces are inherently static.
11. Static initializers or member interfaces cannot be declared inside a local class. 
12. A local class can have static members provided that they are constant variables. A _constant variable_ is a variable of primitive type of type String that is declared final and initialized with a compile-time constant expression. A compile time constant expression is typically a string or an arithmetic expression that can be evaluated at compile time.

### 📌 Anonymous Classes
1. Anonymous classes makes the code more concise. It enables declaration and instantiation of class at the same time. They are similar to local classes except that they do not have a name.
2. While local classes are class declaration, **anonymous classes are expressions**, which means that the class is defined in another expression. 
3. The syntax of an anonymous class expression is like the invocation of a constructor, except that there is a class definition contained in the code block.
```java
HelloWorld helloWorld = new HelloWorld() {
  // code here
};
```
4. The anonymous class expression consists of the following: `new` operator, the name of an interface to implement or a class to extend, parentheses that contain the arguments to a constructor, just like a normal class instance creation expression and a body, which is a class declaration body.
5. Because an anonymous class definition is an expression, it must be part of a statement. This explains why there is a semicolon after the closing brace.

#### 📌 Accessing Local Variables of the Enclosing Scope and Declaring and Accessing Members of the Anonymous Class
1. Like local classes, anonymous classes can capture variables; they have the same access to local variables of the enclosing scope.
2. An anonymous class has access to the members of its enclosing class
3. An anonymous class cannot access local variables in its enclosing scope that are not declared as final or effectively final.
4. Like a nested class, a declaration of a type in an anonymous class shadows any other declarations in the enclosing scope that have the same name.
5. Anonymous classes also have the same restrictions as local classes with respect to their members: static initializers or member interfaces cannot be declared; an anonymous class can have static members provided that they are constant variables. 
6. Note, the ff can be declared in anonymous class
  a. Fields
  b. extra methods
  c. instance initializers
  d. local classes
8. **IMPORTANT: You cannot declare constructors in an anonymous class.**
9. Anonymous classes are ideal for implementing an interface that contains two or more methods.

### 📌 [Lambda Expressions](https://docs.oracle.com/javase/tutorial/java/javaOO/lambdaexpressions.html)
1. Lambda Expressions enables developers to treat functionality as a method argument, or code as a data.
2. For classes with only one method, an anonymous class, much more a named class is a bit excessive and cumbersome. Lambdas express instances of single-method classes more compactly.

#### 📌 Syntax of Lambda Expressions
A lambda expression consists of the ff.
* A comma-separated list of formal parameters enclosed in parentheses. The data type of the parameters in the lambda expression can be omitted. Moreover, the parentheses can be omitted if there is only one parameter.
* The arrow token `->`
* The body which consists of a single expression or a statement block. The return statement can also be used, however, keep in mind that a return statement is not an expression in lambdas, so they must be enclosed in braces. Lambdas can be treated as anonymous methods - methods without names.

#### 📌 Functional Interface
A **_functional interface_** is any interface that contains only one **abstract method**. It may contain one or more default methods of static methods. Because it only contains one abstract method, the name can be omitted when implementing it. By doing this instead of using an anonymous class expression, a lambda expression is used. The JDK defines several standard functional interfaces which can be found in the package `java.util.function`.

#### Accessing Local Variables of the Enclosing Scope in Lambda Expressions
1. Like local and anonymous classes, lambdas can capture variables; they have the same access to local variables of the enclosing scope. However, unlike local and anonymous classes, lambdas do not have shadowing issues. 
2. Lambdas are **lexically scoped**. This means that they do not inherit any names from a supertype of introduce a new level of scoping. Declarations in lambdas are interpreted just as they are in the enclosing environment.
3. If the parameter passed to a lambda is declared in the enclosing scope, then the compiler generates an error, `Lambda expression's parameter {} cannot redeclare another local variable defined in an enclosing scope`. This is because lambda expressions do not introduce a new level of scoping. Consequently, lambdas can directly access fields, methods and local variables of the enclosing scope. 
4. Like local and anonymous classes, a lambda expression can only access local variables and parameters of the enclosing block that are **final** or **effectively final** (value should not be changed after initialization).

#### 📌 Target Typing in Lambdas
> So how can the type of a lambda expression determined, e.g. the type of p in the example below?
`p -> p.getAge() < 18`
When the Java runtime invokes the method where the lambda is passed, it is expecting a specific datatype, so the lambda expression is of this type.The data type that these methods expect is called the **target type**. To determine the type of a lambda expression, the Java compiler uses the target type of the context or situation in which the lambda expression was found. Thus, **_lambda expressions can only be used in situation in which the Java compiler can determin the target type: _**
* variable declarations
* assignments
* return statements
* array initializers
* method or constructor arguments
* lambda expression bodies
* conditional expressions
* cast expressions

##### Target Types and Method Arguments
For method arguments, the Java compiler determines the target type with two other language features **overload resolution** and **type argument interface**.

For instance, the functional interfaces `java.lang.Runnable` and `java.util.Callable<V>` is implemented and overloaded by a certain class.
```java
void invoke(Runnable r) {
    r.run();
}

<T> T invoke(Callable<T> c) {
    return c.call();
}
```

Which method will be invoked by the statement `String s = invoke(() -> "done");` ?
The method with argument `Callable<V>` will be invoked because the lambda returns a value, in this case the string `done`. Note that the method `invoke(Runnable)` does not return a value.

#### 📌 Serialization of Lambdas
A lambda can be serialized if its target type and its captured arguments are serializable. However, like inner classes, 🛑 **the serialization of lambdas are strongly discouraged**.


