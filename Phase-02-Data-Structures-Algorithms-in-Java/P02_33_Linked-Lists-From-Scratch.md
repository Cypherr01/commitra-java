## What Is This?
A linked list is a data structure in which a sequence of nodes are linked together through pointers, allowing for efficient insertion and deletion of elements. Imagine a train with cars, where each car represents a node, and the connection between cars represents the link between nodes, allowing the train to be easily extended or shortened by adding or removing cars.

## How It Works Internally
### Singly Linked List Implementation
A singly linked list is the most basic type of linked list, where each node only points to the next node in the sequence. This is similar to a train where each car only knows about the car in front of it.

### Node Class
The node class is the building block of a linked list, which typically contains a value (data) and a reference (link) to the next node in the sequence. 
```text
# define a node with data and a link to the next node
# the data can be of any type (e.g., integer, string)
# the next node is a reference to another node
```

### LinkedList Class
The LinkedList class typically has a head pointer, which points to the first node in the sequence, and a size variable, which keeps track of the number of nodes in the list. 
```text
# define a linked list with a head pointer and a size variable
# the head pointer points to the first node in the sequence
# the size variable keeps track of the number of nodes
```

### Operations
The LinkedList class supports various operations such as insert at head, insert at tail, insert at a specific position, delete, search, and reverse. These operations are essential for manipulating the linked list.
```text
# insert a new node at the head of the list
# insert a new node at the tail of the list
# insert a new node at a specific position in the list
# delete a node from the list
# search for a node in the list
# reverse the order of nodes in the list
```

### Doubly Linked List
A doubly linked list is an extension of the singly linked list, where each node has two pointers: one pointing to the next node and another pointing to the previous node. This is similar to a train where each car knows about both the car in front of it and the car behind it.
```text
# define a node with data, a link to the next node, and a link to the previous node
```

### Circular Linked List
A circular linked list is a type of linked list where the last node points back to the first node, forming a circle. This is similar to a train where the last car is connected to the first car, forming a loop.
```text
# define a circular linked list where the last node points to the first node
```

### Fast and Slow Pointer (Floyd's Cycle Detection)
Floyd's cycle detection algorithm is used to detect whether a linked list has a cycle. It uses two pointers, a fast pointer and a slow pointer, to traverse the list. If there is a cycle, the fast pointer will eventually catch up to the slow pointer.
```text
# define a function to detect a cycle in a linked list using Floyd's algorithm
```

### Finding Middle of Linked List
To find the middle of a linked list, we can use the slow and fast pointer approach. The slow pointer moves one step at a time, while the fast pointer moves two steps at a time. When the fast pointer reaches the end of the list, the slow pointer will be at the middle.
```text
# define a function to find the middle of a linked list
```

### Merging Two Sorted Linked Lists
To merge two sorted linked lists, we can compare the values of the nodes and link the smaller value node first. This process continues until one of the lists is exhausted.
```text
# define a function to merge two sorted linked lists
```

### Reversing a Linked List Iteratively and Recursively
To reverse a linked list, we can use an iterative approach by keeping track of the previous node and reversing the link between nodes. We can also use a recursive approach by reversing the rest of the list and then linking the current node to the reversed list.
```text
# define a function to reverse a linked list iteratively
# define a function to reverse a linked list recursively
```

## Syntax and Structure
```java
// define a node class
public class Node<T> {
    T data;
    Node<T> next;

    // constructor to initialize the node
    public Node(T data) {
        this.data = data;
        this.next = null;
    }
}

// define a linked list class
public class LinkedList<T> {
    Node<T> head;
    int size;

    // constructor to initialize the linked list
    public LinkedList() {
        this.head = null;
        this.size = 0;
    }

    // method to insert a new node at the head of the list
    public void insertAtHead(T data) {
        Node<T> newNode = new Node<>(data);
        newNode.next = head;
        head = newNode;
        size++;
    }

    // method to insert a new node at the tail of the list
    public void insertAtTail(T data) {
        Node<T> newNode = new Node<>(data);
        if (head == null) {
            head = newNode;
        } else {
            Node<T> current = head;
            while (current.next != null) {
                current = current.next;
            }
            current.next = newNode;
        }
        size++;
    }
}
```

## Practical Example
```java
public class Main {
    public static void main(String[] args) {
        LinkedList<Integer> list = new LinkedList<>();
        list.insertAtHead(1);
        list.insertAtHead(2);
        list.insertAtTail(3);
        list.insertAtTail(4);
        // print the linked list
        Node<Integer> current = list.head;
        while (current != null) {
            System.out.print(current.data + " ");
            current = current.next;
        }
    }
}
```

