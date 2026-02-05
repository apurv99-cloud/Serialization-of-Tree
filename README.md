Serialization and Deserialization of Binary Tree
Overview

Serialization and deserialization are fundamental concepts used to convert complex data structures into a transferable format and reconstruct them back without losing structure.

In this project, I implemented serialization and deserialization of a binary tree using preorder traversal with null markers.
This approach guarantees that both the values and the exact structure of the tree are preserved.

This problem is based on LeetCode 297 (Hard) and is commonly discussed in DSA interviews and system design contexts.

What is Serialization?

Serialization is the process of converting a binary tree into a linear representation (string) so that it can be:

stored in memory or files

transmitted across a network

reconstructed later

Since a binary tree is non-linear, serialization must also capture null child positions to preserve the tree shape.

What is Deserialization?

Deserialization is the reverse process of serialization.
It reconstructs the original binary tree from the serialized string while maintaining:

node values

left/right child relationships

overall structure

Approach Used
Traversal Technique

Preorder Traversal (Root → Left → Right)

Key Idea

Every node value is recorded

null is explicitly recorded for missing children

The same traversal order is used during reconstruction

This ensures that the serialized data uniquely represents the binary tree.

Serialization Logic

Traverse the tree in preorder.

If the node is null, append "null" to the string.

Otherwise, append the node value.

Continue recursively for left and right children.

This produces a single string representing the entire tree structure.

Deserialization Logic

Split the serialized string into tokens.

Use a shared index to read tokens sequentially.

If the current token is "null", return null.

Otherwise:

create a tree node

recursively build its left subtree

recursively build its right subtree

Because the data was written in preorder, reading it in the same order allows correct reconstruction.

Why Null Markers Are Important

Without null markers:

different tree structures can produce the same traversal

reconstruction becomes ambiguous or impossible

Null values act as structural boundaries, allowing the exact tree shape to be rebuilt.

Time and Space Complexity

Time Complexity: O(n)

Space Complexity: O(n)

Where n is the number of nodes in the tree.

Why This Problem Matters

Tests deep understanding of tree traversal and recursion

Connects DSA concepts with real-world systems

Serialization is widely used in:

REST APIs

distributed systems

caching systems

databases

microservices communication

Key Takeaway

A binary tree is defined not only by its values, but by its structure.
Serialization preserves both, and deserialization restores both.
