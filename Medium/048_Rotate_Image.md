<h1 align="center">48. Rotate Image</h1>

<p align="center">
  <img src="https://img.shields.io/badge/Difficulty-Medium-yellow?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Status-Solved-success?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Language-C++-blue?style=for-the-badge" />
</p>

---

## 📘 Problem

🔗 [LeetCode - Rotate Image](https://leetcode.com/problems/rotate-image/)  
> You are given an `n x n` 2D matrix representing an image, rotate the image by 90 degrees (clockwise).  
> You have to rotate the image **in-place**, meaning you have to modify the input 2D matrix directly.

---

## 💡 Approach

### ✅ Step-by-step Strategy (Transpose + Reverse)
1. **Transpose the matrix**:
   - Swap element at `(i, j)` with element at `(j, i)` for all `i ≤ j`.
2. **Reverse each row**:
   - After transposition, reversing each row results in a 90-degree clockwise rotation.

✅ This avoids using extra space and satisfies the **in-place** requirement.

---

## ✅ Code

```cpp
// 📌 Problem: https://leetcode.com/problems/rotate-image/
// ✅ Status: Solved
// 🧠 Approach: Transpose + Reverse each row
// ⌛ TC: O(n^2), SC: O(1)

class Solution {
public:
    void rotate(vector<vector<int>>& matrix) {
        int n = matrix.size();

        // Transpose the matrix
        for (int i = 0 ; i < n; i++) {
            for (int j = 0 ; j <= i; j++) {
                swap(matrix[i][j], matrix[j][i]);
            }
        }

        // Reverse each row
        for (int i = 0; i < n; i++) {
            reverse(matrix[i].begin(), matrix[i].end());
        }
    }
};
