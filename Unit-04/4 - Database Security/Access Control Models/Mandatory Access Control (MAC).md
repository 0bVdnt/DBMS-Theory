# Mandatory Access Control (MAC)

Parent: [[Access Control Models]]

#security #authorization #accesscontrol #mac

*   **Concept:** A system-enforced access control policy based on security classifications (labels) assigned to both users/subjects (clearance) and data objects (classification).
*   **Goal:** Prevent illicit information flow between different security levels.
*   **Core Rules (e.g., Bell-LaPadula Model for confidentiality):**
    *   **Simple Security Property (No Read Up):** A subject can only read an object if the subject's clearance level is greater than or equal to the object's classification level.
    *   **\*-Property (No Write Down):** A subject can only write to an object if the subject's clearance level is less than or equal to the object's classification level.
*   **Advantages:** Strong security guarantees, enforces information flow policies centrally.
*   **Disadvantages:** Rigid, complex to administer, requires careful classification of all data. Not typically used in standard commercial databases, more common in military/high-security environments.

---
**Related Concepts:**
*   [[Access Control Models]]
*   [[../Authorization and Access Control]]
*   [[Discretionary Access Control (DAC)]] (Contrasting model)
*   [[Role-Based Access Control (RBAC)]] 