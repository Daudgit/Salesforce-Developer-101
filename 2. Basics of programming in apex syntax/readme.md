
# Apex Programming Basics

Apex is a powerful programming language that allows you to customize and extend Salesforce applications. Whether you're new to programming or new to Apex, this guide will help you understand the fundamental concepts and syntax.

## 1. Variables

Variables are used to store data in Apex. In Apex, variables are declared using a specific data type, such as `String`, `Integer`, or custom objects.

```apex
String myString = 'Hello, World!';
Integer myNumber = 42;
```

## 2. Operators

Operators are used to perform operations on variables and values. Apex supports a variety of operators, including arithmetic, comparison, and logical operators.

```apex
Integer a = 5;
Integer b = 3;
Integer result = a + b; // result will be 8
```

## 3. Expressions

Expressions are combinations of variables, values, and operators that produce a result. They are the building blocks of any program.

```apex
Boolean isTrue = (a > b); // isTrue will be true
```

## 4. Looping Statement

Looping statements allow you to execute a block of code repeatedly. The `for` and `while` loops are commonly used in Apex.

```apex
for (Integer i = 0; i < 5; i++) {
    // Code to be repeated
}
```

## 5. Controlling Statement

Control statements determine the flow of your program. Apex provides conditional statements like `if`, `else`, and `switch` for decision-making.

```apex
if (a > b) {
    // Code to execute if the condition is true
} else {
    // Code to execute if the condition is false
}
```

## 6. Apex Class

In Apex, you can define custom classes that encapsulate data and methods. Classes are the building blocks of object-oriented programming.

```apex
public class MyClass {
    // Class members and methods
}
```

## 7. Objects

In Salesforce, objects represent entities like Accounts, Contacts, and Custom Objects. You can interact with objects and their data using Apex.

```apex
Account acc = new Account();
acc.Name = 'Acme Inc.';
insert acc; // Create a new Account record
```

## 8. Functions

Functions (or methods) are blocks of code that can be called to perform specific tasks. They can accept parameters and return values.

```apex
public Integer addNumbers(Integer num1, Integer num2) {
    return num1 + num2;
}
```

These are the foundational concepts of programming in Apex. As you progress, you'll delve deeper into object-oriented programming, database operations, and more advanced features. Happy coding!
