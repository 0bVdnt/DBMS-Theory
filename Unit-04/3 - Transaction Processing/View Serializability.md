# View Serializability

Parent: [[Serializability of Scheduling]]

#transaction #concurrency #serializability #view

*   **Concept:** A less strict, more general form of [[Serializability of Scheduling|serializability]] than [[Conflict Serializability]].
*   **View Equivalence:** Two [[Concept of Schedule|schedules]] S and S' are view equivalent if:
    1.  They have the same set of [[Transaction Concept|transactions]].
    2.  For each data item Q, if `Ti` reads the initial value of Q in S, it also reads the initial value in S'.
    3.  For each data item Q, if `Ti` reads a value written by `Tj` in S, it also reads the value written by `Tj` in S'.
    4.  For each data item Q, the transaction performing the final write of Q is the same in both S and S'.
*   **View Serializable Schedule:** A schedule that is view equivalent to some [[Concept of Schedule|serial schedule]].
*   **Relationship to Conflict Serializability:** All conflict serializable schedules are view serializable, but the reverse is not always true (e.g., schedules with "blind writes" - writing without reading first).
*   **Practicality:** Testing for view serializability is NP-complete, making it impractical for use in real [[Concurrency Control Schemes/Concurrency Control Schemes|concurrency control mechanisms]]. [[Conflict Serializability]] is used instead.

---
**Related Concepts:**
*   [[Serializability of Scheduling]]
*   [[Conflict Serializability]]
*   [[Concept of Schedule]]
*   [[Transaction Concept]] 