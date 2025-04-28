# Scalability: Horizontal vs Vertical

Scalability refers to a system's ability to handle growing amounts of work or its potential to be enlarged to accommodate that growth.

## Horizontal Scaling (Scale-Out)

*   **Definition**: Adding more commodity servers (nodes) to a system to distribute the load.
*   **Approach**: Distributes data and workload across multiple machines.
*   **Pros**: Can scale almost indefinitely (theoretically), often more cost-effective using standard hardware, improves fault tolerance (if one node fails, others continue).
*   **Cons**: Increased management complexity, potential [[Consistency]] challenges in distributed systems.
*   **Association**: Preferred model for [[NoSQL Databases|NoSQL databases]] designed for [[Distributed Database Model|distributed environments]].

## Vertical Scaling (Scale-Up)

*   **Definition**: Increasing the resources (CPU, RAM, Disk) of a single server.
*   **Approach**: Making a single machine more powerful.
*   **Pros**: Simpler to manage (single system), maintains strong [[Consistency]] easier.
*   **Cons**: Hardware limits (physical maximums), expensive high-end hardware, single point of failure.
*   **Association**: Traditional approach for [[RDBMS]], though many now incorporate horizontal scaling techniques too.

See also: [[Distributed Database Model]], [[Motivation for NoSQL]], [[SQL vs NoSQL Comparison]]

---
Tags: #scalability #distributed #horizontalscaling #verticalscaling #scaleout #scaleup #nosql #rdbms 