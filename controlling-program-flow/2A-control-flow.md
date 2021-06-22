# Control Flow Statements
Control flow consists of decision-making statements (`if-else`, `switch`), looping statements(`for`, `while`) and branching statements (`break`, `return`).

### 📌 `uf-else`
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
//TODO
