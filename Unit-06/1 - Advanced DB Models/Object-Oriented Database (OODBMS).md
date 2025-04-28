# Object-Oriented Database (OODB / OODBMS)

*   **Concept:** Database systems designed to work directly with object-oriented programming concepts (classes, objects, inheritance, methods/behavior). Objects are stored persistently.
*   **Core Idea:** Overcomes the "[[Impedance Mismatch]]" between object-oriented languages (like Java, C++) and [[Relational Database Management System (RDBMS)|relational databases]], which require mapping objects to tables/rows. Provides a single language interface.
*   **Features & Advantages:**
    *   *Enriched Modeling:* Models complex real-world entities naturally using objects, encapsulation, and inheritance.
    *   *Extensibility:* Allows defining new data types (classes inheriting from superclasses), promoting reuse.
    *   *Handling Variety of Data Types:* Can store diverse data types (text, numbers, multimedia).
    *   *Expressive Query Language:* Often uses navigational access (object references), potentially more intuitive than [[SQL]]. Some offer object-oriented SQL variants (OQL).
    *   *[[Schema Evolution]]:* Potentially easier schema changes due to tight coupling.
    *   *Support for Long-Duration Transactions:* Better suited for long transactions (e.g., CAD/CASE) than traditional RDBMS locking (potentially relaxing [[ACID Properties]] in some interpretations or using different concurrency models).
    *   *Improved Performance (for certain tasks):* Can offer performance gains for complex, navigation-heavy operations.
*   **Disadvantages:**
    *   Lack of Universal Data Model/Standard Query Language.
    *   Less widespread adoption/experience than [[Relational Database Management System (RDBMS)|RDBMS]].
    *   Competition from [[Relational Database Management System (RDBMS)|RDBMS]] and [[Object-Relational Database (ORDBMS)]].
    *   Query optimization complexity.
    *   Potential locking issues.
    *   Complexity & Cost.
    *   Limited view/security support compared to mature [[Relational Database Management System (RDBMS)|RDBMS]].

Contrast with: [[Relational Database Management System (RDBMS)]], [[Object-Relational Database (ORDBMS)]]

---
Tags: #oodbms #database-model #object-oriented #impedance-mismatch #schema-evolution #acid 