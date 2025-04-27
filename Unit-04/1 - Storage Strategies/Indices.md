# Indices

Parent: [[Storage Strategies Overview]]

#storage #index

*   **Concept:** Data structures used to speed up data retrieval operations on database tables at the cost of additional writes and storage space. They allow the database system to find rows matching specific criteria without scanning the entire table.
*   **Purpose:** Primarily used to optimize `SELECT` queries, especially those with `WHERE` clauses, and also [[2 - Query Processing and Optimization/Join Strategies|JOIN operations]].
*   **Common Types:**
    *   *Primary Index:* Index on the primary key, often determines the physical order of data (if clustered). Usually unique.
    *   *Secondary Index:* Index on non-key attributes.
    *   *Clustered Index:* The physical order of rows on disk matches the index order. A table can have only one clustered index (often on the primary key).
    *   *Non-Clustered Index:* The index contains pointers to the actual data rows, which are stored elsewhere (e.g., in a heap or according to a clustered index). A table can have multiple non-clustered indices. Often implemented using [[B-Trees]].
    *   *Unique Index:* Ensures that the indexed column(s) contain no duplicate values.
    *   *Composite Index:* Index on multiple columns.
*   **Trade-offs:** Speed up reads but slow down `INSERT`, `UPDATE`, `DELETE` operations (as indices also need updating) and consume disk space.

---
**Related Concepts:**
*   [[B-Trees]] (Common implementation)
*   [[Hashing]] (Alternative structure for specific lookups)
*   [[2 - Query Processing and Optimization/Query Optimization Algorithms|Query Optimization Algorithms]] (Uses index information)
*   [[2 - Query Processing and Optimization/Join Strategies|Join Strategies]] (e.g., Index Nested-Loop Join)
*   [[3 - Transaction Processing/Concurrency Control Schemes/Phantom Problem|Phantom Problem]] (Related to locking ranges/predicates defined by indices)
*   [[3 - Transaction Processing/Concurrency Control Schemes/Concurrency Control Schemes|Concurrency Control]] for indices (e.g., [[3 - Transaction Processing/Concurrency Control Schemes/Lock-Based Protocols|Locking]] index nodes) 