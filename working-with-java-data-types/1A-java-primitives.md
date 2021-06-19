### 1A. Use primitives and wrapper classes, including, operators, parentheses, type promotion and casting
---

#### 📌 Java Primitives
|Type| Description | Min Value | Max Value | 
|:---|:-----------|:---------|:----------|
|byte | 8-bit signed 2's complement | -2<sup>7</sup>| 2<sup>7</sup> - 1|
|short|16-bit signed 2's complement | -2<sup>15</sup>|2<sup>15</sup> - 1|
|int| 32-bit signed 2's complement | signed: -2<sup>31</sup><br/>unsigned: 0 |signed:  2<sup>31</sup> - 1<br /> unsigned: 2<sup>32</sup> - 1|
|long|64-bit 2's complement| signed: -2<sup>63</sup> <br /> unsigned: 0| signed: 2<sup>63</sup> - 1 <br/> unsigned: 2<sup>64</sup> - 1|
|float|32-bit IEEE 754 floating point|---| --- |
|double|64-bit IEEE 754 floating point|---|---|
|boolean| `true` or `false` | N/A | N/A |
| char |single 16-bit Unicode character| '\u0000' (0)| `\uffff` (65535)| 

In addition to the eight types above, Java also provides special support for `java.lang.String`. String objects are immutable. It is technically not a primitive.

**WARNING**: Do not use float and double for precise values, such as currency. Use `java.math.BigDecimal` class instead.


#### 📌 Java `default` values
Primitives, if uninitialized gets default values. Final and local variables should always be initialized too. The following table lists the default values in Java.
| Type | Default Value |
|:-----| :------------|
| byte | 0 |
| char | '\u0000' |
| short | 0 |
| int | 0 |
| long | 0L |
| float | 0f |
| double | 0d |
| Object | null |
|boolean | false |

#### 📌 Java Literals
1. A **literal** is a source code representation of a fixed value. They can be represented without requiring computation. 
2. An integer literal is of type `Long` if it ends withe letter `L`, e.g. `1L`.
3. The prefix `0x` indicates hexadecimal.
4. The prefix `0b` indicates binary
5. A floating point literal is of type `float` if it ends with `f` or `F`. Otherwise, it defaults to a `double`.
6. There is also a special kind of literal called a `class` literal, e.g. `String.class`. It refers to the class object of the object/primitive. 

```java
int decimalValue = 26;
int hexaValue = 0x1A;
int binaryValue = 0b11010;

double d1 = 123.4;
// same value as d1, but in scientific notation
double d2 = 1.234e2;
float f1  = 123.4f;
```

#### 📌 Underscore Character in Numeric Literals
In Java 7 and later versions, an underscore can be placed in between digits of a numerical literal. This improves readability of code.
```java
long creditCardNumber = 1234_5678_9012_3456L;
long socialSecurityNumber = 999_99_9999L;
float pi =  3.14_15F;
long hexBytes = 0xFF_EC_DE_5E;
long hexWords = 0xCAFE_BABE;
long maxLong = 0x7fff_ffff_ffff_ffffL;
byte nybbles = 0b0010_0101;
long bytes = 0b11010010_01101001_10010100_10010010;
```

There are limitations as to where an underscore can be placed. <br/>
 ❌ Beginning or end of a number `int a = _1000_`. <br/>
 ❌ Adjacent to a decimal point in a floating point literal `float f = 1._009` <br/>
 ❌ Prior to an `F` or `L` suffix `long l = 100_L` <br/>
 ❌ Positions where a string of decimals is expected `int x4 = 0_x52`; <br/>

#### 📌 Java Wrapper Classes
Wrapper classes are object representations of primitive data types. They are used to represent primitives when an `Object` is required. Placing primitive types into wrapper classes is called **BOXING**. The reverse, i.e. from wrapper object to primitive is called **UNBOXING**

Performance-wise, primitives are faster than their boxed counterparts. 

The table below shows the primitive types with their `Wrapper` classes.

|Primitive Type | Wrapper Class | Constructor Arguments|
| :------------- |:-------------| :-----|
|`byte` | `Byte` | byte or String |
|`short` | `Short` | short or String |
|`int` | `Integer` | int or String |
|`long` | `Long` | long or String |
|`float` | `Float` | float, double or String |
|`double` | `Double` | double or String |
|`char` | `Character` | char |
|`boolean` | `Boolean` | boolean or String |

#### 📌 Java AutoBoxing/Unboxing

```java
    // Boxing
    Integer i  = new Integer(8);
    
    //Unboxing
    int i2 = i.intValue();
```
**AutoBoxing** . Primitive values, like `int`, `boolean` are converted to associated wrapper `Object`. 

Java 5 introduced autoboxing. Autoboxing/unboxing means automatic conversion of primitives to objects or vice versa, when needed. 
It can happen during _assignments_, _passing parameters to methods_, _returning values from methods_, _variable comparisons_, _arithmetic operations_, and _others_.  
For example,
```java
   /*
   * 10 is a primitive int. It is autoboxed and saved to i of type Integer Object
   */
   Integer i = 10;
   
   // Auto unboxing happens here
   int j = i;
```

**Unboxing**. Converting an object of a wrapper type (`Integer`) to its corresponding primitive(`int`) value is called unboxing. The Java compiler applies unboxing when a object of a wrapper class is
   * Passed as a parameter to a method that expects a value of the corresponding primitive type.
   * Assigned to a variable of the corresponding primitive type.

