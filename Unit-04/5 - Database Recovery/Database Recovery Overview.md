# Database Recovery Overview

Parent: [[UNIT-IV Overview]]

#recovery #logging #acid #durability #atomicity

This section covers mechanisms and techniques used to restore the database to a consistent state after various types of failures, ensuring [[3 - Transaction Processing/ACID Properties|Atomicity]] and [[3 - Transaction Processing/ACID Properties|Durability]].

## Types of Failures

*   Transaction failure (logical error, deadlock abort)
*   System crash (power loss, OS failure)
*   Disk failure (head crash, data corruption)

## Key Techniques & Concepts

*   [[Log-Based Recovery]] (Most common approach)
    *   [[Write-Ahead Logging (WAL)]] (Fundamental principle)
    *   Log Records
    *   UNDO / REDO operations
    *   [[Checkpoints]] (To reduce recovery time)
*   [[Shadow Paging]] (Alternative approach)

---
**Related Concepts:**
*   [[3 - Transaction Processing/ACID Properties|ACID Properties]] (Atomicity, Durability are the primary goals)
*   [[3 - Transaction Processing/Transaction Concept|Transaction Concept]] (The unit of work being recovered)
*   [[3 - Transaction Processing/Recoverability|Recoverability]] / [[3 - Transaction Processing/Cascadeless Schedules|Cascadeless Schedules]] (Properties that simplify recovery) 