# Log-Based Recovery

Parent: [[Database Recovery Overview]]

#recovery #logging #wal #undo #redo

The most common approach to [[Database Recovery Overview|database recovery]]. Relies on maintaining a log file containing information about all database modifications.

*   **Log File:** An ordered sequence of log records stored on stable storage (resists crashes).
*   **Log Records:** Contain information necessary to UNDO or REDO database changes. Common fields include:
    *   Transaction ID
    *   Operation Type (e.g., UPDATE, INSERT, DELETE)
    *   Data Item Identifier (e.g., Page ID, Row ID)
    *   Old Value (Before Image - for UNDO)
    *   New Value (After Image - for REDO)
    *   Special records: `<START>`, `<COMMIT>`, `<ABORT>`, `<CHECKPOINT>`
*   **Fundamental Principle: [[Write-Ahead Logging (WAL)]]**
*   **Recovery Actions (Post-Crash):** The recovery manager analyzes the log (typically starting from the last [[Checkpoints|Checkpoint]]) to determine the status of transactions active at the time of the crash.
    *   **UNDO:** Revert changes made by transactions that did *not* commit before the crash (using old values from log records). Ensures [[3 - Transaction Processing/ACID Properties|Atomicity]].
    *   **REDO:** Re-apply changes made by transactions that *did* commit before the crash (using new values from log records). Ensures [[3 - Transaction Processing/ACID Properties|Durability]], as some changes might not have reached the database disk before the crash.
*   **Variations:**
    *   *Immediate Modification:* Allows database updates to disk before commit. Recovery requires both UNDO and REDO.
    *   *Deferred Modification:* Database updates written to disk only at commit time. Recovery requires only REDO (no UNDO needed, as uncommitted changes never hit the disk).

---
**Related Concepts:**
*   [[Database Recovery Overview]]
*   [[Write-Ahead Logging (WAL)]]
*   [[Checkpoints]]
*   [[Shadow Paging]] (Alternative)
*   [[3 - Transaction Processing/ACID Properties|ACID Properties]] (Atomicity, Durability)
*   [[3 - Transaction Processing/Transaction Concept|Transaction Concept]] 