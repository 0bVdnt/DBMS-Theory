# Two-Phase Locking (2PL)

Parent: [[Lock-Based Protocols]]

#transaction #concurrency #protocols #locking #2pl

A fundamental [[Lock-Based Protocols|lock-based protocol]] that guarantees [[../Conflict Serializability|conflict serializability]].

*   **Phases:**
    1.  **Growing Phase:** Transaction can acquire locks (S or X) but cannot release any locks.
    2.  **Shrinking Phase:** Transaction can release locks but cannot acquire any new locks.
*   **Guarantee:** Ensures [[../Conflict Serializability|conflict serializability]] by forcing a serial order based on when transactions reach their "lock point" (the end of the growing phase).
*   **Limitations:**
    *   Does **not** inherently prevent [[Deadlock]].
    *   Basic 2PL does **not** guarantee [[../Recoverability|recoverability]] or prevent [[../Cascading Rollbacks]].
*   **Variants:**
    *   *Strict 2PL:* Hold all *exclusive* (X) locks until commit/abort. Prevents [[../Cascading Rollbacks]] related to writes (ensures [[../Recoverability|recoverability]] for writes).
    *   *Rigorous 2PL:* Hold *all* locks (shared (S) and exclusive (X)) until commit/abort. Prevents [[../Cascading Rollbacks]] entirely and ensures [[../Cascadeless Schedules|cascadelessness]]. Most commonly implemented version.

---
**Related Concepts:**
*   [[Lock-Based Protocols]]
*   [[Deadlock]] (Possible under 2PL)
*   [[../Serializability of Scheduling]] / [[../Conflict Serializability]] (Guaranteed by 2PL)
*   [[../Recoverability]] / [[../Cascadeless Schedules]] (Require Strict/Rigorous 2PL)
*   [[../ACID Properties]] (Isolation) 