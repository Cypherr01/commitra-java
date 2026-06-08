## What Is This?
Operators are a fundamental concept in programming that enable you to perform various operations on variables and values, such as arithmetic, comparison, and logical operations. A real-world analogy for operators is a calculator, where you use buttons like "+" and "-" to perform calculations on numbers.

## How It Works Internally
### Arithmetic Operators
Arithmetic operators are used to perform mathematical operations like addition, subtraction, multiplication, and division. For example, `+` is used for addition, `-` for subtraction, `*` for multiplication, and `/` for division.
```text
# Define two numbers
num1 = 5
num2 = 3

# Perform arithmetic operations
addition = num1 + num2  # addition
subtraction = num1 - num2  # subtraction
multiplication = num1 * num2  # multiplication
division = num1 / num2  # division
```
### Integer Division
Integer division is a type of division where the result is an integer, not a decimal. For example, `7 / 2` would result in `3`, not `3.5`.
```text
# Define two numbers
num1 = 7
num2 = 2

# Perform integer division
result = num1 / num2  # result is 3
```
### Modulo Operator
The modulo operator, denoted by `%`, is used to find the remainder of a division operation. For example, `7 % 2` would result in `1`.
```text
# Define two numbers
num1 = 7
num2 = 2

# Perform modulo operation
result = num1 % num2  # result is 1
```
### Pre/Post Increment and Decrement Operators
Pre-increment operators, such as `++i`, increment a variable before using its value, while post-increment operators, such as `i++`, increment a variable after using its value. Similarly, pre-decrement operators, such as `--i`, decrement a variable before using its value, while post-decrement operators, such as `i--`, decrement a variable after using its value.
```text
# Define a variable
i = 5

# Perform pre-increment operation
result = ++i  # result is 6, i is 6

# Perform post-increment operation
result = i++  # result is 6, i is 7
```
### Compound Assignment Operators
Compound assignment operators, such as `+=`, `-=`, `*=`, `/=`, and `%=` , are used to perform arithmetic operations and assign the result to a variable.
```text
# Define a variable
i = 5

# Perform compound assignment operation
i += 3  # i is 8
```
### Relational Operators
Relational operators, such as `==`, `!=`, `>`, `<`, `>=` , and `<=`, are used to compare two values.
```text
# Define two numbers
num1 = 5
num2 = 3

# Perform relational operations
result = num1 == num2  # result is false
result = num1 != num2  # result is true
result = num1 > num2  # result is true
```
### Equality Operator on Primitives and Objects
The equality operator, `==`, compares the values of primitive types, but compares the references of object types.
```text
# Define two primitive numbers
num1 = 5
num2 = 5

# Perform equality operation on primitives
result = num1 == num2  # result is true

# Define two object strings
str1 = "hello"
str2 = "hello"

# Perform equality operation on objects
result = str1 == str2  # result is true due to string pool
```
### .equals() Method
The `.equals()` method is used to compare the values of objects.
```text
# Define two object strings
str1 = new String("hello")
str2 = new String("hello")

# Perform equality operation on objects using .equals() method
result = str1.equals(str2)  # result is true
```
### Logical Operators
Logical operators, such as `&&`, `||`, and `!`, are used to perform logical operations.
```text
# Define two boolean variables
bool1 = true
bool2 = false

# Perform logical operations
result = bool1 && bool2  # result is false
result = bool1 || bool2  # result is true
result = !bool1  # result is false
```
### Bitwise Operators
Bitwise operators, such as `&`, `|`, `^`, `~`, `<<`, `>>`, and `>>>`, are used to perform bitwise operations.
```text
# Define two numbers
num1 = 5
num2 = 3

# Perform bitwise operations
result = num1 & num2  # result is 1
result = num1 | num2  # result is 7
result = num1 ^ num2  # result is 6
```
### Ternary Operator
The ternary operator, `condition ? valueIfTrue : valueIfFalse`, is used to perform conditional operations.
```text
# Define a boolean variable
bool1 = true

# Perform ternary operation
result = bool1 ? 5 : 3  # result is 5
```
### instanceof Operator
The `instanceof` operator is used to check if an object is an instance of a class.
```text
# Define an object
obj = "hello"

# Perform instanceof operation
result = obj instanceof String  # result is true
```
### Operator Precedence
Operator precedence determines the order in which operators are evaluated.
```text
# Define two numbers
num1 = 5
num2 = 3

# Perform operation with multiple operators
result = num1 + num2 * 2  # result is 11
```
CORE INSIGHT: Operators are a fundamental concept in programming that enable you to perform various operations on variables and values, and understanding operator precedence is crucial to writing correct code.

