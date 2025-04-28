# MapReduce

*   **Role:** The original parallel processing framework in [[Hadoop Introduction|Hadoop]] for processing large datasets stored in [[HDFS]].
*   **Model:** Divides computation into two main phases executed in parallel across a cluster:
    1.  **Map Phase:** Input data (key1, value1) is split and processed by map tasks, producing intermediate key-value pairs `list(key2, value2)`.
    2.  **Reduce Phase:** Intermediate pairs are shuffled/sorted by key2. Reduce tasks process `(key2, list(value2))` to produce final output `list(key3, value3)`.
*   **Execution (Hadoop V1):** Managed by JobTracker (master) and TaskTrackers (slaves).
*   **Execution (Hadoop V2+):** Runs as an application on [[YARN]].
*   **Limitations:** Primarily batch-oriented, high latency, relatively complex programming, inefficient for iterative/interactive tasks.
*   **Significance:** A fundamental concept in [[Big Data Introduction|Big Data]] processing, although often superseded or complemented by faster frameworks like [[Spark]]. Performance influenced by disk I/O, benefits from [[SSD (Solid State Drives)]] for shuffling.

See also: [[Hadoop Introduction]], [[HDFS]], [[YARN]], [[Spark]], [[Big Data Introduction]], [[SSD (Solid State Drives)]]

---
Tags: #mapreduce #hadoop #bigdata #processing #parallel-computing #batch #map #reduce #yarn #spark #distributed-computing 