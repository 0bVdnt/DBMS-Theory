# HBase

*   **Definition:** An open-source, distributed, versioned, non-relational ([[Column-Family Stores|column-family]]) database modeled after Google's Bigtable. Part of the [[Hadoop Introduction|Hadoop]] ecosystem, runs on top of [[HDFS]].
*   **Characteristics:**
    *   Provides low-latency random read/write access to huge datasets (billions of rows, millions of columns).
    *   [[Schema|Schema-flexible]]: Sparse, distributed, persistent, multi-dimensional sorted map.
    *   Data is automatically partitioned (sharded) into "regions" managed by RegionServers.
    *   Uses [[HDFS]] for underlying persistent storage.
    *   Uses ZooKeeper for cluster coordination.
*   **Use Cases:** Ideal for applications needing fast key-based lookups and updates within massive tables (e.g., real-time analytics, message brokering, serving web page content).
*   **Performance:** Benefits significantly from [[SSD (Solid State Drives)]] for low-latency operations and Write-Ahead Logs (WALs).

See also: [[Hadoop Introduction]], [[HDFS]], [[Column-Family Stores]], [[Big Data Introduction]], [[NoSQL Databases]], [[SSD (Solid State Drives)]]

---
Tags: #hbase #hadoop #nosql #column-family #bigtable #bigdata #hdfs #distributed-database #random-access #low-latency 