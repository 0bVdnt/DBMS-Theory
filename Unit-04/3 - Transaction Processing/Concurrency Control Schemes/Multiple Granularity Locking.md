# Multiple Granularity Locking (MGL)

Parent: [[Lock-Based Protocols]]

#transaction #concurrency #protocols #locking #granularity

Allows [[Lock-Based Protocols|locking]] items at different levels of a hierarchy (e.g., Database > Table > Page > Row) to optimize locking overhead.

*   **Problem:** Locking only at the finest granularity (e.g., row) can incur high overhead if a [[../Transaction Concept|transaction]] needs to access many rows in a table. Locking only at the coarsest granularity (e.g., table) limits concurrency unnecessarily.
*   **Solution:** Introduce **Intention Locks** placed on higher levels of the hierarchy to signal that locking is happening at a lower level. This prevents conflicts, e.g., prevents granting an X lock on a table if some transaction holds an S lock on a row within that table.
*   **Intention Lock Modes:**
    *   **Intention Shared (IS):** Indicates intent to place S locks at lower levels.
    *   **Intention Exclusive (IX):** Indicates intent to place X *or* S locks at lower levels.
    *   **Shared Intention Exclusive (SIX):** Indicates the current node is locked in S mode, and there's an intent to place X locks at lower levels (e.g., scan table with S lock, update specific rows with X locks).
*   **Compatibility:** Intention locks are compatible with each other (IS/IS, IS/IX, IX/IX) but conflict with actual S/X locks according to specific rules (e.g., an X lock on a table conflicts with any IS/IX/S/X lock request on it).
*   **Protocol:** To lock a node in S or IS mode, must hold at least IS on parent. To lock a node in X, IX, or SIX mode, must hold at least IX or SIX on parent. Locks are released bottom-up.

---
**Related Concepts:**
*   [[Lock-Based Protocols]]
*   [[Two-Phase Locking (2PL)]] (MGL is typically used with 2PL)
*   [[../Transaction Concept]]
*   [[../ACID Properties]] (Isolation) 