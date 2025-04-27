# SQL Isolation Levels

Parent: [[../Transaction Processing Overview]]

#transaction #concurrency #isolation #sql

Standard levels defined in SQL that specify the degree of [[../ACID Properties|Isolation]] between concurrent [[../Transaction Concept|transactions]]. They define which concurrency phenomena (anomalies) are permissible at each level.

## Phenomena:

*   **Dirty Read:** Reading data written by a transaction that has not yet committed (and might abort). Prevented by [[../Recoverability|Recoverability]].
*   **Non-Repeatable Read:** Re-reading a data item within the same transaction yields a different value because another committed transaction modified it.
*   **Phantom Read:** Re-executing a query with a predicate within the same transaction yields a different set of rows because another committed transaction inserted/deleted rows matching the predicate. (See [[Concurrency Control Schemes/Phantom Problem|Phantom Problem]]).

## Standard Levels (Lowest to Highest Isolation):

1.  **Read Uncommitted:**
    *   Allows: Dirty Reads, Non-Repeatable Reads, Phantoms.
    *   Offers highest concurrency but lowest consistency guarantees.
2.  **Read Committed:**
    *   Prevents: Dirty Reads.
    *   Allows: Non-Repeatable Reads, Phantoms.
    *   Common default level. Often implemented by holding short-term read locks or using [[Concurrency Control Schemes/Multiversion Concurrency Control (MVCC)|MVCC]].
3.  **Repeatable Read:**
    *   Prevents: Dirty Reads, Non-Repeatable Reads.
    *   Allows: Phantoms.
    *   Often implemented by holding read locks until commit or using [[Concurrency Control Schemes/Multiversion Concurrency Control (MVCC)|MVCC Snapshot Isolation]].
4.  **Serializable:**
    *   Prevents: Dirty Reads, Non-Repeatable Reads, Phantoms.
    *   Highest isolation level, guarantees execution is equivalent to some [[../Concept of Schedule|serial schedule]].
    *   Typically implemented using strict [[Concurrency Control Schemes/Two-Phase Locking (2PL)|Two-Phase Locking]] (with predicate/index locking) or [[Concurrency Control Schemes/Multiversion Concurrency Control (MVCC)|Serializable Snapshot Isolation]]. Can significantly reduce concurrency.

## Non-Standard Level:

*   **Snapshot Isolation (SI):**
    *   Provided by many [[Concurrency Control Schemes/Multiversion Concurrency Control (MVCC)|MVCC]] systems.
    *   Prevents: Dirty Reads, Non-Repeatable Reads, *most* Phantoms (those caused by inserts/deletes).
    *   Allows: Write Skew (a specific type of phantom anomaly).
    *   Fits between Repeatable Read and Serializable in terms of guarantees/phenomena prevented, but is not part of the SQL standard hierarchy.

---
**Related Concepts:**
*   [[../ACID Properties]] (Isolation)
*   [[Concurrency Control Schemes/Concurrency Control Schemes|Concurrency Control Schemes]] (Implement these levels)
*   [[../Serializability of Scheduling]] (Corresponds to Serializable level)
*   [[../Recoverability]] (Related to preventing Dirty Reads)
*   [[Concurrency Control Schemes/Phantom Problem]]
*   [[Concurrency Control Schemes/Multiversion Concurrency Control (MVCC)|Multiversion Concurrency Control (MVCC)]]
*   [[Concurrency Control Schemes/Two-Phase Locking (2PL)|Two-Phase Locking (2PL)]]
*   [[../Transaction Concept]] 