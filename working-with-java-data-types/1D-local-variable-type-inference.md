# Use local variable type inference, including as lambda parameters

### 📌 Local Variable Type Inference
Java 10 introduced type inference for local variables. Before, all local variable declarations required an explicit type on the left hand side. **With type inference, the explicit type can be replaced by the reserved type name `var` for local variable declarations that have initializers**. The type of the the variable is inferred from the type of the initializer.

#### Guidelines:
1. Choose variable names that provide useful information.
2. Minimize the scope of local variables. 
3. Consider a `var` when the initializer provides sufficient information to the reader.
4. Particular care should be taken when the initializer is a numeric value, especially an integer literal. With an explicit type on the left-hand side, the numeric value may be silently widened or narrowed to types other that int. With `var`, the value will be inferred as an `int` which may be unintended.

#### Notes
1. `var` cannot be used for fields, method parameters, and method return types
2. An initializer is required on the right-hand side of `var`.
3. `var` cannot be used with `null`.
4. Use `var` with diamond on the right hand side with caution, e.g. `var list = new ArrayList<>()`. This will infer the type of list to be `ArrayList<Object>`. In general, it is preferable to use an explicit type on the left with diamond on the right, or use var on the left with an explicit type on the right.

#### Legal Lambda Expression Type Inference Usage
1. Enables you to add annotations to lambda parameters, e.g `(@NonNull var s) -> s.toLowerCase()`

### 📌 Local variable for Lambda Parameters
Example: `(var s1, var s2) -> s1 + s2`
Java 10 did not support the above feature. Java 11 addressed this and allowed this syntax.

#### Limitations of using `var` in lambda
1. We cannot use `var` for some parameters and skip for others, e.g. `(var s1, s2) -> s1 + s2`
2. We cannot mix `var` with explicit types e.g. `(var s1, String s2) -> s1 + s2`
3. Even though the parentheses can be skipped in a single parameter lambda, that can't be done when the `var` keyword is used, e.g. `var s1 -> s1.toUpperCase()`

### [REFERENCES]
[1] [Local Type Inference](https://openjdk.java.net/projects/amber/LVTIstyle.html)
