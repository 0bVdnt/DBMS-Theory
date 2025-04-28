# Data Warehousing

*   **Concept:** A central repository of integrated data from disparate sources (operational systems like [[OLTP]], external data). Stores current and historical data, optimized for querying, reporting, and analysis ([[OLAP]] - Online Analytical Processing).
*   **Definition (Inmon):** "A warehouse is a subject-oriented, integrated, time-variant and non-volatile collection of data in support of management's decision making process."
    *   *Subject-Oriented:* Organized around subjects (customer, product) not operations.
    *   *Integrated:* Data made consistent (naming, units, format).
    *   *Time-Variant:* Contains historical data, snapshots over time.
    *   *Non-Volatile:* Loaded periodically, not updated transactionally like [[OLTP]].
*   **Benefits:** Decision support, business intelligence, trend analysis, consistent view, offloads reporting from [[OLTP]].
*   **Characteristics:** Designed for analytical tasks, updated periodically, historical data.
*   **Related Concepts:** [[Data Warehouse Architecture]], [[ETL Process]], [[Data Marts]], [[Dimensional Modeling]], [[Meta Data]], [[Data Mining]].

Contrast with: [[OLTP]]

---
Tags: #data-warehouse #dw #olap #bi #decision-support #architecture #subject-oriented #integrated #time-variant #non-volatile 