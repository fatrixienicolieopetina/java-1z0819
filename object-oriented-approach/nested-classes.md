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


