# Shadow Paging

Parent: [[Database Recovery Overview]]

#recovery #shadowpaging #alternative

An alternative [[Database Recovery Overview|recovery]] technique to [[Log-Based Recovery]], less commonly used in modern high-performance databases.

*   **Core Idea:** Maintain two page tables during the life of a [[3 - Transaction Processing/Transaction Concept|transaction]]: the *current* page table and the *shadow* page table.
    *   The shadow page table points to the database pages on disk *before* the transaction started (the consistent state).
    *   When the transaction modifies a page, a *copy* of that page is made, and the *current* page table is updated to point to this new copy. The shadow page table remains unchanged, pointing to the original page.
*   **Commit:** To commit the transaction:
    1.  Make the current page table the new shadow page table (atomically, usually by updating a single pointer on disk).
    2.  Discard the old shadow page table.
*   **Abort / Crash Recovery:** To abort the transaction or recover from a crash:
    1.  Discard the current page table (containing pointers to modified pages).
    2.  Reinstate the shadow page table (which still points to the original, unmodified pages).
*   **Advantages:**
    *   UNDO operations are essentially free (just discard the current page table).
    *   No need for complex log processing for UNDO.
*   **Disadvantages:**
    *   **Commit Overhead:** Writing modified pages can be costly.
    *   **Data Fragmentation:** Modified pages can end up scattered on disk.
    *   **Garbage Collection:** Need to reclaim the old, now unused pages.
    *   **Concurrency:** Difficult to extend efficiently to handle multiple concurrent transactions.
    *   REDO operations might still be needed if committed pages weren't fully flushed before a crash, adding complexity.

---
**Related Concepts:**
*   [[Database Recovery Overview]]
*   [[Log-Based Recovery]] (Contrasting, more common approach)
*   [[3 - Transaction Processing/ACID Properties|ACID Properties]] (Atomicity, Durability)
*   [[3 - Transaction Processing/Transaction Concept|Transaction Concept]] 