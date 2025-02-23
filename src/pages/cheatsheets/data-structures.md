---
title: 'Java Data Structures Cheatsheet'
pubDate: 2025-02-16
description: 'A quick reference to the most important data structures in Java.'
author: 'Bryan Lazo'
image:
    url: 'https://www.example.com/data-structures-image.jpg'
    alt: 'A diagram showing different data structures in Java.'
tags: ["java", "data structures", "learning", "programming"]
---

## **Different Data Structures in Java**

Java provides a variety of **linear** and **non-linear** data structures to handle different types of data efficiently.

---

## **1. Linear Data Structures**

Linear data structures store elements in a sequential order.

### **1.1 Arrays**

- Collection of elements of the same type with a fixed size.
- Fast access using an index.
- Cannot be resized dynamically.

📌 **Example:**

```java
int[] numbers = {1, 2, 3, 4, 5};
System.out.println(numbers[2]); // Output: 3
```

---

### **1.2 ArrayList (Dynamic List)**

- Similar to an array but resizable.
- Allows adding and removing elements dynamically.

📌 **Example:**

```java
import java.util.ArrayList;

ArrayList<String> list = new ArrayList<>();
list.add("Alice");
list.add("Bob");
list.remove("Alice"); // Removes "Alice"
System.out.println(list.get(0)); // Output: Bob
```

---

### **1.3 LinkedList (Doubly Linked List)**

- Implements a doubly linked list.
- More efficient for inserting and deleting elements in the middle.
- Can be used as a **list**, **stack**, or **queue**.

📌 **Example:**

```java
import java.util.LinkedList;

LinkedList<Integer> list = new LinkedList<>();
list.add(10);
list.addFirst(5); // Adds at the beginning
list.addLast(15); // Adds at the end
System.out.println(list); // Output: [5, 10, 15]
```

---

### **1.4 Stack (LIFO - Last In, First Out)**

- Last in, first out (**LIFO**) principle.
- Used for **undo/redo** operations, parsing, etc.

📌 **Example:**

```java
import java.util.Stack;

Stack<Integer> stack = new Stack<>();
stack.push(1);
stack.push(2);
System.out.println(stack.pop()); // Output: 2 (last in, first out)
```

---

### **1.5 Queue (FIFO - First In, First Out)**

- First in, first out (**FIFO**) principle.
- Useful for scheduling tasks, request handling, etc.

📌 **Example:**

```java
import java.util.LinkedList;
import java.util.Queue;

Queue<String> queue = new LinkedList<>();
queue.offer("A");
queue.offer("B");
System.out.println(queue.poll()); // Output: A (removes the first element)
```

---

### **1.6 Deque (Double-ended Queue - FIFO or LIFO)**

- Allows inserting and removing elements from both ends.

📌 **Example:**

```java
import java.util.ArrayDeque;

ArrayDeque<Integer> deque = new ArrayDeque<>();
deque.addFirst(10);
deque.addLast(20);
System.out.println(deque.removeFirst()); // Output: 10
```

---

## **2. Non-Linear Data Structures**

Non-linear data structures organize elements in a more complex relationship, like trees and graphs.

### **2.1 HashSet (Set - No Duplicates)**

- Stores unique elements without a defined order.
- Fast insertions, searches, and deletions.

📌 **Example:**

```java
import java.util.HashSet;

HashSet<Integer> set = new HashSet<>();
set.add(1);
set.add(2);
set.add(1); // Won't be added since it's a duplicate
System.out.println(set.contains(2)); // Output: true
```

---

### **2.2 HashMap (Key-Value Dictionary)**

- Associates unique keys with values.
- Allows fast lookup using keys.

📌 **Example:**

```java
import java.util.HashMap;

HashMap<String, Integer> map = new HashMap<>();
map.put("Alice", 25);
map.put("Bob", 30);
System.out.println(map.get("Alice")); // Output: 25
```

---

### **2.3 Trees (TreeSet and TreeMap)**

- **TreeSet** stores unique elements in ascending order.
- **TreeMap** stores key-value pairs sorted by key.

📌 **Example TreeSet:**

```java
import java.util.TreeSet;

TreeSet<Integer> treeSet = new TreeSet<>();
treeSet.add(5);
treeSet.add(1);
treeSet.add(10);
System.out.println(treeSet); // Output: [1, 5, 10] (sorted)
```

📌 **Example TreeMap:**

```java
import java.util.TreeMap;

TreeMap<String, Integer> treeMap = new TreeMap<>();
treeMap.put("Charlie", 40);
treeMap.put("Alice", 25);
System.out.println(treeMap); // Output: {Alice=25, Charlie=40} (sorted by key)
```

---

### **2.4 Graphs**

- Represent relationships between nodes.
- Can be implemented using adjacency lists or adjacency matrices.

📌 **Example representation using a `HashMap`:**

```java
import java.util.*;

class Graph {
    private Map<String, List<String>> adjList = new HashMap<>();

    public void addEdge(String node, String neighbor) {
        adjList.putIfAbsent(node, new ArrayList<>());
        adjList.get(node).add(neighbor);
    }

    public List<String> getNeighbors(String node) {
        return adjList.getOrDefault(node, new ArrayList<>());
    }
}

public class Main {
    public static void main(String[] args) {
        Graph graph = new Graph();
        graph.addEdge("A", "B");
        graph.addEdge("A", "C");
        System.out.println(graph.getNeighbors("A")); // Output: [B, C]
    }
}
```

---

## **Summary of Java's Main Data Structures**

| Type           | Implementation        | Characteristics                     |
|----------------|-----------------------|-------------------------------------|
| **Array**      | `int[]`               | Fixed size, fast index-based access |
| **ArrayList**  | `ArrayList<T>`        | Dynamic size, allows duplicates     |
| **LinkedList** | `LinkedList<T>`       | Fast insert/delete in the middle    |
| **Stack**      | `Stack<T>`            | LIFO (Last In, First Out)           |
| **Queue**      | `Queue<T>`            | FIFO (First In, First Out)          |
| **Deque**      | `ArrayDeque<T>`       | Insert/remove from both ends        |
| **HashSet**    | `HashSet<T>`          | Stores unique elements, unordered   |
| **TreeSet**    | `TreeSet<T>`          | Unique elements in ascending order  |
| **HashMap**    | `HashMap<K, V>`       | Key-value pairs, unordered          |
| **TreeMap**    | `TreeMap<K, V>`       | Key-value pairs, sorted by key      |
| **Graph**      | `HashMap<K, List<K>>` | Represents node relationships       |

---

### **Conclusion**

These data structures are fundamental in Java. Mastering them will help you optimize the efficiency of your programs and
choose the right tool for each situation. 🚀