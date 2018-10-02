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



* REST (Representation State Transfer) is a term we have thrown around a lot in the course.
  * It is a set of design principles for making network communication more scalable and flexible.
