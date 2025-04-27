# Testing for Serializability (Precedence Graph)

Parent: [[Serializability of Scheduling]]

#transaction #concurrency #serializability #testing #graph

Method for testing if a [[Concept of Schedule|schedule]] is [[Conflict Serializability|conflict serializable]].

*   **Procedure:**
    1.  Create a directed graph where each node represents a committed [[Transaction Concept|transaction]] (`Ti`) in the schedule.
    2.  For every pair of [[Conflict Serializability|conflicting operations]] (from different transactions `Ti` and `Tj` where the operation from `Ti` occurs before the operation from `Tj` in the schedule), draw a directed edge from `Ti` to `Tj` (`Ti -> Tj`).
*   **Condition:** The schedule is **conflict serializable if and only if** the precedence graph is **acyclic** (contains no directed cycles).
*   **Interpretation:** If the graph is acyclic, a [[Concept of Schedule|serial schedule]] equivalent to the concurrent schedule can be obtained by topologically sorting the graph.

---
**Related Concepts:**
*   [[Serializability of Scheduling]]
*   [[Conflict Serializability]]
*   [[Concept of Schedule]]
*   [[Transaction Concept]]
*   [[Concurrency Control Schemes/Deadlock|Deadlock]] (Wait-for graphs used for deadlock detection are similar) 