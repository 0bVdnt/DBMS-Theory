# Concurrency Control Schemes

Parent: [[../Transaction Processing Overview]]

#transaction #concurrency #protocols #locking #timestamp #validation #mvcc

Mechanisms used by a DBMS to ensure [[../Serializability of Scheduling|serializability]] (and usually [[../Recoverability|recoverability]]/[[../Cascadeless Schedules|cascadelessness]]) of [[../Concept of Schedule|concurrent schedules]], thus enforcing the [[../ACID Properties|Isolation]] property of [[../Transaction Concept|transactions]].

## Main Types of Schemes

*   [[Lock-Based Protocols]]
*   [[Timestamp-Based Protocols]]
*   [[Validation-Based Protocols (Optimistic)]]
*   [[Multiversion Concurrency Control (MVCC)]]

Also closely related:
*   [[../SQL Isolation Levels]] (Defines practical levels of isolation achieved)

---
**Related Concepts:**
*   [[../Serializability of Scheduling]] (The goal)
*   [[../ACID Properties]] (Isolation)
*   [[../Recoverability]]
*   [[../Cascadeless Schedules]]
*   [[../Concept of Schedule]]
*   [[../Transaction Concept]] 