# Write-Ahead Logging (WAL)

Parent: [[Log-Based Recovery]]

#recovery #logging #wal #durability #atomicity

A fundamental principle required for [[Log-Based Recovery]] to work correctly, ensuring [[3 - Transaction Processing/ACID Properties|Atomicity]] and [[3 - Transaction Processing/ACID Properties|Durability]].

*   **The Rule:** Before a data block (page) containing changes made by a [[3 - Transaction Processing/Transaction Concept|transaction]] is allowed to be written to the database disk (stable storage), the corresponding **log record(s)** describing those changes *must* be written to the stable log file first.
*   **Why it's critical:**
    *   **Ensuring Atomicity (UNDO):** If a crash occurs after a change hits the database disk but *before* the transaction commits, the log record (containing the old value) *must* be available on stable storage to allow the recovery manager to UNDO the change.
    *   **Ensuring Durability (REDO):** If a transaction commits (meaning its commit log record is on stable storage) but a crash occurs *before* all its changes hit the database disk, the log records (containing the new values) *must* be available on stable storage to allow the recovery manager to REDO the changes.

In short, the log acts as the definitive record of what happened and what needs to be done to restore consistency after a crash.

---
**Related Concepts:**
*   [[Log-Based Recovery]] (WAL is essential for it)
*   [[Checkpoints]]
*   [[Database Recovery Overview]]
*   [[3 - Transaction Processing/ACID Properties|ACID Properties]] (Atomicity, Durability)
*   [[3 - Transaction Processing/Transaction Concept|Transaction Concept]] 