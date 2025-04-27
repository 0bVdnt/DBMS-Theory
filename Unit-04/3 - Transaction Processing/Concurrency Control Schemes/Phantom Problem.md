# Phantom Problem

Parent: [[Lock-Based Protocols]]

#transaction #concurrency #protocols #locking #phantom #problem

*   **Problem:** Arises when using [[Lock-Based Protocols|record-level locking]]. A [[../Transaction Concept|transaction]] (T1) reads a set of tuples satisfying some search condition (predicate), another transaction (T2) then inserts or deletes a tuple that matches the condition, and T1 repeats its read, finding a different set of tuples (a "phantom" tuple appeared or disappeared).
*   **Why it's a problem:** Violates [[../ACID Properties|Isolation]], specifically the [[../SQL Isolation Levels|Repeatable Read]] and [[../SQL Isolation Levels|Serializable]] levels, as the results of the query changed within the same transaction.
*   **Why basic record locking fails:** T1 locks the records it *initially* finds, but doesn't lock the *potential* records that might be inserted later matching its predicate.

## Solutions

*   **Predicate Locking:** Lock the search condition (predicate) itself. Conceptually simple but hard to implement efficiently.
*   **Index Locking / Next-Key Locking:** Lock the relevant index entries corresponding to the query predicate. If the predicate involves a range, lock the index entries covering that range, potentially including the "gap" after the last matching entry (next-key locking) to prevent insertions within the range.
*   **Table Lock:** Simplest but least concurrent: lock the entire table.
*   [[Multiversion Concurrency Control (MVCC)|MVCC]] with Snapshot Isolation can avoid some phantoms but may suffer from [[Multiversion Concurrency Control (MVCC)|write skew]], which is similar. [[Multiversion Concurrency Control (MVCC)|Serializable Snapshot Isolation (SSI)]] aims to prevent this.

---
**Related Concepts:**
*   [[Lock-Based Protocols]]
*   [[Two-Phase Locking (2PL)]]
*   [[../SQL Isolation Levels]] (Repeatable Read, Serializable are affected)
*   [[Multiversion Concurrency Control (MVCC)]]
*   [[../../1 - Storage Strategies/Indices|Indices]] (Index locking is a common solution)
*   [[../ACID Properties]] (Isolation)
*   [[../Transaction Concept]] 