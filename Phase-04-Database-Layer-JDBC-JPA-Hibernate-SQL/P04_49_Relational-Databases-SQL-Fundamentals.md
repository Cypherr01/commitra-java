## What Is This?
A relational database is a type of database that stores data in tables, with each table having rows and columns, similar to an Excel spreadsheet. Think of a relational database like a library where books are organized on shelves, and each book has a unique identifier, like an ISBN number, that distinguishes it from other books. Just as a library uses a catalog system to keep track of books, a relational database uses a system of tables, keys, and relationships to manage and retrieve data.

## How It Works Internally
### Introduction to Relational Databases
Relational databases are based on the concept of relational algebra, which provides a way to manage and manipulate data using mathematical operations. The core idea is to represent data as a collection of tables, each with a unique set of columns and rows.

### Data Organization in Tables
Data in a relational database is organized into tables, with each table having a set of columns and rows. Each column represents a field or attribute of the data, and each row represents a single record or tuple. For example, a table might have columns for a student's name, age, and grade, with each row representing a single student.

### Primary Key
A primary key is a unique identifier for each row in a table, similar to a student's ID number. It is used to distinguish one row from another and is often used as a reference point for relationships between tables. A primary key is typically defined as `NOT NULL` and `UNIQUE`, meaning that it cannot be empty and must be distinct for each row.

### Foreign Key
A foreign key is a field in a table that references the primary key of another table, establishing a relationship between the two tables. For example, a table of student grades might have a foreign key that references the student's ID number in the students table. This allows the database to link the grades to the corresponding student.

### Indexes
Indexes are data structures that improve the speed of data retrieval by providing a quick way to locate specific data. They work like an index in a book, allowing the database to quickly find the relevant data without having to scan the entire table. However, indexes can slow down data insertion and update operations, as the index must be updated along with the data.

### ACID Properties
Relational databases follow the ACID properties, which ensure that database transactions are processed reliably and securely. The ACID properties are:
* Atomicity: ensures that database transactions are treated as a single, indivisible unit
* Consistency: ensures that the database remains in a consistent state, even in the event of a failure
* Isolation: ensures that multiple transactions can be processed concurrently without interfering with each other
* Durability: ensures that once a transaction is committed, it is permanent and cannot be rolled back

### Database Normalization
Database normalization is the process of organizing data in a database to minimize data redundancy and improve data integrity. The goal is to ensure that each piece of data is stored in one place and one place only, reducing the risk of data inconsistencies. There are several levels of normalization, including 1NF, 2NF, and 3NF, each of which provides a higher level of normalization.

### DDL, DML, and TCL
Relational databases use several types of languages to manage and manipulate data:
* DDL (Data Definition Language) is used to define the structure of the database, including the creation of tables, indexes, and relationships.
* DML (Data Manipulation Language) is used to insert, update, and delete data in the database.
* TCL (Transaction Control Language) is used to manage transactions, including committing, rolling back, and saving transactions.

### SELECT Fundamentals
The `SELECT` statement is used to retrieve data from a database. It can be used with various clauses, such as `WHERE`, `ORDER BY`, `GROUP BY`, and `HAVING`, to filter, sort, and aggregate data.

### WHERE Operators
The `WHERE` clause is used to filter data based on conditions, such as equality, inequality, and range checks. Common `WHERE` operators include `=`, `!=`, `>`, `<`, `>=` , `<=`, `BETWEEN`, `IN`, `NOT IN`, `LIKE`, `IS NULL`, and `IS NOT NULL`.

### Aggregate Functions
Aggregate functions are used to perform calculations on a set of data, such as counting the number of rows, summing a column of values, or finding the average value. Common aggregate functions include `COUNT()`, `SUM()`, `AVG()`, `MAX()`, and `MIN()`.

### GROUP BY and HAVING
The `GROUP BY` clause is used to group data based on one or more columns, while the `HAVING` clause is used to filter the grouped data based on conditions.

### JOINs
A `JOIN` is used to combine data from two or more tables based on a common column. There are several types of `JOIN`s, including inner joins, left joins, right joins, and full outer joins.

### Subqueries
A subquery is a query nested inside another query. It is used to retrieve data that depends on the results of another query.

### Correlated Subquery
A correlated subquery is a subquery that references the outer query. It is used to retrieve data that depends on the results of the outer query.

### EXISTS vs IN
The `EXISTS` and `IN` operators are used to test for the existence of data in a subquery. The `EXISTS` operator checks if at least one row exists in the subquery, while the `IN` operator checks if a value exists in the subquery.

### CTEs
A common table expression (CTE) is a temporary result set that is defined within the execution of a single query. It is used to simplify complex queries and improve readability.

### Window Functions
Window functions are used to perform calculations on a set of data that is related to the current row, such as ranking or aggregating data.

