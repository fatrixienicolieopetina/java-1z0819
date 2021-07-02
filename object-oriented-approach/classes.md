# Java Classes
In general, class declarations can include these components in order:
1. Modifiers such as public, private and a number of others.
2. The class name, with the initial letter capitalized by conventions
3. The name of hte class's parents (superclass), if any, preceded by the keyword `extends`. A class can only extend (be a subclass) of one parent.
4. A comma-separated list of interfaces implemented by the class, if any, preceded by the keyword implements. A class can implement more than one interface.
5. The class body, surrounded by braces.

```java
public class Sample extends ParentSample implements ExampleInterface {
  // class body
}
```

There are several kinds of variables:
1. Member variables in a class - fields
2. Variables in a method or block of code - local variables
3. Variables in method declarations - parameters

Field declarations are composed of three components, in order:
1. Zero or more modifiers such as `public` or `private`
2. The field's type
3. The field's name

```java
public int fieldName;
```

📌 Access Modifiers
The modifier lets you control what other classes have access to a member field. 
* `public` - the field is accessible from all classes
* `private` - the field is accessible only within its own class

📌 Defining Methods
The only required elements of a method declaration are the **method's return type, name, a pair of parentheses and a body between braces**.

More generally, method declarations have six components, in order:
1. Modifiers - such as public and private
2. The return type - the data type of the value returned by the method or `void` if the method does not return a value.
3. The method name - the rules for field names apply to method names as well
4. The parameter list in parenthesis - a comma-delimited list of input parameters, preceded by their data types
5. An exception list
6. The method body enclosed by braces

**NOTE: Two components of a method declaration comprise the method signature - the method's name and parameter types**

📌 Overloading Methods
1. Java can distinguish between methods with different method signatures. This means that methods within a class can have the same name if they have different parameter lists.
2. Overloaded methods are differentiated by the number and type of the arguments passed into the method.
3. You cannot declare more than one method with the same name and the same number of type of arguments because the compiler cannot tell them apart.
4. The compiler **DOES NOT** consider return type when differentiating methods, so you cannot declare two methods with the same signature even if they have different return type.
5. Overloaded methods should be used sparingly since they can make code much less readable.

### 📌 Returning a Value from a Method
//TODO
