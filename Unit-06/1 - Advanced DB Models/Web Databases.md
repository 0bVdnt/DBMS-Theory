# Web Databases

*   **Concept:** Refers more to the architecture and application context than a distinct database *model*. It's a database system designed to be accessed via the World Wide Web.
*   **Architecture:** Typically a multi-tier architecture:
    1.  **Client Tier:** Web browser (HTML, JavaScript).
    2.  **Web Server Tier:** Handles HTTP requests (e.g., Apache, Nginx).
    3.  **Application Server Tier:** Executes application logic (PHP, Python, Java, etc.) interacting with the database.
    4.  **Database Tier:** Backend database ([[Relational Database Management System (RDBMS)|RDBMS]], [[NoSQL Databases|NoSQL]], etc.).
*   **Key Considerations:**
    *   *Statelessness:* Managing sessions (cookies, server-side stores, maybe [[Key-Value Stores]]).
    *   *Security:* Vulnerable to [[SQL Injection]], XSS. Requires secure coding (prepared statements, input validation).
    *   *[[Scalability (Horizontal vs Vertical)|Scalability]] & Performance:* Handle concurrent users. [[Caching]] is crucial. Backend DB often needs to be scalable ([[NoSQL Databases|NoSQL]], distributed [[Relational Database Management System (RDBMS)|RDBMS]]).
    *   *APIs:* Interaction via database drivers.

---
Tags: #web-db #architecture #database-model #web-application #security #sql-injection #scalability #performance #caching 