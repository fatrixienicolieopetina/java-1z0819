# Inheritance
The idea of inheritance is simple but powerful: When you want to create a new class and there is already a class that includes some of the code that you want, you can derive your new class from the existing class. In doing this, you can reuse the fields and methods of the existing class without having to write them yourself.

1. A class that is derived from another class is called a _subclass_ (also a derived class, extended class, or child class). The class from which the subclass is derived is called a _superclass_ (also a base class or a parent class).
2. Excepting `Object`, which has no superclass, every class has one and only one direct superclass (single inheritance). In the absence of any other explicit superclass, every class is implicitly a subclass of Object.
3. Classes can be derived from classes that are derived from classes that are derived from classes, and so on, and ultimately derived from the topmost class, `Object`. Such a class is said to be descended from all the classes in the inheritance chain stretching back to `Object`.

### What Can Be Done in a Subclass
A subclass **inherits all of the public and protected members of its parent, no matter what package the subclass is in**. If the subclass is in the same package as its parent, it also inherits the package-private members of the parent. 

1. The inherited fields can be used directly, just like any other fields.
2. HIde a field in the superclass by declaring a field in the subclass with the same name as the one in the superclass, thus hiding it (not recommended).
3. Declare new fields in the subclass that are not in the superclass.
4. Use the inherited methods directly as they are.
5. Write a new instance method in the subclass that has the same signature as the one in the superclass, thus overriding it.
6. Write a new static method in the subclass that has the same signature as the one in the superclass, thus hiding it.
7. Declare new methods in the subclass that are not in the superclass.
8. Write a subclass constructor that invokes the constructor of the superclass, either implicitly or by using the keyword super.
