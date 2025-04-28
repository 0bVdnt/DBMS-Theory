# Data Warehouse Architecture

Typical components of a [[Data Warehousing|Data Warehouse]] architecture include:

1.  **Source Systems:** Operational databases ([[OLTP]]), legacy systems, external data feeds.
2.  **Data Staging Area:** Intermediate storage for the [[ETL Process]].
3.  **[[ETL Process]] (Extract, Transform, Load):**
    *   Extracts data from sources.
    *   Transforms/Cleanses data (handles inconsistencies, standardizes formats, ensures quality - [[Data Cleansing]]).
    *   Loads data into the warehouse.
4.  **Presentation Server / Data Warehouse Store:** The actual storage, often using [[Dimensional Modeling]] (star/snowflake schemas). May include [[Data Marts]] (subsets for specific departments).
5.  **[[Meta Data]] Repository:** Stores "data about data" - definitions, sources, transformations, schemas, usage statistics. Crucial for management.
6.  **End-User Access Tools:** Query/reporting tools, [[OLAP]] tools, [[Data Mining]] tools, dashboards.

See also: [[Data Warehousing]], [[ETL Process]], [[Meta Data]], [[Data Marts]], [[OLAP]], [[Data Mining]]

---
Tags: #data-warehouse #architecture #dw #etl #staging #presentation-server #metadata #olap #data-mining #datamart 