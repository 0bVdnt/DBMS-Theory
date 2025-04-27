# Role-Based Access Control (RBAC)

Parent: [[Access Control Models]]

#security #authorization #accesscontrol #rbac

*   **Concept:** Permissions (privileges) are associated with **roles**, and users are assigned to appropriate roles. Access is determined by the permissions assigned to the user's role(s).
*   **Workflow:**
    1.  Define Roles (e.g., `Accountant`, `SalesManager`, `DBAdmin`).
    2.  Grant Permissions to Roles (e.g., `GRANT SELECT ON financials TO Accountant`).
    3.  Assign Users to Roles (e.g., `GRANT Accountant TO alice`).
*   **Advantages:**
    *   Simplifies administration compared to managing permissions per user ([[Discretionary Access Control (DAC)|DAC]]), especially with many users.
    *   Easier to implement the principle of least privilege.
    *   Reflects organizational structure.
*   **Implementation:** Most common access control model in modern enterprise systems and databases.

---
**Related Concepts:**
*   [[Access Control Models]]
*   [[../Authorization and Access Control]]
*   [[Discretionary Access Control (DAC)]] (RBAC simplifies DAC management)
*   [[Mandatory Access Control (MAC)]] 