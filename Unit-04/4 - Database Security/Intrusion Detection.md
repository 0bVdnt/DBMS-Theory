# Intrusion Detection

Parent: [[Database Security Overview]]

#security #intrusiondetection #monitoring

*   **Concept:** Monitoring database activity to detect malicious actions, security policy violations, or anomalous behavior that might indicate an attack or misuse.
*   **Purpose:** Provide alerts or take action when suspicious activity is detected, complementing preventative measures like [[Authentication]] and [[Authorization and Access Control]].
*   **Detection Approaches:**
    *   **Signature-Based (Misuse Detection):** Looks for patterns (signatures) of known attacks (e.g., specific [[SQL Injection]] patterns, known vulnerability exploits).
    *   **Anomaly-Based:** Establishes a baseline of normal user/system behavior and flags significant deviations from that baseline (e.g., user accessing unusual tables, unusually large data downloads, activity at unusual times).
*   **Examples of Monitored Activities:**
    *   Repeated failed login attempts.
    *   Attempts to access unauthorized data objects.
    *   Unusually high volume of queries or data retrieval.
    *   Execution of administrative commands by non-admin users.
    *   Changes to database schema or security configurations.

---
**Related Concepts:**
*   [[Database Security Overview]]
*   [[Authentication]]
*   [[Authorization and Access Control]]
*   [[SQL Injection]] (A common threat IDS aims to detect) 