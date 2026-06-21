## What Is This?
Generics are a feature of the Java programming language that allows for the creation of reusable and type-safe code. Think of generics like a container that can hold different types of objects, but still maintains its structure and functionality, much like a toolbox that can hold various tools, but still serves the same purpose of organizing and protecting its contents.

## How It Works Internally
### Introduction to Generics
Generics are used to parameterize types for type safety and reusability. This means that a class, interface, or method can be defined with a type parameter, which can be replaced with a specific type when the class, interface, or method is used.

### Generic Class
A generic class is a class that has a type parameter. For example, a `Box` class can be defined with a type parameter `T`, which represents the type of object that the box can hold.
```text
# Define a generic class Box with a type parameter T
class Box {
  # The box has a value of type T
  private T value

  # Constructor to initialize the value
  public Box(T value) {
    # Set the value of the box
    this.value = value
  }

  # Method to get the value
  public T getValue() {
    # Return the value of the box
    return this.value
  }
}
```
### Generic Method
A generic method is a method that has a type parameter. For example, an `identity` method can be defined with a type parameter `T`, which represents the type of object that the method can return.
```text
# Define a generic method identity with a type parameter T
public <T> T identity(T value) {
  # Return the value
  return value
}
```
### Type Parameters
Type parameters are used to define the types that can be used with a generic class or method. Common type parameters include `T` (Type), `E` (Element), `K` (Key), `V` (Value), and `N` (Number).

### Multiple Type Parameters
Multiple type parameters can be used to define a generic class or method that works with multiple types. For example, a `Map` interface can be defined with two type parameters `K` and `V`, which represent the types of the keys and values in the map.
```text
# Define a generic interface Map with two type parameters K and V
interface Map<K, V> {
  # Method to get the value for a given key
  V get(K key)
}
```
### Bounded Type Parameters
Bounded type parameters are used to restrict the types that can be used with a generic class or method. For example, a `NumberBox` class can be defined with a type parameter `T` that is bounded by the `Number` class.
```text
# Define a generic class NumberBox with a bounded type parameter T
class NumberBox<T extends Number> {
  # The box has a value of type T
  private T value

  # Constructor to initialize the value
  public NumberBox(T value) {
    # Set the value of the box
    this.value = value
  }

  # Method to get the value
  public T getValue() {
    # Return the value of the box
    return this.value
  }
}
```
### Wildcards
Wildcards are used to represent unknown types in a generic class or method. For example, a `List` interface can be defined with a wildcard type parameter `?`, which represents an unknown type.
```text
# Define a generic interface List with a wildcard type parameter ?
interface List<?> {
  # Method to get the size of the list
  int size()
}
```
### Type Erasure
Type erasure is the process of removing the type parameters from a generic class or method at compile-time. This means that the type parameters are not available at runtime.

### Raw Types
Raw types are generic classes or interfaces that are used without type parameters. For example, a `List` interface can be used as a raw type `List`, which is equivalent to `List<Object>`.
```text
# Define a raw type List
List list = new ArrayList()
```
### Generic Interfaces
Generic interfaces are interfaces that have type parameters. For example, a `Comparable` interface can be defined with a type parameter `T`, which represents the type of object that can be compared.
```text
# Define a generic interface Comparable with a type parameter T
interface Comparable<T> {
  # Method to compare two objects
  int compareTo(T o)
}
```
CORE INSIGHT: Generics provide a way to define reusable and type-safe code, but they can be complex and require careful consideration of type parameters, bounded type parameters, and wildcards.

## Syntax and Structure
```java
// Define a generic class Box with a type parameter T
public class Box<T> {
  // The box has a value of type T
  private T value;

  // Constructor to initialize the value
  public Box(T value) {
    // Set the value of the box
    this.value = value;
  }

  // Method to get the value
  public T getValue() {
    // Return the value of the box
    return this.value;
  }
}
```

## Practical Example
```java
// Define a generic class NumberBox with a bounded type parameter T
public class NumberBox<T extends Number> {
  // The box has a value of type T
  private T value;

  // Constructor to initialize the value
  public NumberBox(T value) {
    // Set the value of the box
    this.value = value;
  }

  // Method to get the value
  public T getValue() {
    // Return the value of the box
    return this.value;
  }

  public static void main(String[] args) {
    // Create a NumberBox with an Integer value
    NumberBox<Integer> intBox = new NumberBox<>(10);
    System.out.println(intBox.getValue());

    // Create a NumberBox with a Double value
    NumberBox<Double> doubleBox = new NumberBox<>(10.5);
    System.out.println(doubleBox.getValue());
  }
}
```

