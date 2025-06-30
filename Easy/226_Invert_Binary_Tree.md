# 226. Invert Binary Tree

**Link**: [LeetCode - Invert Binary Tree](https://leetcode.com/problems/invert-binary-tree/)

---

## 🧠 Problem Statement

> Given the root of a binary tree, invert the tree, and return its root.

Inverting means swapping the left and right children of **every node** in the tree.

---

## 🔍 Approach

We use **recursion (Depth-First Search)** to traverse the binary tree. At every node:

1. Swap the left and right child pointers.
2. Recursively apply the same operation on the left and right subtrees.
3. Return the root after inversion.

This guarantees that every node is visited exactly once.

---

## ✅ Code (C++)

```cpp
class Solution {
public:
    TreeNode* invertTree(TreeNode* root) {
        if(root == NULL) return NULL;

        TreeNode* temp = root->left;
        root->left = root->right;
        root->right = temp;

        invertTree(root->left);
        invertTree(root->right);

        return root;
    }
};
```
```py
class Solution:
    def invertTree(self, root):
        if root is None:
            return None

        root.left, root.right = root.right, root.left
        self.invertTree(root.left)
        self.invertTree(root.right)

        return root
```