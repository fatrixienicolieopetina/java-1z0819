# Annotations

### 📌 Annotation Basics
Annotations, a form of metadata, provide data about a program that is not part of the program itself. It has no direct effect on the operation of the code they annotate.

Annotations hava a number of uses
1. **Information for the compiler**. Annotations can be used by the compiler to detect errors or supress warnings.
2. **Compile-time and deployment time processing**. Software tools can process annotation information to generate code, XML files and so forth.
3. **Runtime processing**. Some annotations are available to be examined at runtime.

### 📌 Declaring an Annotation Type
The simplest format of an annotation looks like
```java
@Entity
```

The @ (sign character) indicates to the compiler that what follows is an annotation. The annotation above has a name `Entity`.

Annotations can also include elements which can be named or unnamed. For instance,
```java
@Author(
   name = "Benjamin Franklin",
   date = "3/27/2003"
)
```
If there is only one element named `value`, then the name can be omitted, as in: 
```java
@SuppressWarnings("unchecked")
void myMethod() { ... }
```

If the annotation has no elements, then the parentheses can be omitted,
```java
@Override
void mySuperMethod() { ... }
```
It is also possible to use multiple annotations on the same declaration.
```java
@Author(name = "Jane Doe")
@EBook
class MyClass { ... }
```
If the annotations have the same type, then that would be a `repeating annotation`.
```java
@Author(name = "Jane Doe")
@Author(name = "John Smith")
class MyClass { ... }
```

The annotation type can be one of the types that are defined in the `java.lang` or `java.lang.annotation` packages, like `@Override` and `@SuppressWarnings`, which are predefined Java annotations. It is also possible to define your own annotation type, i.e. custom annotations.

#### Where Can Annotation Be Used
Annotations can be applied to declarations: classes, fields, methods and other program elements. 

As of Java 8, annotations can be applied to the `use` of types. This form of annotation is called a type annotation.

* Class instance creation expression
```java
new @Interned MyObject();
```
* Type Cast
```java
myString = (@NonNull String) str;
```
* `implements` clause
```java
class UnmodifiableList<T> implements
        @Readonly List<@Readonly T> { ... }
```
* Thrown exception declaration
```java
void monitorTemperature() throws
        @Critical TemperatureException { ... }
```
### 📌 Predefined Annotation Types
### 📌 Type Annotations and Pluggable Type Systems
### 📌 Repeating Annotations