## Syntax and Structure
```java
public class OperatorExample {
    public static void main(String[] args) {
        // Define two numbers
        int num1 = 5;
        int num2 = 3;

        // Perform arithmetic operations
        int addition = num1 + num2;  // addition
        int subtraction = num1 - num2;  // subtraction
        int multiplication = num1 * num2;  // multiplication
        int division = num1 / num2;  // division

        // Perform relational operations
        boolean result = num1 == num2;  // result is false
        result = num1 != num2;  // result is true
        result = num1 > num2;  // result is true

        // Perform logical operations
        boolean bool1 = true;
        boolean bool2 = false;
        result = bool1 && bool2;  // result is false
        result = bool1 || bool2;  // result is true
        result = !bool1;  // result is false

        // Print results
        System.out.println("Addition: " + addition);
        System.out.println("Subtraction: " + subtraction);
        System.out.println("Multiplication: " + multiplication);
        System.out.println("Division: " + division);
        System.out.println("Result: " + result);
    }
}
```
## Practical Example
```java
public class Calculator {
    public static void main(String[] args) {
        // Define two numbers
        int num1 = 5;
        int num2 = 3;

        // Perform arithmetic operations
        int addition = num1 + num2;  // addition
        int subtraction = num1 - num2;  // subtraction
        int multiplication = num1 * num2;  // multiplication
        int division = num1 / num2;  // division

        // Print results
        System.out.println("Addition: " + addition);
        System.out.println("Subtraction: " + subtraction);
        System.out.println("Multiplication: " + multiplication);
        System.out.println("Division: " + division);
    }
}
```
## How This Connects to the Project
Before learning about operators, the Personal Finance Manager project would not be able to perform calculations, such as adding and subtracting expenses. After learning about operators, the project can now perform these calculations, making it more functional. The `Calculator` class in the project uses operators to perform arithmetic operations. One real company that uses this exact pattern is Intuit, which uses operators to perform calculations in their financial software. This matters to you because without operators, your project would not be able to perform calculations, making it less useful.

## Common Mistakes Beginners Make
**Most common mistake:** Using the `==` operator to compare objects instead of the `.equals()` method.
Wrong idea: Using `==` to compare objects is sufficient.
Correct idea: Using `.equals()` to compare objects is necessary.
**Looks right but is silently wrong:** Using the `=` operator instead of the `==` operator for comparison.
```java
int num1 = 5;
int num2 = 3;
if (num1 = num2) {  // This will always be true
    System.out.println("Numbers are equal");
}
```
**Seems optional but critical at scale:** Not using parentheses to clarify operator precedence.
**Missed config or flag:** Not using the `strict` mode in JavaScript to prevent implicit type conversions.
**Interview question:** What is the difference between the `==` operator and the `.equals()` method?

## Verification Task 1
Your system shows incorrect results for arithmetic operations. You have a `Calculator` class that uses operators to perform calculations. Diagnose and fix the issue.

## Solution 1
The issue is due to the incorrect use of operator precedence. The `Calculator` class is using the `+` operator before the `*` operator, which is causing the incorrect results. To fix this, we need to use parentheses to clarify the operator precedence.

## Verification Task 2
You are building a `Calculator` class that uses operators to perform calculations. Should you use the `==` operator or the `.equals()` method to compare objects?

## Solution 2
You should use the `.equals()` method to compare objects. The `==` operator compares the references of objects, not their values.

## Verification Task 3
You have a `Calculator` class that uses operators to perform calculations. The following code snippet has a subtle bug:
```java
public class Calculator {
    public static void main(String[] args) {
        int num1 = 5;
        int num2 = 3;
        int result = num1 + num2 * 2;
        System.out.println("Result: " + result);
    }
}
```
Find and fix the bug.

## Solution 3
The bug is due to the incorrect use of operator precedence. The `*` operator has higher precedence than the `+` operator, so the expression `num2 * 2` is evaluated first. To fix this, we need to use parentheses to clarify the operator precedence:
```java
public class Calculator {
    public static void main(String[] args) {
        int num1 = 5;
        int num2 = 3;
        int result = (num1 + num2) * 2;
        System.out.println("Result: " + result);
    }
}
```
## What Comes Next
The next topic is Arrays. This topic follows logically from Operators because arrays are a fundamental data structure in programming that rely heavily on operators to perform calculations and comparisons. In the next topic, we will learn how to use operators to perform calculations on arrays.

## Reference Summary
Operators are a fundamental concept in programming that enable you to perform various operations on variables and values. Understanding operator precedence is crucial to writing correct code. The most common production mistake is using the `==` operator to compare objects instead of the `.equals()` method. In the Personal Finance Manager project, operators are used to perform calculations, such as adding and subtracting expenses. One real company that uses this exact pattern is Intuit, which uses operators to perform calculations in their financial software. This matters to you because without operators, your project would not be able to perform calculations, making it less useful.