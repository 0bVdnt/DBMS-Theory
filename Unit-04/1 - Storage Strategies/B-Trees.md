# B-Trees (specifically B+-trees)

Parent: [[Storage Strategies Overview]]

#storage #index #btree

*   **Concept:** A self-balancing tree data structure that maintains sorted data and allows searches, sequential access, insertions, and deletions in logarithmic time. Widely used for implementing database [[Indices]].
*   **B+-tree Structure:**
    *   *Balanced:* All leaf nodes are at the same depth.
    *   *Nodes:* Contain keys and pointers. Internal nodes point to child nodes; leaf nodes point to data records or blocks (or contain the data itself in some implementations).
    *   *Sorted Keys:* Keys within nodes are sorted.
    *   *Leaf Node Linking:* Leaf nodes are linked sequentially (doubly linked list), allowing efficient range queries.
    *   *High Fanout:* Nodes typically hold many keys/pointers, making the tree relatively shallow and wide, minimizing disk I/O for searches.
*   **Operations:** Search (traverse from root to leaf), Insertion (find leaf, insert, may cause node splits propagating up), Deletion (find leaf, delete, may cause node merges propagating up).
*   **Advantages for Databases:** Efficient for both point queries (finding a specific value) and range queries (finding values within a range) due to sorted, linked leaves. Logarithmic performance scales well. Disk I/O is minimized.

---
**Related Concepts:**
*   [[Indices]] (Primary use case)
*   [[Hashing]] (Alternative storage strategy) 