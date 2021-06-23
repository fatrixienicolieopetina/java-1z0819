# Control Flow Statements
Control flow consists of decision-making statements (`if-else`, `switch`), looping statements(`for`, `while`) and branching statements (`break`, `return`).

### 📌 `if-else`
1. Most basic

### 📌 `switch`
1. Can have a number of possible execution paths
2. **IMPORTANT IMPORTANT** Can work with `byte`, `short`, `char` and `int` primitive data types.
3. Can work with enumerated data types, `String` class and a few special classes that wrap certain primitive types: `Character`, `Byte`, `Short` and `Integer`.
4. The `switch` statement evaluates its expression then executes all statements that follow the matching case label.
5. `break` statements are necessary because without them, the switch blocks fall through. All statements after the matching case label are executed in sequence, regardless of the expression of the subsequent case labels, until a break statement is encountered.
6. In Java 7 and later, strings can be used as case expression. The string in the switch expression is compared to the case labels using String.equals.

### 📌 `while` and `do-while` 
1. The difference between `do-while` and `while` is that `do-while` evaluates its expression at the bottom of the loop instead of the top. Therefore, the statements within the do block are always executed at least once.

### 📌 `for`
1. The initialization expression initializes the loop; it's executed once, as the loop begins.
2. When the termination expression evaluates to false, the loop terminates.
3. The increment expression is invoked after each iteration through the loop; it is perfectly acceptable for this expression to increment or decrement a value.
4. The three expressions of the for loop are optional; an infinite loop can be created as follows:

```java
for( ; ; ) {
    //code goes here
}
```
5. The enhanced for loop is designed for iterations.

### 📌 Branching Statements
#### `break`
* The break statement has two forms: labeled and unlabeled. 
* **An unlabeled `break` statement terminates the innermost `switch`, `for`, `while` or `do-while` statement, but a labeled break terminates an outer statement**.
* The `break` statement terminates the labeled statement; it does not transfer the flow of control to the label. Control flow is transferred to the statement immediately following the labeled (terminated) statement.

#### `continue`
* The `continue` statement skips the current iteration of a `for`, `while`, `do-while` loop. 
* The unlabeled form skips the the end of the innermost loop's body and evaluates the `boolean` expression that controls the loop.
* A labeled `continue` statement skips the current iteraton of an outer loop marked with the given label. 

#### `return`
* The return statement exits from the current method and control flow returns to where the method was invoked. 
* It has two forms: one that returns a value and one that does not.
* The data type of the returned value must match the type of the method's declared return value. 

### [REFERENCES]
[1] [Java Doc, Control FLow Statements](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/flow.html)
