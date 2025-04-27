# Conflict Serializability

Parent: [[Serializability of Scheduling]]

#transaction #concurrency #serializability #conflict

*   **Conflicting Operations:** Two operations conflict if they belong to different [[Transaction Concept|transactions]], access the same data item, and at least one is a write (`R-W`, `W-R`, `W-W`). `R-R` does not conflict.
*   **Conflict Equivalence:** Two [[Concept of Schedule|schedules]] are conflict equivalent if one can be transformed into the other by a series of swaps of adjacent, non-conflicting operations.
*   **Conflict Serializable Schedule:** A [[Concept of Schedule|schedule]] that is conflict equivalent to some [[Concept of Schedule|serial schedule]].
*   **Testing:** Can be efficiently checked using the [[Testing for Serializability|precedence graph]] method.

**Note:** All conflict serializable schedules are also [[View Serializability|view serializable]]. This is the type of serializability typically enforced by [[Concurrency Control Schemes/Concurrency Control Schemes|concurrency control protocols]] like [[Concurrency Control Schemes/Two-Phase Locking (2PL)|Two-Phase Locking]].

---
**Related Concepts:**
*   [[Serializability of Scheduling]]
*   [[View Serializability]]
*   [[Testing for Serializability]]
*   [[Concept of Schedule]]
*   [[Transaction Concept]]
*   [[Concurrency Control Schemes/Concurrency Control Schemes|Concurrency Control Schemes]] 