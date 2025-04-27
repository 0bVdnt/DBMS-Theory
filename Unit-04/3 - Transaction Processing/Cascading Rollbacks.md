# Cascading Rollbacks

Parent: [[Recoverability]]

#transaction #concurrency #schedule #recovery #problem

*   **Problem:** A situation in a [[Recoverability|recoverable]] [[Concept of Schedule|schedule]] where the failure/abort of one [[Transaction Concept|transaction]] (`Ti`) causes one or more other transactions (`Tj`, `Tk`, ...) that read data written by `Ti` to also be aborted.
*   **Why it's Undesirable:** Leads to wasted work and potentially significant performance degradation as the rollback cascades through dependent transactions.
*   **Example:** `T1` writes X, `T2` reads X, `T1` aborts. Because the schedule must be [[Recoverability|recoverable]], `T2` cannot commit until `T1` commits. Since `T1` aborts, `T2` must also abort.

This problem is avoided by using [[Cascadeless Schedules]].

---
**Related Concepts:**
*   [[Recoverability]] (Cascading rollbacks can occur in recoverable schedules)
*   [[Cascadeless Schedules]] (Prevent cascading rollbacks)
*   [[Concept of Schedule]]
*   [[Transaction Concept]]
*   [[ACID Properties]] (Related to Atomicity) 