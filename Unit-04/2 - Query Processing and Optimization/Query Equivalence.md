# Query Equivalence

Parent: [[Query Processing Overview]]

#query #optimization #algebra

*   **Concept:** Different relational algebra expressions can be logically equivalent (produce the same result for any valid database state).
*   **Goal:** The [[Query Optimization Algorithms|optimizer]] uses equivalence rules to transform an initial query plan (algebra expression) into potentially cheaper equivalent plans during the [[Query Processing Steps Overview|Optimization phase]].
*   **Key Rules:**
    *   *Commutativity/Associativity:* [[Join Strategies|Joins]], unions, intersections can often be reordered.
    *   *Selection Pushdown:* Perform selections (`σ`) as early as possible to reduce intermediate relation sizes. `σ_p(R ⋈ S) ≡ σ_p(R) ⋈ S` (if p only involves R attributes).
    *   *Projection Pushdown:* Perform projections (`Π`) early to reduce the number of attributes carried along.
    *   Transform `σ (R × S)` into `R ⋈ S`.

---
**Related Concepts:**
*   [[Query Optimization Algorithms]] (Utilizes these rules)
*   [[Evaluation of Relational Algebra Expressions]] (Operators being rearranged)
*   [[Query Processing Steps Overview]] 