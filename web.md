# Web Notes

* REST (Representation State Transfer) is a term we have thrown around a lot in the course.
  ### [Reading here](https://codewords.recurse.com/issues/five/what-restful-actually-means)

  * It is a set of design principles for making network communication more scalable and flexible.
  * These principles answer a number of questions.
  * What are the components of the system?
  * How should they communicate with each other?
  * How do we ensure we can swap out different parts of the system at any time?
  * How can the system be scaled up to serve billions of users?

## Stateless

Stateless does not mean that servers and clients do not have state, it simply means that they do not need to keep track of each other’s state. When a client is not interacting with the server, the server has no idea of its existence. The server also does not keep a record of past requests. Each request is treated as a standalone.
