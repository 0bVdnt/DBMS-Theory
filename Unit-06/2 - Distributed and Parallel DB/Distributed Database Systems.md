# Distributed Database Systems

*   **Goal:** Allow data to be physically stored across multiple, potentially geographically dispersed, sites (nodes) that are loosely coupled. Sites might be autonomous.
*   **Focus:** Data sharing, local autonomy, increased [[Availability]]/reliability by distributing data. (See also [[Distributed Database Model]] from Unit V).
*   **Architectures:**
    *   *Homogeneous:* All sites run the same DBMS type.
    *   *Heterogeneous:* Sites run different DBMS types (requires gateways/mediators).
*   **[[Transparency]]**: Aim to hide distribution details (location, replication, fragmentation).
*   **Key Challenges:**
    *   [[Distributed Query Processing]]
    *   [[Distributed Transactions]] (e.g., [[Two-Phase Commit (2PC)]])
    *   [[Consistency]] across replicas (related to [[CAP Theorem]], [[BASE Properties]])
    *   Catalog management.

See also: [[Parallel Database Systems]], [[Parallel vs Distributed DB Comparison]], [[Distributed Database Model]], [[Scalability (Horizontal vs Vertical)]], [[Consistency]], [[Availability]], [[Transparency]]

---
Tags: #distributed-db #database #architecture #availability #autonomy #homogeneous #heterogeneous #transparency #distributed-query #distributed-transaction #consistency #cap-theorem 