### PL/SQL
PL/SQL is a procedural language that is used to create stored procedures, functions, and triggers in an Oracle database.

### Oracle-Specific Features
Oracle has several specific features, including the `DUAL` table, `ROWNUM`, `SYSDATE`, `NVL()`, `DECODE()`, and `CONNECT BY`.

## Syntax and Structure
```java
// Create a table
CREATE TABLE students (
  id INT PRIMARY KEY,
  name VARCHAR(255),
  age INT
);

// Insert data into the table
INSERT INTO students (id, name, age)
VALUES (1, 'John Doe', 20);

// Select data from the table
SELECT * FROM students
WHERE age > 18;
```

## Practical Example
```java
// Create a table
CREATE TABLE courses (
  id INT PRIMARY KEY,
  name VARCHAR(255),
  credits INT
);

// Insert data into the table
INSERT INTO courses (id, name, credits)
VALUES (1, 'Math', 3),
       (2, 'Science', 4),
       (3, 'English', 3);

// Create a table for student grades
CREATE TABLE grades (
  id INT PRIMARY KEY,
  student_id INT,
  course_id INT,
  grade DECIMAL(3, 2),
  FOREIGN KEY (student_id) REFERENCES students(id),
  FOREIGN KEY (course_id) REFERENCES courses(id)
);

// Insert data into the grades table
INSERT INTO grades (id, student_id, course_id, grade)
VALUES (1, 1, 1, 85.00),
       (2, 1, 2, 90.00),
       (3, 1, 3, 78.00);

// Select the student's grades
SELECT g.grade, c.name
FROM grades g
JOIN courses c ON g.course_id = c.id
WHERE g.student_id = 1;
```

## How This Connects to the Project
The EduHub project requires a relational database to store data about students, courses, and grades. The database will be designed using the concepts learned in this topic, including tables, primary and foreign keys, indexes, and normalization. The database will be used to store and retrieve data, and will be accessed using SQL queries.

## Common Mistakes Beginners Make
**Wrong idea:** Thinking that a relational database is the same as a spreadsheet.
**Correct idea:** A relational database is a powerful tool for managing and analyzing large amounts of data, with features like tables, relationships, and queries.

## Verification Task 1
Debug the following SQL query: `SELECT * FROM students WHERE age > 18;`. The query is returning an error message saying that the `age` column does not exist.

## Solution 1
The error message is indicating that the `age` column does not exist in the `students` table. To fix this, we need to check the table schema to see if the column name is correct. Let's assume that the correct column name is `student_age`. We can modify the query to use the correct column name: `SELECT * FROM students WHERE student_age > 18;`.

## Verification Task 2
Design a database schema for a simple e-commerce application. The application needs to store data about products, customers, and orders.

## Solution 2
We can design a database schema with three tables: `products`, `customers`, and `orders`. The `products` table can have columns for `product_id`, `name`, `price`, and `description`. The `customers` table can have columns for `customer_id`, `name`, `email`, and `address`. The `orders` table can have columns for `order_id`, `customer_id`, `product_id`, `quantity`, and `total_cost`. We can use foreign keys to establish relationships between the tables.

## Verification Task 3
Code review: The following SQL query is used to retrieve data about students: `SELECT * FROM students WHERE age > 18;`. However, the query is returning incorrect results. What could be the problem?

## Solution 3
The problem could be that the `age` column is not being updated correctly. Perhaps the `age` column is being calculated based on the student's birthdate, and the calculation is incorrect. We need to check the code that updates the `age` column to ensure that it is correct.

## What Comes Next
The next topic is JPA & Hibernate — ORM Fundamentals. This topic follows logically from the current topic because it builds on the concepts of relational databases and SQL. In JPA & Hibernate, we will learn how to use an object-relational mapping (ORM) tool to interact with a relational database using Java. We will learn how to define entities, map them to tables, and perform CRUD operations using Hibernate. The concept of relational databases and SQL is a prerequisite for JPA & Hibernate because it provides the foundation for understanding how data is stored and retrieved in a relational database. One concrete concept from this topic that will reappear in JPA & Hibernate is the use of primary and foreign keys to establish relationships between tables.

## Reference Summary
A relational database is a type of database that stores data in tables, with each table having rows and columns. The database uses a system of tables, keys, and relationships to manage and retrieve data. The ACID properties ensure that database transactions are processed reliably and securely. Database normalization is used to minimize data redundancy and improve data integrity. SQL is used to define the structure of the database, insert, update, and delete data, and retrieve data. Common mistakes beginners make include thinking that a relational database is the same as a spreadsheet, and not understanding the importance of normalization. The EduHub project requires a relational database to store data about students, courses, and grades. The database will be designed using the concepts learned in this topic, and will be used to store and retrieve data using SQL queries.