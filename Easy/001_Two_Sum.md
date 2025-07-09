<h1 align="center">1. Two Sum</h1>

<p align="center">
  <img src="https://img.shields.io/badge/Difficulty-Easy-brightgreen?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Status-Solved-success?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Language-C++-blue?style=for-the-badge" />
</p>

---

## 📘 Problem

🔗 [Two Sum - LeetCode](https://leetcode.com/problems/two-sum/)  
> Given an array of integers `nums` and an integer `target`, return the indices of the two numbers such that they add up to the target.  
> You may assume that each input would have exactly one solution, and you may not use the same element twice.

---

## 💡 Approach

### ✅ Brute-Force (Nested Loops)
- Check all possible pairs `(i, j)` where `i < j`.
- If `nums[i] + nums[j] == target`, return `[i, j]`.
- Guaranteed one solution, so return is safe once found.

---

## ✅ Code
 
### 🔹 C++ — Brute Force

```cpp
// 📌 Problem: https://leetcode.com/problems/two-sum/
// ✅ Status: Solved
// 🧠 Approach: Brute-force nested loops
// ⌛ TC: O(n^2), SC: O(1)

class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        int n = nums.size();
        for(int i = 0; i < n; i++) {
            for(int j = i + 1; j < n; j++) {
                if(nums[i] + nums[j] == target) {
                    return {i, j};
                }
            }
        }
        return {};
    }
};
