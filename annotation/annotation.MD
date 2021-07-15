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

#### Defining the annotation type
The syntax for doing this is:
```java
@interface ClassPreamble {
   String author();
   String date();
   int currentRevision() default 1;
   String lastModified() default "N/A";
   String lastModifiedBy() default "N/A";
   // Note use of array
   String[] reviewers();
}
```
The annotation type definitions looks similar to an interface definition where the keyword `interface` is preceded by the @ sign. Annotations are a form of interface. The body of the annotation definition contains `annotation type element` declaration, which look a lot like methods. They can also be defined with default values filled in.

**NOTE**: To make the information of an annotation appear in Javadoc-generated documentation, it must be annotated with the @Documented annotation.


### 📌 Predefined Annotation Types
A set of annotation types are predefined in the Java SE API.

#### Annotation Types Used by the Java Language
The predefined annotation types defined in `java.lang` are : `@Deprecated`, `@Override`, and `@SuppressWarnings`.
* `@Deprecated`. This indicates that the marked element is deprecated and should no longer be used. The compuler generates a warning whenever a program uses a method, class, or field with this annotation. When an element is deprecated it should also be documented using the Javadoc `@deprecated` tag.
```java
// Javadoc comment follows
    /**
     * @deprecated
     * explanation of why it was deprecated
     */
    @Deprecated
    static void deprecatedMethod() { }
```

* `@Override`. This informs the compiler that the element is meant to override an element declared in superclass. While it is not required to use this annotation when overriding a method, it helps to prevent errors. If a method marked with `@Override` fails to correclty override a method in one of its superclasses, the compiler generates an error.

* `@SupressWarnings`. This tells the compiler to suppress specific warnings that it would otherwise generate. For instance,
```java
// use a deprecated method and tell 
   // compiler not to generate a warning
   @SuppressWarnings("deprecation")
    void useDeprecatedMethod() {
        // deprecation warning
        // - suppressed
        objectOne.deprecatedMethod();
    }
```
Every compiler warning belongs to a category. The Java language specification lists two categories: `deprecation` and `unchecked`. Unchecked warnings occur when interfacing with legacy code written before the advent of generics.
* `@SafeVarargs` . When applied to a method or constructor, this asserts that the code does not perform potentially unsafe operations on its `varargs` parameter. When this annotation is used, unchecked warnings related to `varargs` are suppressed.
* `@FunctionalInterface`. Introduced in Java 8, this indicates that the type declaration is intended to be a functional interface.

#### Annotations that Apply to Other Annotations
Annotations that apply to other annotations are called meta-annotations. There are several meta-annotations defined in `java.lang.annotation`.

* `@Retention`. This specifies how the marked annotation is stored. 
   - `RetentionPolicy.SOURCE`. The marked annotation is retained only in the source level and is ignored by the compiler.
   - `RetentionPolicy.CLASS`. The marked annotation is retained by the compiler at compile time, but is ignored by JVM.
   - `RetentionPolicy.RUNTIME`. The marked annotation is retained by the JVM so it can be used by the runtime environment.
* `@Documented`. This indicates that whenever the specified annotation is used, those elements should be documented using the Javadoc tool (By default, annotations are not inclueded in the Javadoc). 
* `@Target`. This annotation marks another annotation to restrict what kind of Java elements the annotation can be applied to. A target annotation specifies one of the ff. element.
   - `ElementType.ANNOTATION_TYPE`. This can be applied to an annotation type.
   - `ElementType.CONSTRUCTOR`. This can be applied to a constructor.
   - `ElementType.FIELD`. This can be applied to a field or property.
   - `ElementType.LOCAL_VARIABLE`. This can be applied to a local variable.
   - `ElementType.METHOD`. This can be applied to a method level annotation.
   - `ElementType.PACKAGE`. This can be applied to a package declaration.
   - `ElementType.PARAMETER`. THis can be applied to the parameters of a method.
   - `ElementType.TYPE`. This can be applied to any element of a class.

* `@Inherited`. This indicates that the annotation type can be inherited from the superclass (not true by default). When the user queries the annotation type and the class has no annotation for this type, the class' superclass is queried for the annotation type. This can only be applied to class declarations.
* `@Repeatable`. Introduced in Java 8, this indicates that the marked annotation can be applied more than once to the same declaration or type use. 

### 📌 Type Annotations and Pluggable Type Systems
Before Java 8, annotations can only be applied to declarations. After Java 8's release, annotations can also be applied to any **type use**. This meant that annotations can be used anywhere where type is used., e.g. instance creation expressions _`(new)`_, casts, `implements` clauses and `throws` clauses. This form of annotation is called `type annotation`. 

Type Annotations were created to support improved analysis of Java programs way of ensuring stronger type checking. The Java SE 8 release does not provide a type checking framework, but it allows developers to write (or download) a type checking framework that is implemented as one or more **pluggable modules** that are used in conjunction with the compiler.

For instance, a custom plug-in check can be used to ensure that a certain variable is never assigned `null`.
```java
@NonNull String str;
```
When this code is compiled including the `NonNull` module, the compiler prints a warning if it detects a potential problem, allowing developers to modify the code to avoid the error. After the code is corrected, this particular error will not occur when the program runs.

With the judicious use of type annotations and presence of pluggable type checkers, the code can be stronger and less prone to error.

There are a lot of existing libraries for type checking modules. For example the Checker Framework created by University of Washington. This framework includes a NonNull module, as well as regular expression module and a mutex lock module. See [this](https://checkerframework.org/) for more information.

### 📌 Repeating Annotations
