# Timestamp-Based Protocols

Parent: [[Concurrency Control Schemes]]

#transaction #concurrency #protocols #timestamp #tso

Ensure [[../Serializability of Scheduling|serializability]] by ordering [[../Transaction Concept|transaction]] operations based on unique timestamps assigned to each transaction.

*   **Timestamp Assignment:** Each transaction `Ti` gets a unique timestamp `TS(Ti)` when it starts (typically system clock value or counter).
*   **Timestamp Ordering (TSO) Protocol:**
    *   Each data item `Q` maintains:
        *   `W-TS(Q)`: Largest timestamp of any transaction that successfully wrote `Q`.
        *   `R-TS(Q)`: Largest timestamp of any transaction that successfully read `Q`.
    *   **Read Operation (`read(Q)` by `Ti`):**
        *   If `TS(Ti) < W-TS(Q)`, `Ti` needs to read a value already overwritten. Abort `Ti`.
        *   Otherwise, execute read, update `R-TS(Q) = max(R-TS(Q), TS(Ti))`.
    *   **Write Operation (`write(Q)` by `Ti`):**
        *   If `TS(Ti) < R-TS(Q)`, `Ti`'s write is too late (value needed by later read). Abort `Ti`.
        *   If `TS(Ti) < W-TS(Q)`, `Ti` is writing an obsolete value (Stale Write). Abort `Ti` (**unless using Thomas' Write Rule**).
        *   Otherwise, execute write, update `W-TS(Q) = TS(Ti)`.
*   **Thomas' Write Rule:** Modification to TSO. If `TS(Ti) < W-TS(Q)` during a write, simply ignore the write (treat as NOP) instead of aborting `Ti`. Preserves [[../View Serializability|view serializability]] but not [[../Conflict Serializability|conflict serializability]].
*   **Advantages:**
    *   Guarantees [[../Serializability of Scheduling|serializability]] (timestamp order corresponds to a serial order).
    *   Deadlock-free (transactions wait or abort, never form cycles).
*   **Disadvantages:**
    *   Can suffer from [[../Cascading Rollbacks]] if not modified (e.g., requires reads to wait for writes with smaller TS to commit).
    *   May cause more aborts than locking, especially in high-conflict workloads.

---
**Related Concepts:**
*   [[Concurrency Control Schemes]]
*   [[../Serializability of Scheduling]]
*   [[../Conflict Serializability]] / [[../View Serializability]]
*   [[../Recoverability]] / [[../Cascading Rollbacks]]
*   [[../Transaction Concept]]
*   [[Deadlock]] (Avoided by TSO) 