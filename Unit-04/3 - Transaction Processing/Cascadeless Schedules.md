# Cascadeless Schedules

Parent: [[Recoverability]]

#transaction #concurrency #schedule #recovery #solution

*   **Definition:** A stronger condition than [[Recoverability]]. In a cascadeless schedule, if [[Transaction Concept|transaction]] `Tj` reads data written by `Ti`, then `Ti` must commit *before* `Tj` reads that data.
*   **Advantage:** Prevents [[Cascading Rollbacks]]. If `Ti` aborts, no other transaction `Tj` could have possibly read its (now invalid) data, so no other transaction needs to be aborted as a consequence of `Ti`'s failure.
*   **Relationship to Recoverability:** All cascadeless schedules are also [[Recoverability|recoverable]].
*   **Implementation:** [[Concurrency Control Schemes/Concurrency Control Schemes|Concurrency control protocols]] like Strict [[Concurrency Control Schemes/Two-Phase Locking (2PL)|Two-Phase Locking]] typically generate cascadeless schedules.

This is a highly desirable property for [[Concept of Schedule|schedules]] as it simplifies [[5 - Database Recovery/Database Recovery Overview|recovery]] actions.

---
**Related Concepts:**
*   [[Recoverability]]
*   [[Cascading Rollbacks]] (Avoided by cascadeless schedules)
*   [[Concept of Schedule]]
*   [[Transaction Concept]]
*   [[Concurrency Control Schemes/Concurrency Control Schemes|Concurrency Control Schemes]] (e.g., Strict [[Concurrency Control Schemes/Two-Phase Locking (2PL)|2PL]])
*   [[5 - Database Recovery/Database Recovery Overview|Database Recovery]] 