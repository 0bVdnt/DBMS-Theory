# Database Statistics

Parent: [[Query Processing Overview]]

#query #optimization #statistics

Information maintained by the DBMS about the data, crucial for **cost estimation** in [[Query Optimization Algorithms|cost-based query optimization]].

*   **Types of Statistics:**
    *   Relation size (number of tuples, number of blocks/pages).
    *   Attribute cardinalities (number of distinct values for each attribute).
    *   Value distributions (histograms showing frequency of different value ranges).
    *   [[1 - Storage Strategies/Indices|Index information]] (height of B-tree, number of leaf pages).
*   **Purpose:** Allow the optimizer to estimate the size of intermediate results and the cost (e.g., I/Os) of different operations (like scans, joins) for various execution plans.
*   **Maintenance:** Statistics can become outdated as data changes. DBMS typically provides commands to update statistics (e.g., `ANALYZE` in PostgreSQL, `UPDATE STATISTICS` in SQL Server). Keeping statistics current is vital for good query performance.

---
**Related Concepts:**
*   [[Query Optimization Algorithms]] (Uses statistics for cost estimation)
*   [[Evaluation of Relational Algebra Expressions]] (Costs being estimated)
*   [[Join Strategies]] (Cost depends on relation sizes, etc.)
*   [[1 - Storage Strategies/Indices|Indices]] (Statistics are kept about indices too) 