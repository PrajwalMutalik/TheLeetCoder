<h1 align="center">53. Maximum Subarray</h1>

<p align="center">
  <img src="https://img.shields.io/badge/Difficulty-Easy-brightgreen?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Status-Solved-success?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Language-C++-blue?style=for-the-badge" />
</p>

---

## 📘 Problem

🔗 [Maximum Subarray - LeetCode](https://leetcode.com/problems/maximum-subarray/)  
> Given an integer array `nums`, find the contiguous subarray (containing at least one number) which has the largest sum and return its sum.

---

## 💡 Approach

### ✅ Kadane’s Algorithm
- Use a variable `bag` to store the **current subarray sum**.
- Keep track of the **maximum sum so far** in `ans`.
- If `bag` becomes negative, reset it to 0 — because any negative sum will reduce future subarray totals.
- This works due to the **greedy and dynamic** nature of the problem.

---

## ✅ Code

### 🔹 C++ — Kadane's Algorithm

```cpp
// 📌 Problem: https://leetcode.com/problems/maximum-subarray/
// ✅ Status: Solved
// 🧠 Approach: Kadane's Algorithm (Greedy + DP)
// ⌛ TC: O(n), SC: O(1)
  
class Solution {
public: 
    int maxSubArray(vector<int>& nums) {
        int bag = 0;
        int ans = INT_MIN;

        for(int x : nums) {
            bag += x;
            ans = max(ans, bag);
            if(bag < 0) bag = 0;
        }

        return ans; 
    }
};
