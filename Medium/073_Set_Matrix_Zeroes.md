<h1 align="center">73. Set Matrix Zeroes</h1>

<p align="center">
  <img src="https://img.shields.io/badge/Difficulty-Medium-yellow?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Status-Solved-success?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Language-C++-blue?style=for-the-badge" />
</p>

---

## 📘 Problem

🔗 [LeetCode - Set Matrix Zeroes](https://leetcode.com/problems/set-matrix-zeroes/)  
> Given an `m x n` integer matrix, if an element is 0, set its entire row and column to 0 in-place.

---

## 💡 Approach

### ✅ Step-by-step Strategy (Using Extra Space)
- Use two boolean arrays: one for **rows**, one for **columns**.
- In the **first pass**, mark which rows and columns should be zeroed (based on where 0s are).
- In the **second pass**, set the appropriate cells to `0` using the markers.

✅ This avoids modifying the matrix while scanning it the first time.

> ⚠️ This version uses **O(m + n)** extra space.  
> A more optimal solution exists using **O(1)** space by leveraging the matrix itself.

---

## ✅ Code

```cpp
// 📌 Problem: https://leetcode.com/problems/set-matrix-zeroes/
// ✅ Status: Solved
// 🧠 Approach: Use row and column markers to track 0s
// ⌛ TC: O(m * n), SC: O(m + n)

class Solution {
public:
    void setZeroes(vector<vector<int>>& matrix) {
        int n = matrix.size();
        int m = matrix[0].size();
        vector<bool> r(n, false);
        vector<bool> c(m, false);

        // First pass: mark rows and columns
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < m; j++) {
                if (matrix[i][j] == 0) {
                    r[i] = true;
                    c[j] = true;
                }
            }
        }

        // Second pass: update the matrix
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < m; j++) {
                if (r[i] || c[j]) {
                    matrix[i][j] = 0;
                }
            }
        }
    }
};
