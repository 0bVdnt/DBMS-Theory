# YARN (Yet Another Resource Negotiator)

*   **Role:** Introduced in [[Hadoop Introduction|Hadoop]] 2, YARN separates cluster resource management from job scheduling/monitoring, making Hadoop a more general-purpose [[Big Data Introduction|Big Data]] platform.
*   **Architecture:** Replaces the [[MapReduce]] V1 JobTracker/TaskTracker model.
    *   **ResourceManager (RM):** Global master managing resource allocation across all applications in the cluster.
    *   **NodeManager (NM):** Per-node slave agent responsible for launching/monitoring containers (application processes) and reporting resource usage to the RM.
    *   **ApplicationMaster (AM):** Framework-specific entity (one per application) that negotiates resources from the RM and works with NMs to execute and monitor tasks.
*   **Benefit:** Allows multiple different processing frameworks (e.g., [[MapReduce]], [[Spark]], Tez, Flink) to run concurrently on the same Hadoop cluster, sharing resources managed by YARN.

See also: [[Hadoop Introduction]], [[MapReduce]], [[Spark]], [[HDFS]], [[Big Data Introduction]]

---
Tags: #yarn #hadoop #resource-management #cluster #bigdata #resourcemanager #nodemanager #applicationmaster #mapreduce #spark 