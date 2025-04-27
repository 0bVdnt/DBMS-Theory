# Evaluation of Relational Algebra Expressions

Parent: [[Query Processing Overview]]

#query #optimization #algebra #execution

Implementing the relational algebra operators during the Evaluation phase of [[Query Processing Steps Overview]]:

*   **Selection (`σ`):**
    *   *File Scan:* Read the entire relation (linear scan). Necessary if no index or condition involves non-indexed attributes.
    *   *Index Scan:* Use an [[1 - Storage Strategies/Indices|index]] (e.g., [[1 - Storage Strategies/B-Trees|B+-tree]] or [[1 - Storage Strategies/Hashing|hash]]) if the selection condition involves indexed attributes (e.g., `id = 10`, `salary > 50000`). Much faster for selective conditions.
*   **Projection (`Π`):** Read tuples, extract specified attributes. May require duplicate elimination (using sorting or hashing).
*   **Join (`⋈`):** Combine tuples from two relations based on a condition. Computationally expensive. See [[Join Strategies]].
*   **Other Operators:** Set operations (Union, Intersection, Difference), Aggregation (SUM, COUNT, AVG, etc.), Sorting – implemented using various algorithms, often involving sorting or hashing.
*   **Evaluation Models:**
    *   *Materialization:* Execute one operator at a time, storing intermediate results on disk/memory. Simple but potentially high I/O cost.
    *   *Pipelining:* Pass results from one operator directly to the next without storing intermediate results. Reduces I/O but requires careful coordination.

---
**Related Concepts:**
*   [[Query Processing Steps Overview]]
*   [[Query Optimization Algorithms]] (Chooses which operators and strategies to use)
*   [[Query Equivalence]] (Allows rearranging operators)
*   [[Join Strategies]] (Specific algorithms for the join operator)
*   [[1 - Storage Strategies/Indices|Indices]] (Used for efficient selection/join) 