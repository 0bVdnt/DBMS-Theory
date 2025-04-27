# Authorization and Access Control

Parent: [[Database Security Overview]]

#security #authorization #accesscontrol #privileges

*   **Concept:** Defining and enforcing the permissions (privileges) for [[Authentication|authenticated]] users or programs. Determines *who* can do *what* to *which* database objects (tables, views, procedures, etc.).
*   **Purpose:** Implement the principle of least privilege, ensuring users only have access to the data and operations necessary for their tasks.
*   **Implementation:** Typically managed using:
    *   `GRANT`: Give privileges (e.g., `SELECT`, `INSERT`, `UPDATE`, `DELETE`, `EXECUTE`) on specific objects to users or roles.
    *   `REVOKE`: Remove previously granted privileges.
*   **Models:** Different strategies for organizing and managing permissions. See [[Access Control Models/Access Control Models|Access Control Models]].

---
**Related Concepts:**
*   [[Authentication]] (Prerequisite for authorization)
*   [[Access Control Models/Access Control Models|Access Control Models]] (Different ways to structure authorization)
    *   [[Access Control Models/Discretionary Access Control (DAC)|DAC]]
    *   [[Access Control Models/Mandatory Access Control (MAC)|MAC]]
    *   [[Access Control Models/Role-Based Access Control (RBAC)|RBAC]]
*   [[Database Security Overview]] 