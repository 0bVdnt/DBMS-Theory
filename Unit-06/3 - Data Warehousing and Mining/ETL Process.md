# ETL Process

ETL stands for **Extract, Transform, Load**. It is a crucial process in [[Data Warehousing]] for moving data from source systems into the data warehouse.

1.  **Extract:** Reading data from various source systems (e.g., [[OLTP]] databases, flat files, APIs, legacy systems).
2.  **Transform:** Applying rules to convert the extracted data into the required format or structure for querying and analysis. This often involves:
    *   [[Data Cleansing]]: Correcting errors, handling missing values.
    *   Standardization: Ensuring consistent units, formats, naming conventions.
    *   Integration: Combining data from multiple sources.
    *   Derivation: Calculating new values.
    *   Aggregation: Summarizing data.
3.  **Load:** Writing the transformed data into the target [[Data Warehousing|Data Warehouse]] (or [[Data Marts]]). This can be a full load or incremental updates.

The [[Data Warehouse Architecture|Data Staging Area]] is often used to temporarily hold data during the ETL process.

See also: [[Data Warehousing]], [[Data Warehouse Architecture]], [[Data Cleansing]]

---
Tags: #etl #data-warehouse #extract #transform #load #data-integration #data-cleansing #staging 