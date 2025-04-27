# Transaction Concept

Parent: [[Transaction Processing Overview]]

#transaction

*   A **transaction** is a logical unit of work consisting of one or more database operations.
*   Example: Transferring funds involves reading balances, updating them, and writing them back.
*   **Challenges Addressed:**
    *   **Failures:** Hardware, software, system crashes. Handled by [[5 - Database Recovery/Database Recovery Overview|Database Recovery]] mechanisms, ensuring [[ACID Properties|Atomicity]] and [[ACID Properties|Durability]].
    *   **Concurrent Execution:** Multiple transactions running interleaved. Handled by [[Concurrency Control Schemes/Concurrency Control Schemes|Concurrency Control Schemes]] to ensure [[ACID Properties|Isolation]] and [[ACID Properties|Consistency]] (via [[Serializability of Scheduling|Serializability]]).

---
**Related Concepts:**
*   [[ACID Properties]] (The guarantees transactions provide)
*   [[Concept of Schedule]] (How concurrent operations are ordered)
*   [[Concurrency Control Schemes/Concurrency Control Schemes|Concurrency Control Schemes]] (Ensuring correctness of concurrent execution)
*   [[5 - Database Recovery/Database Recovery Overview|Database Recovery]] (Ensuring correctness despite failures) 