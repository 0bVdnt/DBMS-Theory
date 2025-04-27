# Lock-Based Protocols

Parent: [[Concurrency Control Schemes]]

#transaction #concurrency #protocols #locking #2pl

[[../Transaction Concept|Transactions]] acquire locks on data items before accessing them to prevent [[../Conflict Serializability|conflicts]].

*   **Lock Modes:**
    *   **Shared (S):** For reading. Multiple transactions can hold S locks simultaneously.
    *   **Exclusive (X):** For writing (or reading+writing). Only one transaction can hold an X lock.
*   **Compatibility Matrix:**
    | Requested | S | X |
    |---|---|---|
    | **S** | Yes | No |
    | **X** | No | No |
*   **Core Protocol: [[Two-Phase Locking (2PL)]]**
*   **Challenges & Refinements:**
    *   [[Deadlock]]: Circular waiting for locks.
    *   [[Multiple Granularity Locking]]: Locking at different levels (table, page, row) for efficiency.
    *   [[Phantom Problem]]: Handling locks on predicates or sets of rows.
*   **Common Variants ensuring [[../Recoverability|Recoverability]]/[[../Cascadeless Schedules|Cascadelessness]]:**
    *   *Strict 2PL:* Hold all X-locks until commit/abort.
    *   *Rigorous 2PL:* Hold *all* locks (S and X) until commit/abort. (Most common).

---
**Related Concepts:**
*   [[Concurrency Control Schemes]]
*   [[Two-Phase Locking (2PL)]]
*   [[Deadlock]]
*   [[Multiple Granularity Locking]]
*   [[Phantom Problem]]
*   [[../Serializability of Scheduling]] (Guaranteed by 2PL)
*   [[../Recoverability]] / [[../Cascadeless Schedules]] (Ensured by Strict/Rigorous 2PL)
*   [[../ACID Properties]] (Isolation)
*   [[../Conflict Serializability]] 