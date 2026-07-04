## What Is This?
Hashing is a fundamental concept in computer science that enables fast and efficient lookup, insertion, and deletion of data in a collection. Imagine a library where each book has a unique identifier, such as an ISBN number, that allows you to quickly locate it on a shelf. In a similar way, hashing maps a key to a specific index in a data structure, allowing for rapid access and retrieval of associated data.

## How It Works Internally
### Introduction to Hash Functions
A hash function is a mathematical function that takes a key as input and generates a hash code, which is an integer that corresponds to a specific index in a data structure. This process is similar to a librarian using a cataloging system to assign a unique shelf location to each book.

### Hash Function — Maps Key to Bucket Index
The hash function is responsible for mapping a key to a specific index, known as a bucket index, in a data structure. This is done by applying a mathematical formula to the key, which produces a unique hash code. The hash code is then used to determine the bucket index where the associated data will be stored.

### Collision Handling
However, it's possible for two different keys to produce the same hash code, a situation known as a collision. To handle collisions, data structures use techniques such as chaining or open addressing. Chaining involves storing multiple key-value pairs in a single bucket, while open addressing involves probing other buckets to find an empty slot.

### Load Factor — Ratio of Entries to Buckets
The load factor is a measure of how full a data structure is, calculated as the ratio of the number of entries to the number of buckets. In Java, the default load factor for a HashMap is 0.75, which means that when the map is 75% full, it will be resized to maintain efficient lookup and insertion times.

### Rehashing — When Load Factor Exceeded
When the load factor exceeds a certain threshold, the data structure is resized, and all existing entries are rehashed to ensure that they are properly distributed across the new buckets. This process is known as rehashing and helps maintain the efficiency of the data structure.

### `hashCode()` and `equals()` Contract
In Java, the `hashCode()` and `equals()` methods are used to determine the uniqueness of objects. The `hashCode()` method returns a hash code for an object, while the `equals()` method checks whether two objects are equal. It's essential to override these methods in custom classes to ensure that objects are properly compared and stored in data structures.

### Custom `hashCode()` Implementation
To implement a custom `hashCode()` method, you can use the `Objects.hash()` method, which takes multiple fields as input and returns a hash code. Alternatively, you can use a prime number multiplier, such as 31, to combine the hash codes of individual fields.

### CORE INSIGHT
The core insight to remember is that hashing is a trade-off between memory usage and lookup efficiency. By using a hash function to map keys to indices, data structures can achieve fast lookup and insertion times, but may require more memory to store the hash codes and handle collisions.

## Syntax and Structure
```java
// Import the HashMap class
import java.util.HashMap;

// Create a new HashMap
HashMap<String, Integer> map = new HashMap<>();

// Put a key-value pair into the map
map.put("apple", 1);

// Get the value associated with a key
Integer value = map.get("apple");

// Check if a key is present in the map
boolean containsKey = map.containsKey("apple");

// Remove a key-value pair from the map
map.remove("apple");
```

## Practical Example
```java
// Create a new HashMap to store books
HashMap<String, Book> bookMap = new HashMap<>();

// Define a Book class with a title and author
class Book {
    String title;
    String author;

    public Book(String title, String author) {
        this.title = title;
        this.author = author;
    }
}

// Add books to the map
bookMap.put("To Kill a Mockingbird", new Book("To Kill a Mockingbird", "Harper Lee"));
bookMap.put("1984", new Book("1984", "George Orwell"));

// Retrieve a book from the map
Book book = bookMap.get("To Kill a Mockingbird");

// Print the title and author of the book
System.out.println("Title: " + book.title + ", Author: " + book.author);
```

## How This Connects to the Project
Before implementing hashing, the library management system would have to use a linear search to find a book, which would be inefficient for large collections. After implementing hashing, the system can use a HashMap to store books, allowing for fast lookup and retrieval of book information. The `Book` class would need to override the `hashCode()` and `equals()` methods to ensure proper comparison and storage in the map. The `Library` class would use the `HashMap` to store books, and the `getBook()` method would use the `hashCode()` method to quickly locate a book.

## Common Mistakes Beginners Make
* **Most common mistake**: Using a poor hash function that produces many collisions, leading to inefficient lookup and insertion times.
* **Looks right but is silently wrong**: Using a custom `hashCode()` method that is not consistent with the `equals()` method, leading to unexpected behavior when storing and retrieving objects.
* **Seems optional but critical at scale**: Failing to override the `hashCode()` and `equals()` methods in custom classes, leading to poor performance and incorrect results when using data structures.
* **Missed config or flag**: Not setting the initial capacity and load factor of a HashMap, leading to poor performance and unnecessary resizing.
* **Interview question**: How would you implement a custom `hashCode()` method for a class with multiple fields, and what considerations would you take into account to ensure efficient and correct hashing?

## Verification Task 1
Your system is experiencing slow lookup times when searching for books in the library. You have evidence that the current implementation uses a linear search. Diagnose and fix the issue.

## Solution 1
The issue is due to the use of a linear search, which has a time complexity of O(n). To fix the issue, implement a HashMap to store books, using the book's title as the key and the book object as the value. This will allow for fast lookup and retrieval of book information.

## Verification Task 2
You are designing a new data structure to store user information. Should you use a HashMap or a TreeMap to store the data, and why?

## Solution 2
You should use a HashMap to store the data, as it provides faster lookup and insertion times compared to a TreeMap. However, if you need to maintain a sorted order of the data, a TreeMap would be a better choice.

## Verification Task 3
The following code snippet is used to store books in a HashMap:
```java
HashMap<String, Book> bookMap = new HashMap<>();
bookMap.put("To Kill a Mockingbird", new Book("To Kill a Mockingbird", "Harper Lee"));
bookMap.put("1984", new Book("1984", "George Orwell"));
```
Find and fix the bug in the code.

## Solution 3
The bug in the code is that the `Book` class does not override the `hashCode()` and `equals()` methods, which can lead to unexpected behavior when storing and retrieving books from the map. To fix the issue, add the following methods to the `Book` class:
```java
@Override
public int hashCode() {
    return Objects.hash(title, author);
}

@Override
public boolean equals(Object obj) {
    if (this == obj) return true;
    if (obj == null || getClass() != obj.getClass()) return false;
    Book book = (Book) obj;
    return Objects.equals(title, book.title) && Objects.equals(author, book.author);
}
```

## What Comes Next
The next topic is Design Patterns — Creational, which follows logically from this topic because it builds on the concepts of hashing and data structures. In Design Patterns — Creational, you will learn how to apply creational design patterns to create objects and systems that are efficient, scalable, and maintainable. The concept of hashing will be directly used in the implementation of design patterns such as the Factory pattern and the Singleton pattern.

## Reference Summary
Hashing is a fundamental concept in computer science that enables fast and efficient lookup, insertion, and deletion of data in a collection. A hash function maps a key to a specific index in a data structure, allowing for rapid access and retrieval of associated data. The load factor and rehashing are critical concepts in maintaining the efficiency of data structures. The `hashCode()` and `equals()` methods are used to determine the uniqueness of objects, and custom implementation of these methods is essential for proper comparison and storage in data structures. Hashing is a trade-off between memory usage and lookup efficiency, and it is widely used in many applications, including library management systems. By understanding hashing, you can design and implement efficient data structures and systems that meet the requirements of your project.