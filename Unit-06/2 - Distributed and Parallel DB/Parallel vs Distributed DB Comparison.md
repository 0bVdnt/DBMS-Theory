# Parallel vs Distributed Database Comparison

| Feature             | [[Parallel Database Systems]]                    | [[Distributed Database Systems]]                            |
| :------------------ | :----------------------------------------------- | :---------------------------------------------------------- |
| **Coupling**        | Tightly coupled (high-speed interconnect)        | Loosely coupled (standard network)                          |
| **Autonomy**        | Nodes are non-autonomous                         | Sites are often autonomous                                  |
| **Primary Goal**    | Performance through parallelization              | [[Availability]], Sharing, Autonomy through distribution    |
| **[[Scalability]]** | Typically Shared Nothing offers high scalability | Designed for geographical distribution, scales horizontally |

**Convergence:** The lines can blur. Shared-nothing [[Parallel Database Systems|parallel systems]] resemble [[Distributed Database Systems|distributed systems]] architecturally. Many [[NoSQL Databases|NoSQL systems]] and [[Big Data Technologies|Big Data frameworks]] (like [[Hadoop Introduction|Hadoop]]) are inherently both parallel (within nodes) and distributed (across nodes).

See also: [[Parallel Database Systems]], [[Distributed Database Systems]], [[Distributed Database Model]], [[Scalability (Horizontal vs Vertical)]]

---
Tags: #parallel-db #distributed-db #comparison #architecture #performance #availability #autonomy #scalability 