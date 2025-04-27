# Recoverability

Parent: [[Transaction Processing Overview]]

#transaction #concurrency #schedule #recovery

Ensures that [[Transaction Concept|transactions]] commit only after all transactions whose changes they read have already committed. This property is crucial for [[5 - Database Recovery/Database Recovery Overview|database recovery]] and prevents anomalies arising from reading uncommitted ("dirty") data.

*   **Recoverable Schedule:** If transaction `Tj` reads data written by transaction `Ti`, then `Ti` must commit before `Tj` commits.
*   **Problem Avoided:** Prevents situations where `Tj` commits based on data from `Ti`, but `Ti` subsequently aborts. If the schedule wasn't recoverable, `Tj`'s committed state would reflect an aborted transaction's effects, violating [[ACID Properties|Consistency]]/[[ACID Properties|Atomicity]].

Further constraints are often desirable:
*   [[Cascading Rollbacks]] (Problem)
*   [[Cascadeless Schedules]] (Solution)

[[Concurrency Control Schemes/Concurrency Control Schemes|Concurrency control protocols]] often ensure recoverability implicitly (e.g., Strict [[Concurrency Control Schemes/Two-Phase Locking (2PL)|2PL]]).

---
**Related Concepts:**
*   [[Concept of Schedule]]
*   [[Serializability of Scheduling]] (Orthogonal property, desirable schedules are both serializable and recoverable/cascadeless)
*   [[Cascading Rollbacks]]
*   [[Cascadeless Schedules]]
*   [[ACID Properties]] (Consistency, Atomicity)
*   [[5 - Database Recovery/Database Recovery Overview|Database Recovery]]
*   [[Concurrency Control Schemes/Concurrency Control Schemes|Concurrency Control Schemes]] 