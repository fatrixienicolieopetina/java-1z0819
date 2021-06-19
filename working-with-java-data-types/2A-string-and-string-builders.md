### Handle text using String and StringBuilder classes

#### 📌 Strings
1. The String class has 13 constructors that allows you to provide the initial value of the string using different sources.
2. The String class is immutable. The String class provides a number of method that seemingly modifies the string object. However, what it really does is create a new String as a result of the operation.
3. `Charsequence` is an interface that is implemented by the `String` class. Therefore, a string can be used as an argument for `contains`.

#### 📌 Converting between Numbers and Strings
1. The `Number` subclasses (`Byte`, `Integer`, `Double`, etc) provides a class method `valueOf` that converts a string to an object of that type.
2. Each of the `Number` subclass also provides a `parseXXX` method that converts string to their primitive counterparts.

#### 📌 The StringBuilder class
1. `StringBuilder` objects are like `String` objects, except that they can be modified. Internallly, they are treated as **variable-length** arrays that contain a sequence of characters.
2. Strings should always be used unless string builders offer an advantage in code. 
3. StringBuilders also have a capacity, the number of character spaces that have been allocated. The **`capacity`** is always greater than or equal to its length, which will automatically expand as necessary to accommodate additions to the string builder.
4. One notable StringBuilder constructor is `StringBuilder(CharSequence cs)` and `StringBuilder(String s)`. It constructs a string builder containing the same characters as the specified `CharSequence` or `String`, plus an extra 16 empty elements trailing the `CharSequence` or `String`.
5. The default capacity of a `StringBuilder` is 16, 16 empty elements.
6. The principal operations on a `StringBuilder` that are not available in `String` are the `append` and `insert` methods, which are overloaded to accept data of any type.
7. Any `String` method can be used on a `StringBuilder` object by first converting the string builder to a string via the `toString` method.
8. There is also a `StringBuffer` class that is exactly the same as the `StringBuilder` class except that it is thread safe.
