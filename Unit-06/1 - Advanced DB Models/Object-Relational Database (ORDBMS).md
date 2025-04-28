# Object-Relational Database (ORDBMS)

*   **Concept:** A hybrid approach extending the [[Relational Database Management System (RDBMS)|relational model]] with object-oriented features. Aims to leverage the stability of [[Relational Database Management System (RDBMS)|RDBMS]] while incorporating richer data modeling.
*   **Core Idea:** Add support for complex objects, [[User-Defined Types (UDTs)]], inheritance, and methods/functions directly within the [[SQL]]/relational framework.
*   **Features:**
    *   Retains relational foundation (tables, [[SQL]]).
    *   Supports complex data types (e.g., arrays, ROW types).
    *   Allows [[User-Defined Types (UDTs)]] and associated methods/functions usable in [[SQL]] queries.
    *   Supports type inheritance (subtypes).
    *   Can store methods (procedures, triggers) in the database.
*   **Advantages:**
    *   *Reuse and Sharing:* Leverages existing relational technology and experience.
    *   *Increased Productivity:* Richer modeling than pure [[Relational Database Management System (RDBMS)|RDBMS]].
    *   *Evolutionary Path:* Gradual adoption of OO features for [[Relational Database Management System (RDBMS)|RDBMS]] users.
*   **Disadvantages:**
    *   Complexity and Cost.
    *   Loss of Simplicity compared to the pure relational model.
    *   Potential [[Impedance Mismatch|semantic gap]] still exists with true OO applications.

Contrast with: [[Relational Database Management System (RDBMS)]], [[Object-Oriented Database (OODBMS)]]

---
Tags: #ordbms #database-model #object-relational #sql #udt #rdbms 