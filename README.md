Serialization and Deserialization of Binary Tree
Overview

Serialization and deserialization are fundamental concepts used to convert complex data structures into a transferable format and reconstruct them later without losing structure.

In this project, I implemented serialization and deserialization of a binary tree using preorder traversal with explicit null markers.
This approach guarantees that both the node values and the exact structure of the tree are preserved.

This implementation is based on LeetCode 297 (Hard) and is commonly discussed in DSA interviews as well as system design contexts.

What is Serialization?

Serialization is the process of converting a binary tree into a linear representation (string) so that it can be:

Stored in memory or files

Transmitted across a network

Reconstructed later

Since a binary tree is a non-linear data structure, serialization must also capture null child positions to preserve the original tree shape.

What is Deserialization?

Deserialization is the reverse process of serialization.
It reconstructs the binary tree from the serialized string while maintaining:

Node values

Left and right child relationships

Overall structure of the tree

Approach Used
Traversal Strategy

Preorder Traversal (Root → Left → Right)

Core Idea

Record every node value

Explicitly record null for missing children

Use the same traversal order during reconstruction

This guarantees a unique and reversible representation of the binary tree.

Serialization Logic

Traverse the tree using preorder traversal.

If the current node is null, append "null" to the string.

Otherwise, append the node’s value.

Recursively process the left and right subtrees.

This produces a single string representing both the structure and data of the tree.

Deserialization Logic

Split the serialized string into tokens.

Use a shared index pointer to process tokens sequentially.

If the current token is "null", return null.

Otherwise:

Create a tree node from the value

Recursively build the left subtree

Recursively build the right subtree

Because the data was serialized in preorder, reading it in the same order reconstructs the original tree correctly.

Why Null Markers Are Important

Without null markers:

Different tree structures can produce identical traversals

Reconstruction becomes ambiguous or impossible

Null markers act as structural boundaries, enabling exact reconstruction of the binary tree.

Time and Space Complexity

Time Complexity: O(n)

Space Complexity: O(n)

Where n is the number of nodes in the binary tree.

Why This Problem Matters

Tests deep understanding of recursion and tree traversal

Bridges DSA concepts with real-world systems

Serialization is widely used in:

REST APIs

Distributed systems

Caching systems

Databases

Microservices communication

Key Takeaway

A binary tree is defined not only by its values, but by its structure.
Serialization preserves both, and deserialization restores both.
Serialization preserves both, and deserialization restores both.
