# Validation-Based Protocols (Optimistic)

Parent: [[Concurrency Control Schemes]]

#transaction #concurrency #protocols #validation #optimistic

Assumes conflicts between [[../Transaction Concept|transactions]] are rare and allows transactions to execute without acquiring locks, validating them only at commit time.

*   **Philosophy:** "Ask for forgiveness, not permission."
*   **Phases:**
    1.  **Read Phase:** Transaction reads values from the database, computes, and writes updates to *private temporary variables*, not directly to the database.
    2.  **Validation Phase:** At commit time, check if the transaction's execution has conflicted with any other recently committed transactions. Check if its read/write sets overlap in conflicting ways with transactions that committed since it started.
    3.  **Write Phase:** If validation succeeds, make the temporary updates permanent in the database. If validation fails, abort the transaction.
*   **Validation Check:** Uses transaction timestamps (start, validation, finish times) to check for potential [[../Conflict Serializability|conflicts]] (Read/Write or Write/Write) with transactions that committed between the validating transaction's start and validation phases.
*   **Advantages:**
    *   High concurrency if conflicts are indeed rare (no waiting for locks).
    *   Deadlock-free.
*   **Disadvantages:**
    *   Potential for significant wasted work if validation fails often (starvation possible for long transactions).
    *   Validation phase can be complex and become a bottleneck.
    *   Best suited for read-heavy workloads.

---
**Related Concepts:**
*   [[Concurrency Control Schemes]]
*   [[../Serializability of Scheduling]] (Validation ensures this)
*   [[../Conflict Serializability]]
*   [[../Transaction Concept]]
*   [[Deadlock]] (Avoided) 