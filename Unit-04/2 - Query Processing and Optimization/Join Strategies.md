# Join Strategies

Parent: [[Query Processing Overview]]

#query #optimization #join #nlj #smj #hashjoin

Algorithms for implementing the join (`⋈`) operator during [[Evaluation of Relational Algebra Expressions|query evaluation]]. Choosing the right strategy is critical for [[Query Optimization Algorithms|query optimization]].

*   **Nested-Loop Join (NLJ):** For each tuple in the outer relation, iterate through all tuples in the inner relation.
    *   *Block Nested-Loop:* Process relations block by block to improve I/O.
    *   *Cost:* Proportional to `|R| * |S|`. Can be very slow.
*   **Index Nested-Loop Join (INLJ):** For each tuple in the outer relation, use an [[1 - Storage Strategies/Indices|index]] on the join attribute of the inner relation to find matching tuples quickly.
    *   *Cost:* Depends on outer relation size and index lookup cost. Good if index exists and is selective.
*   **Sort-Merge Join (SMJ):** Sort both relations on the join attribute(s), then scan through the sorted relations and merge matching tuples.
    *   *Cost:* Dominated by sorting cost (often `O(N log N)`). Efficient for equi-joins and if relations are already sorted. Handles non-equi-joins (e.g., `<`).
*   **Hash Join (HJ):** Uses [[1 - Storage Strategies/Hashing|hashing]].
    *   *Partitioning (Build) Phase:* Hash the smaller relation (build input) into in-memory hash buckets based on the join attribute.
    *   *Probing Phase:* Hash the larger relation (probe input) tuple by tuple; for each tuple, probe the corresponding hash bucket from the build phase for matches.
    *   *Cost:* Roughly linear `O(|R| + |S|)`. Very efficient for large equi-joins, assuming the build input fits reasonably in memory (or requires recursive partitioning).

---
**Related Concepts:**
*   [[Evaluation of Relational Algebra Expressions]] (Where joins are executed)
*   [[Query Optimization Algorithms]] (Selects the best join strategy)
*   [[Query Equivalence]] (Allows reordering joins)
*   [[1 - Storage Strategies/Indices|Indices]] (Used by INLJ)
*   [[1 - Storage Strategies/Hashing|Hashing]] (Used by Hash Join) 