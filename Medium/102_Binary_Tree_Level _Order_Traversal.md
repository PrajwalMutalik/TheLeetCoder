<h1 align="center">102. Binary Tree Level Order Traversal</h1>

<p align="center">
  <img src="https://img.shields.io/badge/Difficulty-Medium-yellow?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Status-Solved-success?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Language-C++/Python-blue?style=for-the-badge" />
</p>

---

## 📘 Problem

🔗 [102. Binary Tree Level Order Traversal - LeetCode](https://leetcode.com/problems/binary-tree-level-order-traversal/)  
> Given the root of a binary tree, return the level order traversal of its nodes' values. (i.e., from left to right, level by level).

---

## 💡 Approach

- Use a **queue (BFS)** to traverse the tree level by level.
- For each level:
  - Track the number of nodes at the current level (`size` of queue).
  - Collect their values.
  - Add their children to the queue for the next level.
- Append each level's list of values to the final result.

---

## ✅ Code

### 🔹 C++

```cpp
// 📌 Problem: https://leetcode.com/problems/binary-tree-level-order-traversal/
// ✅ Status: Solved
// 🧠 Approach: BFS using queue
// ⌛ TC: O(n), SC: O(n)

class Solution {
public:
    vector<vector<int>> levelOrder(TreeNode* root) {
        vector<vector<int>> res;
        if(root == NULL) return res;

        queue<TreeNode*> qu;
        qu.push(root);

        while(!qu.empty()) {
            int size = qu.size();
            vector<int> level;
            for(int i = 0; i < size; i++) {
                TreeNode* node = qu.front();
                qu.pop();

                if(node->left) qu.push(node->left);
                if(node->right) qu.push(node->right);

                level.push_back(node->val);
            }
            res.push_back(level);
        }

        return res;
    }
};
