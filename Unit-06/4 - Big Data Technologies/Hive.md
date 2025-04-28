# Hive (Apache Hive)

*   **Definition:** A data warehouse software project built on top of [[Hadoop Introduction|Hadoop]] for providing data query and analysis.
*   **Functionality:**
    *   Provides an [[SQL]]-like interface called HiveQL (HQL) to query data stored in various formats on [[HDFS]] or in [[HBase]].
    *   Translates HQL queries into execution plans, typically involving [[MapReduce]], Tez, or [[Spark]] jobs running on the cluster via [[YARN]].
    *   Facilitates [[ETL Process|ETL]], reporting, and data analysis on [[Big Data Introduction|Big Data]].
    *   Uses a metastore (often a traditional [[Relational Database Management System (RDBMS)|RDBMS]]) to store schema information about the data stored in [[HDFS]] ("schema-on-read").
*   **Goal:** To make large-scale data processing on Hadoop accessible to users familiar with [[SQL]].

See also: [[Hadoop Introduction]], [[HDFS]], [[HBase]], [[MapReduce]], [[Spark]], [[YARN]], [[SQL]], [[ETL Process]], [[Data Warehousing]], [[Big Data Introduction]]

---
Tags: #hive #hadoop #data-warehouse #sql #hql #bigdata #hdfs #mapreduce #spark #yarn #etl #query-engine #schema-on-read 