# Comparative Study of SQL and NoSQL

| Feature                  | [[SQL]] ([[RDBMS]])                                      | [[NoSQL Databases|NoSQL Databases]]                                                                 |
| :----------------------- | :------------------------------------------------------- | :---------------------------------------------------------------------------------- |
| **Data Model**           | Structured, tables with predefined columns and rows.     | Varied: [[Key-Value Stores]], [[Document Stores]], [[Column-Family Stores]], [[Graph Databases]]. |
| **[[Schema]]**           | Rigid, predefined schema (schema-on-write).              | Dynamic, flexible, or schema-less (schema-on-read).                                 |
| **[[Scalability]]**      | Primarily [[Scalability (Horizontal vs Vertical)|Vertical (Scale-Up)]]. Horizontal is complex. | Primarily [[Scalability (Horizontal vs Vertical)|Horizontal (Scale-Out)]]. Designed for distribution.  |
| **[[Consistency]]**      | Strong Consistency ([[ACID Properties]]).                  | Tunable/[[Eventual Consistency]] ([[BASE Properties]] typical). Some offer ACID for limited operations. |
| **Relationships**        | Handled via Foreign Keys and [[Joins]].                  | Handled via embedding, direct references, or graph structures. [[Joins]] often limited. |
| **Query Language**       | [[SQL]] (Structured Query Language) - standardized.      | Varies by type (APIs, sometimes SQL-like like [[CQL]]). Less standardized.        |
| **Data Type**            | Primarily [[Structured vs Unstructured Data|structured data]].        | [[Structured vs Unstructured Data|Structured, semi-structured, unstructured data]].                   |
| **Use Cases**            | OLTP, complex queries, data warehousing, strong [[Consistency]] needs (finance). | [[Big Data]], real-time web apps, content management, IoT, social networks, [[Caching]]. |
| **Examples**             | MySQL, PostgreSQL, Oracle, SQL Server.                 | [[MongoDB Overview|MongoDB]], [[Cassandra Overview|Cassandra]], [[Redis Overview|Redis]], [[Neo4j]].                        |


See also: [[What is NoSQL?]], [[Motivation for NoSQL]]

---
Tags: #nosql #sql #rdbms #comparison #acid #base #scalability #schema #consistency #datamodel 