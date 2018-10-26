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

* What is a Data Structure?

A Data Structure is a way to store and organize data in order to facilitate access and modifications. (Let's go into more depth)
