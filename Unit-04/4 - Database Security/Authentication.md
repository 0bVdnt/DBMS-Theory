# Authentication

Parent: [[Database Security Overview]]

#security #authentication

*   **Concept:** Verifying the identity of a user, program, or system trying to access the database.
*   **Purpose:** Ensure that only legitimate entities can attempt to interact with the database. The first line of defense.
*   **Common Methods:**
    *   Username/Password (Most common, susceptible to weak passwords, brute-force)
    *   Multi-Factor Authentication (MFA) (Combines something you know, something you have, something you are)
    *   Digital Certificates / Public Key Infrastructure (PKI)
    *   Kerberos / Single Sign-On (SSO) systems
    *   OS Authentication

Authentication precedes [[Authorization and Access Control]].

---
**Related Concepts:**
*   [[Authorization and Access Control]] (What an authenticated user *can do*)
*   [[Database Security Overview]] 