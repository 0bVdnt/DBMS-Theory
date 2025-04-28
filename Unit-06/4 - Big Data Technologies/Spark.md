# Spark (Apache Spark)

*   **Definition:** A fast, general-purpose cluster computing system. Provides high-level APIs (Java, Scala, Python, R).
*   **Advantages over [[MapReduce]]:**
    *   Significantly faster due to in-memory processing capabilities (using [[RDDs|Resilient Distributed Datasets (RDDs)]], DataFrames, Datasets).
    *   More flexible and expressive programming model.
*   **Workloads:** Supports batch processing, interactive queries ([[Spark SQL]]), [[Streaming Data Processing|streaming data (Spark Streaming)]], machine learning ([[MLlib]]), and graph processing ([[GraphX]]).
*   **Integration:**
    *   Can run standalone, on Apache Mesos, or on [[Hadoop Introduction|Hadoop]] [[YARN]].
    *   Can read/write data from [[HDFS]], [[HBase]], [[Hive]], Cassandra, [[Relational Database Management System (RDBMS)|RDBMS]], and many other sources.
*   **Role:** Often used as a faster, more versatile replacement or complement to [[Hadoop Introduction|Hadoop]] [[MapReduce]] within the [[Big Data Introduction|Big Data]] ecosystem.
*   **Performance:** In-memory nature benefits greatly from RAM, but also uses disk for shuffling/spilling, where [[SSD (Solid State Drives)]] offer significant speedups.

See also: [[Hadoop Introduction]], [[MapReduce]], [[YARN]], [[HDFS]], [[RDDs]], [[Big Data Introduction]], [[SSD (Solid State Drives)]]

---
Tags: #spark #hadoop #bigdata #cluster-computing #in-memory #rdd #dataframe #dataset #mapreduce #yarn #hdfs #streaming #machine-learning #graph-processing #performance 