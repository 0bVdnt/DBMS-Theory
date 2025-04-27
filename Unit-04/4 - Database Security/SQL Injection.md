# SQL Injection

Parent: [[Database Security Overview]]

#security #sqlinjection #attack #vulnerability

*   **Threat:** A common code injection technique used to attack data-driven applications. Malicious SQL statements are inserted (`injected`) into data entry fields (e.g., web forms, URL parameters) for execution by the backend database.
*   **Mechanism:** Exploits applications that dynamically construct SQL queries by concatenating unvalidated or unsanitized user input directly into the SQL query string.
*   **Impact:** Can be used to:
    *   Bypass [[Authentication]].
    *   Read sensitive data (data theft).
    *   Modify or delete data.
    *   Execute administrative database operations (e.g., drop tables, shut down DB).
*   **Example:**
    *   Original Query (intended): `SELECT * FROM users WHERE username = '` + userInput + `'`;
    *   Malicious Input (`userInput`): `' OR '1'='1`
    *   Executed Query: `SELECT * FROM users WHERE username = '' OR '1'='1'` (returns all users, bypassing intended filter).

## Prevention (Primary Defenses)

1.  **Prepared Statements / Parameterized Queries:** (Most effective defense)
    *   Treat user input strictly as data, not as part of the executable SQL command.
    *   The database driver/engine handles quoting and escaping correctly.
2.  **Input Validation / Sanitization:**
    *   Validate input against expected formats (e.g., check if user ID is numeric).
    *   Sanitize input by escaping special SQL characters (e.g., `'`, `;`, `--`). Less robust than prepared statements.
3.  **Principle of Least Privilege:**
    *   Ensure the database account used by the application has only the minimum necessary permissions via [[Authorization and Access Control]]. Limits damage if injection occurs.
4.  **Web Application Firewalls (WAFs):**
    *   Can help detect and block common [[SQL Injection]] patterns at the network level.

---
**Related Concepts:**
*   [[Database Security Overview]]
*   [[Authentication]] (Can be bypassed)
*   [[Authorization and Access Control]] (Least privilege limits impact)
*   [[Intrusion Detection]] (Can potentially detect injection attempts) 