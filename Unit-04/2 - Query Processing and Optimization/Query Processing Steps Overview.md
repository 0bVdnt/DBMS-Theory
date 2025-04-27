# Query Processing Steps Overview

Parent: [[Query Processing Overview]]

#query #optimization

Overall flow of handling a user query:

1.  **Parsing and Translation:** Check SQL syntax, verify table/attribute names, translate SQL into an internal representation (often a relational algebra expression tree).
2.  **Optimization:** Use [[Query Optimization Algorithms]] to find the most efficient way to execute the query among many [[Query Equivalence|equivalent plans]].
3.  **Evaluation:** Execute the chosen plan using [[Evaluation of Relational Algebra Expressions|operator evaluation]] techniques and return results.

---
**Related Concepts:**
*   [[Query Optimization Algorithms]]
*   [[Evaluation of Relational Algebra Expressions]]
*   [[Query Equivalence]] 