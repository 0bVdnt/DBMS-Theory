# Distributed Database Model

A distributed database is one whose storage devices are not all attached to a common processing unit. Data is stored across multiple physical locations (nodes/servers) connected by a network.

## Goals:
*   Increased reliability/[[High Availability|availability]] (no single point of failure)
*   [[Scalability (Horizontal vs Vertical)|Scalability]] (add more nodes)
*   Potentially faster local access

## Challenges:
*   Query processing complexity
*   Transaction management complexity (distributed commits)
*   Maintaining [[Consistency]] across nodes
*   Network latency
*   Potential for network [[Partition Tolerance|partitions]]

See also: [[CAP Theorem]], [[BASE Properties]], [[Scalability (Horizontal vs Vertical)]]

---
Tags: #distributed #database #architecture #scalability #consistency #availability #partition 