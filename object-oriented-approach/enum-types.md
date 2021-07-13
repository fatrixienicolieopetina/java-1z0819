# Enum Types
1. An enum is a special data type that enables a variable to be a set of predefined constants. The variable must be equal to one of the values that have been predefined for it. 
2. Because they are contants, the names of an enum type's field are in uppercase letters.
```java
public enum Day {
    SUNDAY, MONDAY, TUESDAY, WEDNESDAY,
    THURSDAY, FRIDAY, SATURDAY 
}
```
3. Enums should be used any time it is needed to represent a fixed set of constants, i.e. datasets where all possible values are known.
4. The `enum` declaration defines a class (called an `enum` type). The `enum` class body can include methods and other fields. The compiler automatically adds some special methods when it creates an enum. 
5. Enums have static `values` method that returns an array containing all of the values of the enum in the order they are declared. 
6. **NOTE:** All enums explicity extend `java.lang.Enum`. Since classes in Java only allows one superclass, enums cannot extend anything else. 
7. **NOTE:** The constructor for an enum type must be package-private or private access. It automatically creates the constants that are defined at the beginning of the enum body.
