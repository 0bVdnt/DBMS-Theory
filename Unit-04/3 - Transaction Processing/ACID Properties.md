# ACID Properties

Parent: [[Transaction Processing Overview]]

#transaction #acid #consistency #isolation

Fundamental properties guaranteed by [[Transaction Concept|transaction]] management:

*   **Atomicity:** A transaction's operations are performed "all or nothing." If any part fails, the entire transaction is rolled back. Primarily ensured by the [[5 - Database Recovery/Database Recovery Overview|Recovery]] system (e.g., UNDO logs).
*   **Consistency:** A transaction transforms the database from one valid state to another, preserving database integrity constraints (e.g., sum of balances remains constant in a transfer). Ensured by programmer logic combined with [[Concurrency Control Schemes/Concurrency Control Schemes|Concurrency Control]] (preventing interference) and [[5 - Database Recovery/Database Recovery Overview|Recovery]] (undoing invalid states).
*   **Isolation:** Concurrent transactions do not interfere with each other. Each transaction appears to execute in isolation from others. Intermediate results are hidden. Ensured by [[Concurrency Control Schemes/Concurrency Control Schemes|Concurrency Control Schemes]]. The degree of isolation can often be configured via [[SQL Isolation Levels]].
*   **Durability:** Once a transaction commits successfully, its changes are permanent and survive subsequent system failures (e.g., crashes). Primarily ensured by the [[5 - Database Recovery/Database Recovery Overview|Recovery]] system (e.g., forcing log records to stable storage - [[5 - Database Recovery/Write-Ahead Logging (WAL)|WAL]], REDO logs).

---
**Related Concepts:**
*   [[Transaction Concept]] (The unit these properties apply to)
*   [[Serializability of Scheduling]] (The formal basis for Isolation)
*   [[Concurrency Control Schemes/Concurrency Control Schemes|Concurrency Control Schemes]] (Mechanisms to enforce Isolation)
*   [[5 - Database Recovery/Database Recovery Overview|Database Recovery]] (Mechanisms to enforce Atomicity and Durability)
*   [[SQL Isolation Levels]] (Practical levels of Isolation) 