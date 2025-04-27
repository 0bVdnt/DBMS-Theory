# Query Optimization Algorithms

Parent: [[Query Processing Overview]]

#query #optimization #costbased #heuristic

*   **Goal:** Select the [[Evaluation of Relational Algebra Expressions|execution plan]] with the minimum estimated cost during the Optimization phase of [[Query Processing Steps Overview]].
*   **Cost Estimation:** Estimate the cost (typically disk I/Os, sometimes CPU/network) of different plans/operators. Relies heavily on [[Database Statistics]].
*   **Optimization Approaches:**
    *   **Heuristic/Rule-Based:** Apply [[Query Equivalence|equivalence rules]] in a fixed order (e.g., always push selections down). Fast but may not find the optimal plan.
    *   **Cost-Based:**
        1.  Enumerate potential plans using [[Query Equivalence|equivalence rules]] (e.g., different [[Join Strategies|join orders]], algorithms, access paths like [[1 - Storage Strategies/Indices|index scans]]).
        2.  Estimate the cost of each plan using [[Database Statistics]].
        3.  Choose the plan with the lowest estimated cost.
        4.  Search space can be huge. Often uses techniques like **dynamic programming** or randomized algorithms to explore the space efficiently.

---
**Related Concepts:**
*   [[Query Processing Steps Overview]]
*   [[Evaluation of Relational Algebra Expressions]] (The plans being optimized)
*   [[Query Equivalence]] (Rules used to generate plans)
*   [[Join Strategies]] (Algorithm choices influencing cost)
*   [[Database Statistics]] (Crucial input for cost estimation)
*   [[1 - Storage Strategies/Indices|Indices]] (Information used in cost estimation) 