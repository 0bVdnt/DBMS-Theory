# Hashing

Parent: [[Storage Strategies Overview]]

#storage #hashing

*   **Concept:** Uses a hash function to compute an address (bucket) in storage for a given key. Aims for O(1) average-case lookup, insertion, and deletion.
*   **Static Hashing:**
    *   *Hash Function:* Maps keys to a fixed set of bucket addresses.
    *   *Buckets:* Storage units (e.g., disk blocks).
    *   *Collisions:* Multiple keys hashing to the same bucket. Handled using techniques like:
        *   *Overflow Chaining:* Buckets have pointers to overflow blocks/records.
        *   *Open Addressing:* Find the next available slot (less common for disk-based DBs).
    *   *Limitation:* Fixed number of buckets; performance degrades significantly if data size changes drastically or collisions are frequent.
*   **Dynamic Hashing:** Allows the hash structure to grow or shrink as data volume changes. Examples:
    *   *Extendible Hashing:* Uses a directory of pointers to buckets; directory size doubles/halves as needed; buckets split locally.
    *   *Linear Hashing:* Buckets are split in a fixed order, regardless of which bucket overflowed; uses multiple hash functions over time.
*   **Advantages/Disadvantages:** Excellent for exact-match queries. Not suitable for range queries (hashed values lose proximity). Collision handling adds overhead.

---
**Related Concepts:**
*   [[Indices]] (Alternative, better for range queries)
*   [[B-Trees]] (Alternative, better for range queries)
*   [[2 - Query Processing and Optimization/Join Strategies|Join Strategies]] (Hash Join utilizes hashing internally) 