## How This Connects to the Project
Before learning about linked lists, the library management system project would have to use a fixed-size array to store the catalog of books, which would be inefficient and inflexible. After learning about linked lists, the project can use a dynamic linked list to store the catalog, allowing for efficient insertion and deletion of books. The exact file and function name where this concept lives in the project is `BookCatalog.java` and `addBook()` function. One real company that uses this exact pattern is Amazon, which uses linked lists to manage its vast catalog of products.

## Common Mistakes Beginners Make
**Most common mistake**: Not checking for null pointers when traversing a linked list, which can lead to a NullPointerException. 
Wrong idea: Assuming that the next node will always exist.
Correct idea: Always check if the next node is null before accessing it.

**Looks right but is silently wrong**: Inserting a new node at the head of the list without updating the head pointer, which can lead to the loss of the new node.
```java
// incorrect code
public void insertAtHead(T data) {
    Node<T> newNode = new Node<>(data);
}
```
**Seems optional but critical at scale**: Not handling edge cases such as inserting at an empty list or deleting from an empty list.
**Missed config or flag**: Not setting the next pointer of the last node to null, which can lead to a cycle in the linked list.
**Interview question**: How would you implement a linked list in Java, and what are the time and space complexities of the insert and delete operations?

## Verification Tasks
## Verification Task 1
Debug the following code: 
```java
public void insertAtHead(T data) {
    Node<T> newNode = new Node<>(data);
    newNode.next = head;
    head = newNode;
}
```
The code is supposed to insert a new node at the head of the list, but it throws a NullPointerException.

## Solution 1
The problem is that the size variable is not being updated after inserting a new node. To fix this, we need to increment the size variable after inserting the new node.
```java
public void insertAtHead(T data) {
    Node<T> newNode = new Node<>(data);
    newNode.next = head;
    head = newNode;
    size++;
}
```

## Verification Task 2
Design a function to merge two sorted linked lists. The function should take two linked lists as input and return a new linked list that contains all the elements from the two input lists in sorted order.

## Solution 2
We can use a recursive approach to merge the two linked lists. We compare the values of the nodes at the current positions in the two lists and link the smaller value node first. We repeat this process until one of the lists is exhausted.
```java
public LinkedList<T> merge(LinkedList<T> list1, LinkedList<T> list2) {
    LinkedList<T> mergedList = new LinkedList<>();
    Node<T> current1 = list1.head;
    Node<T> current2 = list2.head;
    while (current1 != null && current2 != null) {
        if (current1.data < current2.data) {
            mergedList.insertAtTail(current1.data);
            current1 = current1.next;
        } else {
            mergedList.insertAtTail(current2.data);
            current2 = current2.next;
        }
    }
    while (current1 != null) {
        mergedList.insertAtTail(current1.data);
        current1 = current1.next;
    }
    while (current2 != null) {
        mergedList.insertAtTail(current2.data);
        current2 = current2.next;
    }
    return mergedList;
}
```

## Verification Task 3
Find and fix the bug in the following code:
```java
public void delete(T data) {
    if (head == null) {
        return;
    }
    if (head.data == data) {
        head = head.next;
    } else {
        Node<T> current = head;
        while (current.next != null) {
            if (current.next.data == data) {
                current.next = current.next.next;
                return;
            }
            current = current.next;
        }
    }
}
```
The code is supposed to delete the first occurrence of the specified data in the list, but it throws a NullPointerException.

## Solution 3
The problem is that the size variable is not being updated after deleting a node. To fix this, we need to decrement the size variable after deleting the node.
```java
public void delete(T data) {
    if (head == null) {
        return;
    }
    if (head.data == data) {
        head = head.next;
        size--;
    } else {
        Node<T> current = head;
        while (current.next != null) {
            if (current.next.data == data) {
                current.next = current.next.next;
                size--;
                return;
            }
            current = current.next;
        }
    }
}
```

## What Comes Next
The next topic is Trees, which builds upon the concepts learned in this topic, such as node structures and recursive traversal. The knowledge of linked lists is essential for understanding tree data structures, as trees can be viewed as a specialized type of linked list where each node has a fixed number of children. One concrete concept from this topic that will reappear in Trees is the idea of recursive traversal, which is used to visit each node in the tree.

## Reference Summary
A linked list is a dynamic data structure that consists of nodes linked together through pointers, allowing for efficient insertion and deletion of elements. The LinkedList class supports various operations such as insert, delete, and search, and has a time complexity of O(1) for insertion and deletion at the head, and O(n) for search. The most common production mistake is not checking for null pointers when traversing the list, which can lead to a NullPointerException. The concept of linked lists is essential for understanding more complex data structures such as trees and graphs, and is used in many real-world applications such as database query optimization and file system management. This matters to you because understanding linked lists is crucial for building efficient and scalable data structures in your projects.