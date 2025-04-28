# CAP Theorem (Brewer's Theorem)

The CAP Theorem, formulated by Eric Brewer, states that it is impossible for a [[Distributed Database Model|distributed data system]] to simultaneously guarantee all three of the following properties:

1.  **[[Consistency]] (C):** Every read receives the most recent write or an error. All nodes see the same data at the same time (looks like a single, up-to-date system).
2.  **[[Availability]] (A):** Every request (read or write) receives a (non-error) response, without guarantee that it contains the most recent write. The system remains operational.
3.  **[[Partition Tolerance]] (P):** The system continues to operate despite an arbitrary number of messages being dropped (or delayed) by the network between nodes (i.e., the network partitions into potentially non-communicating sub-groups).

## The Trade-off

In a real-world distributed system, network [[Partition Tolerance|partitions (P) are a fact of life]]. Therefore, when a partition occurs, a system must choose between Consistency (C) and Availability (A):

*   **CP System**: Chooses [[Consistency]] over [[Availability]]. If a partition occurs, the system might become unavailable (return errors or wait indefinitely) to avoid returning stale data from one side of the partition. (e.g., Traditional [[RDBMS]] with distributed transactions often lean CP).
*   **AP System**: Chooses [[Availability]] over [[Consistency]]. If a partition occurs, the system remains available, but some nodes might return older versions of data until the partition heals ([[Eventual Consistency]]). (e.g., Many [[NoSQL Databases|NoSQL systems]] like [[Cassandra Overview|Cassandra]], DynamoDB).
*   **CA System**: Chooses [[Consistency]] and [[Availability]] but cannot tolerate [[Partition Tolerance|partitions]]. This only works if the system is not distributed (e.g., a single-node [[RDBMS]]).

The [[BASE Properties]] model is often associated with AP systems.

---
Tags: #distributed #cap-theorem #consistency #availability #partition-tolerance #theory #tradeoff #nosql #rdbms 