## How This Connects to the Project
BEFORE: Without generics, the Personal Finance Manager project would have to use raw types or casting to work with different types of financial data, which could lead to type safety issues and bugs.
AFTER: With generics, the project can define reusable and type-safe classes and methods to work with different types of financial data, such as `Transaction` and `Account`.
The `Transaction` class can be defined with a type parameter `T`, which represents the type of transaction (e.g. deposit, withdrawal).
The `Account` class can be defined with a type parameter `T`, which represents the type of account (e.g. checking, savings).
One real company that uses this exact pattern is Intuit, which uses generics to define reusable and type-safe classes and methods in their financial software products.

## Common Mistakes Beginners Make
**Wrong idea:** Generics are only used for collections and lists.
**Correct idea:** Generics can be used for any type of class or method that needs to work with different types of data.
Wrong idea: Generics are only useful for complex data structures.
Correct idea: Generics can be useful for simple data structures as well, such as a `Box` class that can hold any type of object.
**Most common mistake:** Forgetting to specify the type parameter when using a generic class or method.
**Looks right but is silently wrong:** Using a raw type instead of a parameterized type.
**Seems optional but critical at scale:** Using bounded type parameters to restrict the types that can be used with a generic class or method.
**Missed config or flag:** Forgetting to use the `extends` keyword when defining a bounded type parameter.
**Interview question:** How would you implement a generic `Stack` class that can work with any type of data?

## Verification Tasks
## Verification Task 1
Your system shows a `ClassCastException` when trying to retrieve a value from a `Map`. You have a `Map` defined with a raw type `Map`, and you are trying to retrieve a value from it using a `String` key. Diagnose and fix the issue.
## Solution 1
The issue is that the `Map` is defined with a raw type, which means that it can hold any type of object. To fix the issue, you need to define the `Map` with a parameterized type, such as `Map<String, Integer>`. This will ensure that the `Map` can only hold `String` keys and `Integer` values.

## Verification Task 2
You are building a `Transaction` class that needs to work with different types of transactions (e.g. deposit, withdrawal). You need to decide whether to use a generic class or a non-generic class. Defend your decision using the concepts learned in this topic.
## Solution 2
I would decide to use a generic class for the `Transaction` class. This is because the `Transaction` class needs to work with different types of transactions, and using a generic class will allow me to define a reusable and type-safe class that can work with any type of transaction. I can define the `Transaction` class with a type parameter `T`, which represents the type of transaction. This will allow me to create `Transaction` objects that can hold any type of transaction data.

## Verification Task 3
You are reviewing a code snippet that uses a generic `List` interface. The code snippet is as follows:
```java
List list = new ArrayList();
list.add("hello");
list.add(10);
```
Find and fix the bug in the code snippet.
## Solution 3
The bug in the code snippet is that it is using a raw type `List` instead of a parameterized type. This can lead to type safety issues and bugs. To fix the bug, you need to define the `List` with a parameterized type, such as `List<String>`. This will ensure that the `List` can only hold `String` objects.

## What Comes Next
The next topic in the roadmap is JDBC — Java Database Connectivity. This topic follows logically from the current topic because generics are used extensively in JDBC to define reusable and type-safe classes and methods that work with different types of database data. For example, the `ResultSet` interface is a generic interface that can be used to retrieve data from a database.

## Reference Summary
Generics are a feature of the Java programming language that allows for the creation of reusable and type-safe code. Generics are used to parameterize types for type safety and reusability. A generic class is a class that has a type parameter, and a generic method is a method that has a type parameter. Type parameters are used to define the types that can be used with a generic class or method. Bounded type parameters are used to restrict the types that can be used with a generic class or method. Wildcards are used to represent unknown types in a generic class or method. Type erasure is the process of removing the type parameters from a generic class or method at compile-time. Raw types are generic classes or interfaces that are used without type parameters. Generic interfaces are interfaces that have type parameters. The most common production mistake when using generics is forgetting to specify the type parameter when using a generic class or method. This topic connects to the Personal Finance Manager project because generics are used to define reusable and type-safe classes and methods that work with different types of financial data. One real company that uses this exact pattern is Intuit, which uses generics to define reusable and type-safe classes and methods in their financial software products. This matters to you because it allows you to write more robust and maintainable code that can work with different types of data.