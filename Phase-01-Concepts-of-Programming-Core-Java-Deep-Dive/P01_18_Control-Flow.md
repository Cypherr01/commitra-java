## What Is This?
Control flow refers to the order in which a program's code is executed, allowing it to make decisions, repeat actions, and skip over certain sections. Think of it like a recipe for your favorite dish: you need to follow a specific sequence of steps, and sometimes you need to decide whether to add an ingredient or not, or repeat a step several times.

## How It Works Internally
Control flow is the backbone of any programming language, and Java is no exception. Let's break it down into its components.

### Conditional Execution
The `if` statement is used to execute a block of code if a certain condition is true. 
```text
# check a condition
# if true, execute this block of code
# if false, skip to the next line
```
The `else if` statement is used to check another condition if the initial condition is false. 
```text
# check the first condition
# if false, check this condition
# if true, execute this block of code
```
The `else` statement is used to execute a block of code if all previous conditions are false. 
```text
# if all previous conditions are false
# execute this block of code
```

### Nested If Statements
Nested `if` statements are used to check conditions within conditions. 
```text
# check a condition
# if true, check another condition
# if true, execute this block of code
```

### Switch Statement
The `switch` statement is used to execute a block of code based on the value of a variable. 
```text
# check the value of a variable
# execute the corresponding block of code
```
The traditional `switch` statement works on `int`, `char`, `String`, and `enum` types.

### Switch Expression
The `switch` expression, introduced in Java 14, allows for a more concise way of writing `switch` statements. 
```text
# check the value of a variable
# return the corresponding value
```

### For Loop
The `for` loop is used to execute a block of code repeatedly for a specified number of iterations. 
```text
# initialize a counter
# check a condition
# execute this block of code
# update the counter
```

### While Loop
The `while` loop is used to execute a block of code repeatedly while a certain condition is true. 
```text
# check a condition
# execute this block of code
# update the condition
```

### Do-While Loop
The `do-while` loop is used to execute a block of code at least once, and then repeat it while a certain condition is true. 
```text
# execute this block of code
# check a condition
# if true, repeat the block of code
```

### Enhanced For-Each Loop
The enhanced `for-each` loop is used to iterate over any `Iterable` collection. 
```text
# iterate over a collection
# execute this block of code for each element
```

### Break and Continue Statements
The `break` statement is used to exit a loop or `switch` statement. 
```text
# exit the loop or switch statement
```
The `continue` statement is used to skip to the next iteration of a loop. 
```text
# skip to the next iteration
```

### Labeled Break and Continue Statements
Labeled `break` and `continue` statements are used to break out of or continue to a specific loop. 
```text
# label a loop
# break out of or continue to the labeled loop
```

### Ternary Operator
The ternary operator is used to execute a block of code based on a condition. 
```text
# check a condition
# if true, execute this block of code
# if false, execute this block of code
```

### No Goto Statement
Java does not have a `goto` statement, and the `goto` keyword is reserved but not used.

## Syntax and Structure
Here is an example of a `switch` statement in Java:
```java
// declare a variable
int day = 1;

// use a switch statement to print the day of the week
switch (day) {
    // case 1 corresponds to Monday
    case 1:
        System.out.println("Monday");
        break;
    // case 2 corresponds to Tuesday
    case 2:
        System.out.println("Tuesday");
        break;
    // default case corresponds to any other day
    default:
        System.out.println("Unknown day");
        break;
}
```

## Practical Example
Here is an example of a `for` loop in Java:
```java
// declare a variable
int sum = 0;

// use a for loop to calculate the sum of numbers from 1 to 10
for (int i = 1; i <= 10; i++) {
    // add the current number to the sum
    sum += i;
}

// print the sum
System.out.println("The sum is: " + sum);
```

## How This Connects to the Project
Before learning about control flow, the Personal Finance Manager project would not be able to handle different financial scenarios, such as budget overages. 
After learning about control flow, the project can now use `if` statements to check for budget overages and `for` loops to calculate the total expenses. 
The exact file and function name where this concept lives in the project is `BudgetManager.java` and `calculateTotalExpenses()`. 
A real company that uses this exact pattern is Intuit, the maker of TurboTax, which uses control flow statements to handle different tax scenarios and calculate the total tax liability.

## Common Mistakes Beginners Make
**Wrong idea: Using a `switch` statement with a `String` variable that is not defined.**
Correct idea: Always define the variable before using it in a `switch` statement.
**Looks right but is silently wrong: Using a `for` loop with an incorrect loop condition.**
```java
// incorrect loop condition
for (int i = 1; i < 10; i++) {
    // this will only iterate 9 times
}
```
**Seems optional but critical at scale: Not using `break` statements in `switch` cases.**
If not used, the program will execute all the cases after the matched one.
**Missed config or flag: Not checking for `null` values in variables used in control flow statements.**
This can lead to `NullPointerExceptions`.
**Interview question: Write a program that uses a `while` loop to calculate the factorial of a given number.**
Surface answer: Use a `while` loop to multiply the numbers from 1 to the given number.
Production answer: Use a `while` loop with a conditional statement to handle the case where the input number is 0 or negative.

## Verification Task 1
Debug this code: The program is supposed to calculate the sum of numbers from 1 to 10, but it is printing an incorrect result. 
You have the code:
```java
int sum = 0;
for (int i = 1; i < 10; i++) {
    sum += i;
}
System.out.println("The sum is: " + sum);
```
Diagnose and fix the bug.

## Solution 1
The bug is in the loop condition. The loop should iterate from 1 to 10, but the condition `i < 10` will only iterate from 1 to 9. 
To fix the bug, change the loop condition to `i <= 10`.

## Verification Task 2
Design decision: You are building a `BudgetManager` class that needs to calculate the total expenses for a given month. 
Should you use a `for` loop or a `while` loop to iterate over the expenses?
Defend your answer using this topic.

## Solution 2
You should use a `for` loop because you know the exact number of iterations (the number of days in the month), and you can use the loop counter to access the expenses for each day.

## Verification Task 3
Code review: Find and fix the bug in this code:
```java
int sum = 0;
for (int i = 1; i < 10; i++) {
    sum += i;
}
System.out.println("The sum is: " + sum);
if (sum > 10) {
    System.out.println("The sum is greater than 10");
} else {
    System.out.println("The sum is less than or equal to 10");
}
```
The bug is that the code is not handling the case where the sum is exactly 10.

## Solution 3
To fix the bug, change the `else` clause to `else if (sum == 10)` and add a separate `else` clause to handle the case where the sum is less than 10.

## What Comes Next
The next topic is Object-Oriented Programming — Advanced. This topic follows logically from control flow because object-oriented programming builds on the concepts of control flow to create more complex and organized code structures. 
One concrete concept from this topic that will reappear in Object-Oriented Programming — Advanced is the use of `if` statements to check for conditions and make decisions, which is essential for creating conditional logic in object-oriented programs.

## Reference Summary
Control flow is the order in which a program's code is executed, and it is essential for making decisions, repeating actions, and skipping over certain sections. 
The central insight of control flow is that it allows programs to adapt to different situations and make decisions based on conditions. 
A common production mistake is not using `break` statements in `switch` cases, which can lead to unexpected behavior. 
Control flow is connected to the Personal Finance Manager project, where it is used to handle different financial scenarios and calculate the total expenses. 
This concept enables the next topic, Object-Oriented Programming — Advanced, by providing the foundation for creating conditional logic in object-oriented programs. 
In summary, control flow is a fundamental concept in programming that allows programs to make decisions and adapt to different situations, and it is essential for creating complex and organized code structures.