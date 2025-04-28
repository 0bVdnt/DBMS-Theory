# HDFS (Hadoop Distributed File System)

*   **Role:** The primary storage system of [[Hadoop Introduction|Hadoop]]. A fault-tolerant, high-throughput [[Distributed Database Systems|distributed file system]] designed for [[Commodity Hardware]].
*   **Architecture:** Master/slave.
    *   **NameNode:** Master server managing file system namespace ([[Meta Data]]) and block locations. Regulates client access.
    *   **DataNodes:** Slave servers storing actual data blocks. Data blocks are replicated (e.g., 3x) across DataNodes for fault tolerance.
*   **Characteristics:**
    *   Optimized for large files and streaming data access (write-once, read-many).
    *   High throughput but potentially higher latency.
    *   Not ideal for low-latency random access or many small files.
    *   Performance can be significantly improved by using [[SSD (Solid State Drives)]] for [[Meta Data]] (NameNode) and potentially data storage (DataNodes).

See also: [[Hadoop Introduction]], [[MapReduce]], [[YARN]], [[NameNode]], [[DataNode]], [[Fault Tolerance]], [[Meta Data]], [[SSD (Solid State Drives)]]

---
Tags: #hdfs #hadoop #distributed-filesystem #storage #bigdata #namenode #datanode #replication #fault-tolerance #streaming #commodity-hardware 