Autoboxing and unboxing lets developers write cleaner code, making it easier to read.


#### 📌 Object Interning
Object interning is keeping only one copy of every distinct Java object. The object must be immutable. These objects are stored in an **_INTERN POOL_** . In Java, when primitive values are boxed into a wrapper object, the values are interned, and any boxing conversions  of these values are guaranteed to result in the same object. 

There are consequences when comparing wrapper objects using `==` or `.equals`. Remember that `==` operator compares the reference of two objects while `equals` compares values. Thus, from the example below both equality checks would return to true.
```java
Integer a = 5; //automatically boxed and interned
Integer b = 5; // automatically boxed and is already interned

System.out.println(a == b); //true
System.out.println(a.equals(b)); //true
```

#### 📌 Java `null` type
Null values represents a `null` reference, meaning the memory address does not refer to any object. It is the default value of Java reference variables. Primitives cannot be assigned a `null`.

#### 📌 Array Manipulation
Java SE provides methods to perform some of the most common manipulations related to arrays, such as sorting, copying and searching in `Java.util.Arrays` class. 

#### 📌 Type Promotion and Casting
**Typecasting or type conversion** in java is the process of assigning a primitive data type's value to another primitive. It is automatically performed if the data types of the variables are compatible with each other. This is called automatic type conversion. Typecasting can also be applied to a class or an interface. 

##### Types of Casting
1. Primitive Type Casting
    * **Widening casting or implicit conversion** .  Involves casting of a data type with lower value to one with higher value. Thus no loss of information, e.g `integer` to `long`.
    * **Narrowing casting or explicit conversion**. Involves casting of a data type with a higher value  into a data type with lower value. It can lead to loss of information. 
2. Reference Type Casting
    * **Upcasting**. Involves conversion of a subtype to an object of supertype.
    *  **Downcasting**. Involves conversion of supertype to subtype.

---
### Operators
#### 📌 The Unary Operatorss
**Unary Operators** require only one operand.
1. Unary Plus `+`. Indicates positive values, numbers without it are positive by default, e.g. `int i = +1;`.
2. Unary Minus `-`. Negates an expression, e.g. `int i = -2`;
3. Increment `++`. Increments a value by 1
4. Decrement `--`. Decrements a value by 1
5. Logical Complement `!`. Inverts the value of a boolean.

**NOTE** : The increment(`++`) and decrement(`--`) can be applied prefix or postfix. The prefix version evaluates to the incremented value then and there, while the postfix version evaluates to the original value. See this example from the [Java Documentation](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/op1.html) itself.
```java
class PrePostDemo {
    public static void main(String[] args){
        int i = 3;
        i++; // At this point the value of i is 3
        // prints 4
        System.out.println(i); // Then it got post incremented
        ++i;			   // The value of i here is 5 already
        // prints 5
        System.out.println(i); 
        // prints 6
        System.out.println(++i); // The value of i here gots incremented to 6 on the flu
        // prints 6
        System.out.println(i++); // The value of i here is still 6, since it is a postfix
        // prints 7
        System.out.println(i);
    }
}
```

#### 📌 The Conditional Operators
The `&&` and `||` operators performs Conditional-AND and Conditional-OR on two boolean expressions. They exhibit `short-circuiting` which means that the second operand is evaluated only if needed.

#### 📌 The Type Comparison Operator `instanceof`
The `instanceof` operator compares an object to a specified type, whether it is an instance of a class, an instance of a subclass, or an instance of a particular interface. Note that **null is not an instance of anything**.

#### 📌 Bitwise and Bit Shift Operators
* Unary bitwise complement operator `~` = inverts a bit pattern. It can be applied to any of the **integral** types, e.g. `~ 00100011`
* Signed left shift operator `<<` = shifts a bit pattern to the left by a certain number of specified bits. Syntax would be `number << x_places`
* Signed right shift operator `>>` = shifts a bit pattern to the right by a certain number of specified bits. Syntax would be `number >> x_places`. The leftmost position after `>>` depends on the sign extension.
* Unsigned right shift operator `>>>` The vacant leftmost position is filled with 0 instead of the sign bit. 
* Bitwise AND `&`
* Bitwise OR `|`
* Bitwise XOR `^`

#### 📌 Expressions, Statements and Blocks
* The evaluation of an expression can be specified by using parentheses. If an expression is ambiguous because the order is not explicitly indicated, it will be evailuated by the precedence assigned to the operators.
* A statement forms a complete unit of execution, terminated by a semi-colon `;`. 
    * assignment statement
    * increment statement
    * method invocation
    * object creation statement 
* There are 2 kinds of statements, **declaration statements** and  **control-flow statements**. A declaration statement declares a variable. Control flow statements regulate the order in which statements get executed.
* A block is a group of zero or more statements between balanced braces. 


#### ℹ️ Additional Notes :
1. Primitive data types cannot be placed in Java Collections. The primitive values should be boxed first before putting them in a collection.
2. Java **DOES NOT** support operator overloading. When arithmetic operations are performed on wrapper objects, automatic boxing/unboxing is done by the compiler. _[i should think about this 🤔]_


### [REFERENCES]
1. [zetcode](https://zetcode.com/lang/java/datatypes2/)
2. [Java Nuts and Bolts](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/datatypes.html)
