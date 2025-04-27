# Checkpoints

Parent: [[Log-Based Recovery]]

#recovery #logging #checkpoint #performance

Mechanism used in [[Log-Based Recovery]] systems to reduce the amount of work needed during recovery after a system crash.

*   **Problem:** Without checkpoints, the recovery manager might need to process the *entire* log file from the beginning to determine which transactions need REDO/UNDO, which can be very time-consuming for long-running systems.
*   **Checkpoint Procedure (Simplified):**
    1.  Temporarily pause accepting new [[3 - Transaction Processing/Transaction Concept|transactions]].
    2.  Wait until all currently active transactions finish writing their log records for updates already performed.
    3.  Force-write all log records currently in memory buffers to the stable log file.
    4.  Force-write all modified database pages currently in memory buffers to the database disk.
    5.  Write a special `<CHECKPOINT L>` record to the stable log file, where `L` is the list of transactions active at the time of the checkpoint.
    6.  Resume normal transaction processing.
*   **Recovery Impact:** When recovering from a crash, the system only needs to:
    *   Find the last `<CHECKPOINT L>` record in the log.
    *   UNDO transactions that started *before* the checkpoint but didn't commit (are in `L` but have no later `<COMMIT>` record), and transactions that started *after* the checkpoint but didn't commit.
    *   REDO transactions that committed *after* the checkpoint, and transactions in `L` that committed *after* the checkpoint.
    *   Transactions that committed *before* the checkpoint require no action, as their changes are guaranteed to be on disk.
*   **Variations:** Different types exist (fuzzy checkpoints, etc.) to reduce the pause during checkpointing.

---
**Related Concepts:**
*   [[Log-Based Recovery]]
*   [[Write-Ahead Logging (WAL)]]
*   [[Database Recovery Overview]]
*   [[3 - Transaction Processing/ACID Properties|ACID Properties]]
*   [[3 - Transaction Processing/Transaction Concept|Transaction Concept]] 