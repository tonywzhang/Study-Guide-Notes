# Algorithm Notes

## Graphs Notes

A graph is similar to a tree, in that it is a collection of objects or entities that we call nodes or vertices connected to each other through a set of edges. In a tree, there are restrictions on the way nodes/vertices are connected.

For example, if we have a tree with N nodes, we must have N-1 number of edges. We must have one edge for each parent-child relationship. Each node except the very root node will have an edge to it's parent.

* How do we define a graph, and where are they commonly used?
  * In mathematics, graphs are a way to formally represent a network, which is basically a collection of objects that are all inter-connected.
  * G = (V,E) where V is a set of nodes, also called vertices
  * E is a set of edges, also called links.


* What are the specific attributes that graphs can have, and how do we talk about them?
  * Graphs may have directed or undirected edges. Directed graphs have one directional edges, whereas undirected graphs have bi-directional edges.


* What are some ways we might store a graph in memory? What space/time complexity problems might we face?
  * If we store a graph in memory as nodes with pointers to one another, the space complexity is O(n) depending on the total number of nodes we have.
  * The number of pointers required is O(n^2)

## Adjacency Matrix

* We can represent our edges as a V x V array, where V denotes the number of vertices.
* We can label vertices based on each index.
* We denote 1s in columns/rows where the two nodes labeled have a connection. 0 denotes no connection.

This representation is considered an adjacency matrix representation.

If there are edges for each vertex towards every other vertex in the tree, it would expect there to be an estimated n^2 number of edges. An adjacency matrix would be a huge waste of space assuming n is an exceedingly large number.

## Recursion

### What is Recursion?

The process in which a function calls itself directly or indirectly is called recursion and the corresponding function is called as recursive function.

### What is base condition in recursion?

In recursive program, the solution to base case is provided and solution of bigger problem is expressed in terms of smaller problems.

### When does Stack Overflow occur in recursion?

If the base case is not reached or not defined, then stack overflow problem may arise.

### What is a Heap?

A Heap is nothing more than binary tree with some additional rules it has to follow.

A heap sort algorithm is a sorting technique that leans on binary heap data structures. Because we know that heaps must always follow a specific order, we can leverage that property and use that to find the largest, maximum value element, and sequentially sort elements by selecting the root node of a heap, and adding it to the end of the array.

### What is Bubble Sort?

Bubble sort has many of the same properties as insertion sort, but has slightly higher overhead. In the case of nearly sorted data, bubble sort takes O(n) time, but requires at least 2 passes through the data (whereas insertion sort requires something more like 1 pass).

```
for i = 1:n,
    swapped = false
    for j = n:i+1,
        if a[j] < a[j-1],
            swap a[j,j-1]
            swapped = true
    → invariant: a[1..i] in final position
    break if not swapped
end
```

* Stable
* O(1) extra space
* O(n2) comparisons and swaps
* Adaptive: O(n) when nearly sorted

### Algorithm Trivia

#### Data Structures

##### What is a Data Structure?

```
A Data Structure is a way to store and organize data in order to facilitate access and modifications. (Let's go into more depth)
```

##### Rank Data Structures in order of importance

```
Data Structures can be organized into several main categories:

Data Types(primitive, composite, abstract data types)
Linear Data Structures (arrays, lists)
Trees
Hashes
Graphs
```

##### Define the abstraction mechanism. What are it's benefits?

```
Abstraction can be thought of as a mechanism for suppressing irrelevant details while at the same time emphasizing relevant ones. An important benefit of abstraction is that it makes it easier for the programmer to think about the problem to be solved.
```

##### What is encapsulation?

```
Encapsulation is the mechanism of enforcing information hiding. Objects encapsulate data and the procedures for manipulating that data, thus the object hides the details of the implementation from the user of the object.
```

##### What is a binary numbering system?

```
A binary numbering system consists of two digits: one and zero. A switch in the off state represents zero and a switch in the on state represents one. This means that one transistor can represent one of two digits.
```

##### What is the binding process?

```
Binding is the process of assigning a value to an attribute. When a value is assigned to an attribute, it is said to be bound to the value. As an example, when defining a variable int i = 5, the value of the integer variable i is bound to 5.
```

##### What is the difference between early and late binding?

```
Early binding is the binding done statically by the compiler - it is realized by method overloading. Late binding is done dynamically at run-time and it is realized through inheritance and polymorphism.
```

##### Which are the main primitive data types?

```
Integer - stores whole numbers and signed numbers
Floating Point - store real numbers (fractional values)
Character - stores characters (names of things)
Boolean - stores a true or false value
```

#### What are the five standard algorithm approaches?

```
Examplify: Write out specific examples of the problem
Pattern Matching: Consider what problems the algorithm is similar to
Simplify & Generalize: Change a constraint to simplify the question. Once you have a general solution for the problem, expand it for the actual question.
Base Case & Build: Solve the algorithm for a base case, and then expand upon that with more complex cases.
Data Structure Brainstorm: Run through all Data Structures and see which one works best
```

#### Linked Lists
