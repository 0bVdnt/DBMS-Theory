# BASE Properties

BASE is an alternative model to [[ACID Properties|ACID]], often associated with [[CAP Theorem|AP NoSQL systems]] that prioritize [[Availability]] over strong [[Consistency]].

It stands for:

*   **Basically Available**: The system guarantees [[Availability]] (responds to requests), as per the [[CAP Theorem]] (prioritizes A over C).
*   **Soft State**: The state of the system may change over time, even without new input, due to [[Eventual Consistency]]. Data might be inconsistent across nodes temporarily.
*   **Eventually Consistent**: If no new updates are made, eventually all replicas will converge to the same value. [[Consistency]] is achieved over time, not instantaneously.

Contrast with: [[ACID Properties]] (strong consistency)
See also: [[CAP Theorem]], [[Eventual Consistency]], [[NoSQL Databases]]

---
Tags: #distributed #base #consistency #availability #eventual-consistency #nosql #acid #theory 