# SSD (Solid State Drives)

*   **Technology:** Storage devices using integrated circuit assemblies (flash memory) for persistent data storage. Lack moving mechanical parts found in traditional Hard Disk Drives (HDDs).
*   **Impact on Databases & Big Data:**
    *   **Performance:** Offer significantly lower latency (faster access) and much higher Input/Output Operations Per Second (IOPS) compared to HDDs.
    *   **Benefits:**
        *   Dramatically speeds up I/O-bound [[Database]] operations (queries, indexing, logging, loading).
        *   Improves performance of [[Big Data Technologies|Big Data systems]] like [[Hadoop Introduction|Hadoop]] and [[Spark]].
        *   Faster [[MapReduce]] shuffles.
        *   Quicker [[HBase]] random reads/writes and WAL operations.
        *   Improved [[Spark]] caching, checkpointing, and shuffle performance.
        *   Faster [[HDFS]] [[Meta Data]] operations (if NameNode uses SSDs).
*   **Usage:** Increasingly used for primary [[Database]] storage, [[Caching|caching layers]], temporary file storage (e.g., [[Spark]] shuffle directories), and critical [[Meta Data]] storage ([[HDFS]] NameNode, [[HBase]] WALs).

See also: [[Database]], [[Big Data Technologies]], [[Hadoop Introduction]], [[HDFS]], [[MapReduce]], [[Spark]], [[HBase]], [[Performance]]

---
Tags: #ssd #storage #hardware #performance #latency #iops #flash-memory #database #bigdata #hadoop #spark #hbase #hdfs 