# Serializability of Scheduling

Parent: [[Transaction Processing Overview]]

#transaction #concurrency #serializability #schedule

*   **Concept:** A [[Concept of Schedule|concurrent schedule]] is **serializable** if it is equivalent (in terms of its effect on the database) to some [[Concept of Schedule|serial schedule]].
*   **Goal:** This is the primary criterion for correctness in concurrent execution, ensuring [[ACID Properties|Isolation]]. [[Concurrency Control Schemes/Concurrency Control Schemes|Concurrency control schemes]] aim to produce only serializable schedules.

## Types of Serializability

*   [[Conflict Serializability]]: Easier to test, widely used in practice.
*   [[View Serializability]]: More general but harder to test.

## Testing

*   [[Testing for Serializability]] (Focuses on conflict serializability using precedence graphs).

---
**Related Concepts:**
*   [[Concept of Schedule]]
*   [[ACID Properties]] (Specifically Isolation)
*   [[Conflict Serializability]]
*   [[View Serializability]]
*   [[Testing for Serializability]]
*   [[Concurrency Control Schemes/Concurrency Control Schemes|Concurrency Control Schemes]] (Implementations ensuring serializability)
*   [[Recoverability]] (Another important property of schedules) 