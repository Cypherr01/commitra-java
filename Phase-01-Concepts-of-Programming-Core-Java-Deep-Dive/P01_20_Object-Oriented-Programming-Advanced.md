## What Is This?
Object-Oriented Programming — Advanced is a set of concepts that allow developers to create complex, reusable, and maintainable software systems by building on the principles of object-oriented programming. Think of it like a LEGO structure, where each brick represents an object, and the way these bricks are connected and interact with each other determines the overall behavior of the system.

## How It Works Internally
### Inheritance
Inheritance is a mechanism that allows one class to inherit the properties and behavior of another class. This is similar to how a child inherits traits from their parents. The child class, also known as the subclass, inherits all the fields and methods of the parent class, also known as the superclass, and can also add new fields and methods or override the ones inherited from the parent class.

### Polymorphism
Polymorphism is the ability of an object to take on multiple forms. This can be achieved through method overriding or method overloading. Method overriding is when a subclass provides a different implementation of a method that is already defined in its superclass. Method overloading is when multiple methods with the same name can be defined, but with different parameter lists.

### Abstraction
Abstraction is the concept of exposing only the necessary information to the outside world while hiding the implementation details. This is similar to how a car works. You don't need to know how the engine works in order to drive the car. You only need to know how to interact with the car's interface, such as the steering wheel, pedals, and gears.

### Object Class
Every class in Java implicitly extends the Object class, which is the root of the class hierarchy. The Object class provides several methods that are available to all classes, such as toString(), equals(), and hashCode().

### Inner Classes
Inner classes are classes that are defined inside another class. They have access to the members of the outer class and can be used to group related classes together.

## Syntax and Structure
```java
// Define a parent class
public class Animal {
    // Fields
    private String name;

    // Constructor
    public Animal(String name) {
        this.name = name;
    }

    // Method
    public void sound() {
        System.out.println("The animal makes a sound");
    }
}

// Define a child class that inherits from the parent class
public class Dog extends Animal {
    // Constructor
    public Dog(String name) {
        super(name); // Call the parent class constructor
    }

    // Override the sound method
    @Override
    public void sound() {
        System.out.println("The dog barks");
    }
}
```

## Practical Example
```java
// Create an instance of the Dog class
Dog myDog = new Dog("Rex");

// Call the sound method
myDog.sound(); // Output: The dog barks
```

## How This Connects to the Project
Before learning about advanced object-oriented programming concepts, the Personal Finance Manager project would have been limited in its ability to model complex financial relationships. After applying these concepts, the project can now accurately represent real-world financial scenarios, such as inheritance of financial attributes from parent classes to child classes. The `FinancialAccount` class, for example, can be the parent class, and `CheckingAccount` and `SavingsAccount` can be child classes that inherit and extend its behavior. The exact file and function name where this concept lives in the project is `FinancialAccount.java`. A real company that uses this exact pattern is a banking institution, which uses object-oriented programming to model complex financial relationships and transactions.

## Common Mistakes Beginners Make
**Most common mistake**: Incorrectly using inheritance, leading to a rigid and inflexible class hierarchy. 
Wrong idea: Using inheritance to reuse code without considering the "is-a" relationship between classes. 
Correct idea: Use inheritance to model a true "is-a" relationship between classes.

**Looks right but is silently wrong**: Using method overloading without considering the implications of method overriding. 
For example, if a subclass overrides a method with a different return type, it can lead to unexpected behavior.

**Seems optional but critical at scale**: Not using abstraction to hide implementation details, leading to tight coupling between classes. 
As the system grows, this can make it difficult to modify or extend the code without affecting other parts of the system.

**Missed config or flag**: Not using the `@Override` annotation when overriding a method, which can lead to subtle bugs if the method signature changes in the parent class.

**Interview question**: How would you design a class hierarchy to model a university's faculty and staff, including professors, lecturers, and administrators? 
Surface answer: Use inheritance to create a hierarchy of classes, with `Person` as the parent class and `Professor`, `Lecturer`, and `Administrator` as child classes. 
Production answer: Consider using a combination of inheritance and composition to model the complex relationships between faculty and staff, and use abstraction to hide implementation details.

## Verification Task 1
Debug the following code:
```java
public class Animal {
    public void sound() {
        System.out.println("The animal makes a sound");
    }
}

public class Dog extends Animal {
    public void sound() {
        System.out.println("The dog barks");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal myAnimal = new Dog();
        myAnimal.sound(); // Output: The animal makes a sound
    }
}
```
The output is not what we expect. Diagnose and fix the issue.

## Solution 1
The issue is that the `sound()` method in the `Dog` class is not correctly overriding the `sound()` method in the `Animal` class. To fix this, we need to add the `@Override` annotation to the `sound()` method in the `Dog` class.

```java
public class Dog extends Animal {
    @Override
    public void sound() {
        System.out.println("The dog barks");
    }
}
```

## Verification Task 2
Design a class hierarchy to model a bank's account system, including checking and savings accounts. Should we use inheritance or composition to model the relationship between accounts?

## Solution 2
We should use a combination of inheritance and composition to model the relationship between accounts. Inheritance can be used to model the common attributes and methods of all accounts, such as account number and balance. Composition can be used to model the specific features of each type of account, such as overdraft protection for checking accounts.

## Verification Task 3
Code review: Find and fix the bug in the following code:
```java
public class BankAccount {
    private double balance;

    public BankAccount(double balance) {
        this.balance = balance;
    }

    public void deposit(double amount) {
        balance += amount;
    }

    public void withdraw(double amount) {
        balance -= amount;
    }
}
```
The bug is that the `withdraw()` method does not check if the account balance is sufficient before making a withdrawal.

## Solution 3
To fix the bug, we need to add a check to the `withdraw()` method to ensure that the account balance is sufficient before making a withdrawal.
```java
public void withdraw(double amount) {
    if (balance >= amount) {
        balance -= amount;
    } else {
        System.out.println("Insufficient funds");
    }
}
```

## What Comes Next
The next topic is Exception Handling. This topic is a natural follow-up to advanced object-oriented programming because it provides a way to handle errors and exceptions that may occur in complex software systems. The concept of inheritance, which we learned in this topic, will be directly used in exception handling to create a hierarchy of exception classes.

## Reference Summary
Object-Oriented Programming — Advanced is a set of concepts that allows developers to create complex, reusable, and maintainable software systems. It includes inheritance, polymorphism, abstraction, and inner classes. Inheritance allows one class to inherit the properties and behavior of another class. Polymorphism allows objects to take on multiple forms. Abstraction exposes only the necessary information to the outside world while hiding implementation details. Inner classes are classes defined inside another class. The most common mistake beginners make is incorrectly using inheritance. A real company that uses this exact pattern is a banking institution, which uses object-oriented programming to model complex financial relationships and transactions. This topic enables the next topic, Exception Handling, which provides a way to handle errors and exceptions in complex software systems.