# Deadlock

Parent: [[Lock-Based Protocols]]

#transaction #concurrency #protocols #locking #deadlock #problem

*   **Definition:** A situation where two or more [[../Transaction Concept|transactions]] are blocked indefinitely, each waiting for a resource (typically a lock) held by another transaction in the cycle.
*   **Example:** T1 locks A, waits for B; T2 locks B, waits for A.
*   **Condition:** Arises under [[Lock-Based Protocols]] like [[Two-Phase Locking (2PL)|2PL]] when transactions acquire multiple locks.

## Deadlock Handling Strategies

1.  **Deadlock Prevention:** Impose rules to ensure cycles cannot form.
    *   *Lock Ordering:* Acquire locks in a predefined global order (can be restrictive).
    *   *Wait-Die:* If T(older) requests lock held by T(younger), T(older) waits. If T(younger) requests lock held by T(older), T(younger) aborts (dies).
    *   *Wound-Wait:* If T(older) requests lock held by T(younger), T(younger) aborts (is wounded). If T(younger) requests lock held by T(older), T(younger) waits.
2.  **Deadlock Detection and Recovery:** Allow deadlocks to occur, detect them, and break the cycle.
    *   *Wait-For Graph:* Nodes are transactions, edge `Ti -> Tj` if `Ti` waits for `Tj`. Cycles indicate deadlock.
    *   *Detection:* Periodically build/check the wait-for graph for cycles.
    *   *Recovery (Victim Selection):* Abort one or more transactions in the cycle to break it. Choice of victim based on factors like age, locks held, work done, etc.

---
**Related Concepts:**
*   [[Lock-Based Protocols]]
*   [[Two-Phase Locking (2PL)]]
*   [[../Testing for Serializability]] (Wait-for graph is similar to precedence graph)
*   [[../Transaction Concept]]
*   [[../ACID Properties]] (Can lead to transaction aborts - Atomicity) 