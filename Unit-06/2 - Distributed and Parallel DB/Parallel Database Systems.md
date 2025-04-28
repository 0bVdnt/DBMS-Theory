# Parallel Database Systems

*   **Goal:** Improve performance (processing/IO speed) by executing database operations *in parallel* using multiple CPUs and disks within a tightly coupled system.
*   **Focus:** Performance through parallelization of tasks like data loading, index building, [[Query Processing and Optimization|query evaluation]].
*   **Architectures:**
    *   *Shared Memory:* Multiple processors share common main memory. Simple communication, potential bottleneck.
    *   *Shared Disk:* Processors have private memory, share disk storage (SAN). Balances load, potential disk contention.
    *   *Shared Nothing:* Each processor has private memory *and* disk. Data is partitioned. High [[Scalability (Horizontal vs Vertical)|scalability]], needs network communication. Most scalable.
*   **Data Distribution:** Primarily for performance (partitioning for parallel processing).

See also: [[Distributed Database Systems]], [[Parallel vs Distributed DB Comparison]], [[Query Processing and Optimization]]

---
Tags: #parallel-db #database #architecture #performance #scalability #shared-memory #shared-disk #shared-nothing #query-processing 