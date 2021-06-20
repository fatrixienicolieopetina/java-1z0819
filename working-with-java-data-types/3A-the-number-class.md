### The Number Classes
1. All of the numeric wrapper classes - `Byte`, `Double`, `Float`, `Integer`, `Short` and `Long` are subclasses of the abstract class `Number`.
2. There are four other `Number` subclasses: `BigDecimal` and `BigInteger` for high-precision calculations. `AtomicInteger` and `AtomicLong` are used for multi-threaded applications.

📌 Three reasons why a `Number` object might be used rather than a primitive
1. As an argument of a method that expects an object
2. To be able to use constants defined by the `Number` class such as `MIN_VALUE` and `MAX_VALUE`, providing the upper and lower bounds of the data type.
3. To use class methods provided by `Number` for converting values to and from primitives, for converting to and from strings, and converting between number systems

📌 Formatting Numeric Print Output
* The `printf` and format methods. The `java.io` package includes a `PrintStream` class that has formatting methods that can be used to replace `print` and `println`. These methods are **`format`** and **`printf`**. Note that `System.out` is a `PrintStream` object, so any `PrintStream` method can be invoked on `System.out`. Syntax would be `System.out.format(...)`.
* Format specifiers begin with a % (percent) sign and end with a converter. A **converter** is a character indicating the type of argument that can be formatted.
 
📌 The `DecimalFormat` Class

The `java.text.DecimalFormat` class is used to control the display of leading an trailing zeros, prefixes and suffixes, grouping separators, and the decimal separator.
The `format` method of `DecimalFormat` is inherited from `NumberFormat`.

  * Pattern Examples
    * `###,###.##` = The pound sign (#) denotes a digit, a comma is a placeholder for the grouping separator and the period is a placeholder for the decimal separator.
    * `000000.00` = The pattern specifies leading and trailing zeros, because the 0 character is used instead of the pound sign.

📌 Beyond Basic Arithmetic
* The `Math`class in the `java.lang` package provides methods and constants for doing more advanced mathematical computations.
The methods in the `Math` class are **all static**, so they can be called directly from the class.

* Constants and Basic Methods
  * The `Math` class includes two constants: `Math.E`, which is the base of natural logarithms and `Math.PI` which is the ratio of the circumference of a circle to its diameter.
  * The `Math` class also includes more than 40 static methods, such as `abs` for absolute value, `round`, `rint`, etc. 

* Trogonometric, Exponential and Logarithmic Methods
    * The `Math` class also includes exponential and logarithmic methods such as `exp`, `log`, `pow` and `sqrt`.
    * It also includes trigonometric methods such as `sin`, `cos`, `tan`.

* Random Numbers
  * The `random` method returns a pseudo-randomly selected number between 0.0 and 1.0. The range includes 0 but not 1. Thus, `0.0 <= Math.random()  < 1.0`. 
  * Using `Math.random` works for generating single random numbers. For a series of random numbers, it is better to create an instance of `java.util.Random` and invoke methods on that object to generate numbers.

📌 Character Class Notes
* The form feed is a page-breaking ASCII control character denoted by `\f`. It forces the printer to eject the current page and to continue printing at the top of another.
* The `Character` class is immutable.



#### REFERENCES
[1] [Beyond Math](https://docs.oracle.com/javase/tutorial/java/data/beyondmath.html)

