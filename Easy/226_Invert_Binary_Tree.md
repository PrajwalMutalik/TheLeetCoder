<h1 align="center">226. Invert Binary Tree</h1>

<p align="center">
  <img src="https://img.shields.io/badge/Difficulty-Easy-brightgreen?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Status-Solved-success?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Language-C++/Python-blue?style=for-the-badge" />
</p>

---

## 📘 Problem

🔗 [Invert Binary Tree - LeetCode](https://leetcode.com/problems/invert-binary-tree/)  
> Given the root of a binary tree, invert the tree, and return its root.  
Inverting means swapping the left and right children of **every node** in the tree.

---

## 💡 Approach

- Use **recursion** to traverse the binary tree.
- At each node:
  - Swap the left and right subtrees.
  - Recurse on both children.
- Return the modified root.

This approach ensures every node is visited **once**, making it optimal.

---

## ✅ Code

### 🔹 C++

```cpp
// 📌 Problem: https://leetcode.com/problems/invert-binary-tree/
// ✅ Status: Solved
// 🧠 Approach: Recursive DFS with left-right subtree swap
// ⌛ TC: O(n), SC: O(h)

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
### 🔹 Python
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