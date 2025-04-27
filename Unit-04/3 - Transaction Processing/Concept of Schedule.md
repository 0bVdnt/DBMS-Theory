# Concept of Schedule

Parent: [[Transaction Processing Overview]]

#transaction #concurrency #schedule

*   **Definition:** An ordering of operations (read, write, abort, commit) from one or more concurrent [[Transaction Concept|transactions]].
*   **Constraint:** Must preserve the order of operations within each individual transaction.
*   **Types:**
    *   **Serial Schedule:** Operations of different transactions are not interleaved (executed one after another). Always consistent if individual transactions preserve [[ACID Properties|Consistency]]. Performance can be poor.
    *   **Concurrent Schedule:** Operations from multiple transactions are interleaved. Offers better throughput and resource utilization but requires [[Concurrency Control Schemes/Concurrency Control Schemes|Concurrency Control]] to ensure correctness, typically by guaranteeing [[Serializability of Scheduling|Serializability]].

---
**Related Concepts:**
*   [[Transaction Concept]]
*   [[Serializability of Scheduling]] (Correctness criterion for concurrent schedules)
*   [[Concurrency Control Schemes/Concurrency Control Schemes|Concurrency Control Schemes]] (Mechanisms to manage concurrent schedules) 