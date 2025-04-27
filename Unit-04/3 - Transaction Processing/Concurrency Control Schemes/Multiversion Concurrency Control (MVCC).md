# Multiversion Concurrency Control (MVCC)

Parent: [[Concurrency Control Schemes]]

#transaction #concurrency #protocols #mvcc #snapshot

Maintains multiple versions of data items to increase concurrency, particularly allowing reads to proceed without blocking or being blocked by writes.

*   **Core Idea:** When a [[../Transaction Concept|transaction]] updates a data item, it creates a new version instead of overwriting the old one. Each version is typically timestamped with the ID/timestamp of the transaction that created it.
*   **Read Operations:** When a transaction reads a data item, the system selects the appropriate version based on the transaction's timestamp or start time (e.g., the most recent committed version that existed when the transaction started).
*   **Write Operations:** Create a new version. Concurrency control is still needed to manage conflicts between concurrent writes.

## Common MVCC Implementations

*   **MVCC Timestamp Ordering:** Uses [[Timestamp-Based Protocols|timestamps]] similar to TSO, but reads access older versions if a write with a later timestamp has occurred. Writes may still block or abort if they conflict with reads of older versions.
*   **MVCC Two-Phase Locking (MVCC 2PL):** Combines versioning with [[Two-Phase Locking (2PL)|locking]]. Reads access appropriate older versions without needing read locks (usually). Writes still acquire X locks on the *latest* version, potentially blocking other writers.
*   **Snapshot Isolation (SI):**
    *   A popular MVCC implementation (often the default in systems like PostgreSQL, Oracle).
    *   Each transaction reads data from a consistent *snapshot* of the database as it existed when the transaction started.
    *   Writes use a "first-committer wins" rule: If transaction T1 tries to commit an update to item X, but another concurrent transaction T2 has already committed an update to X since T1 started, T1 aborts.
    *   **Benefits:** Reads don't block writes, writes don't block reads. Avoids [[Phantom Problem|phantoms]] caused by inserts/deletes (reads see the start-time snapshot).
    *   **Drawback:** **Not truly serializable.** Susceptible to **write skew** anomaly (a type of [[Phantom Problem|phantom]] where two transactions read overlapping data, update disjoint parts based on those reads, and both commit, leading to an inconsistent state that wouldn't occur in any serial execution).
*   **Serializable Snapshot Isolation (SSI):** An extension of SI that detects potential write skew situations and aborts one of the transactions, thus ensuring true [[../Serializability of Scheduling|serializability]].

---
**Related Concepts:**
*   [[Concurrency Control Schemes]]
*   [[Timestamp-Based Protocols]]
*   [[Two-Phase Locking (2PL)]]
*   [[Phantom Problem]] (SI avoids some, but suffers write skew; SSI avoids all)
*   [[../SQL Isolation Levels]] (Snapshot is a common, though non-standard, level)
*   [[../Serializability of Scheduling]] (Achieved by some MVCC variants like SSI, but not basic SI)
*   [[../Transaction Concept]] 