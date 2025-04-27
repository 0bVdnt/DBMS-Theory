# Discretionary Access Control (DAC)

Parent: [[Access Control Models]]

#security #authorization #accesscontrol #dac

*   **Concept:** The owner of a database object (e.g., the user who created a table) has the discretion to grant or revoke privileges on that object to other users.
*   **Implementation:** Typically uses SQL `GRANT` and `REVOKE` commands.
*   **Example:** User A creates table `T`. User A can `GRANT SELECT ON T TO User B`. User B might then be able (depending on system rules) to `GRANT SELECT ON T TO User C` (privilege propagation).
*   **Advantages:** Flexible.
*   **Disadvantages:** Can become complex to manage securely. Difficult to track who has what privileges, especially with propagation. Doesn't inherently prevent malicious users from leaking data they legitimately have access to.

---
**Related Concepts:**
*   [[Access Control Models]]
*   [[../Authorization and Access Control]]
*   [[Mandatory Access Control (MAC)]] (Contrasting model)
*   [[Role-Based Access Control (RBAC)]] (Often used alongside or instead of DAC) 