<h1 align="center">🧠 LeetCode Daily Grind</h1>
<p align="center">
  <img src="https://img.shields.io/badge/Problems%20Solved-XX-orange?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Language-C++/Python-blue?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Updated-Daily-success?style=for-the-badge" />
</p>

## 📘 About

This repository contains my daily solutions to LeetCode problems, along with clear and concise explanations.  
I aim to improve my DSA skills consistently while helping others learn too.

## 🗂️ Structure

- `Easy/`, `Medium/`, `Hard/`: Sorted by difficulty.
- `Daily/`: Day-wise problems with markdown explanations.
- Each solution contains:
  - ✅ Problem Link
  - 💡 Explanation
  - ⌛ Time and Space Complexity

## 🛠️ Languages Used
- C++ (primary)
- Python (for scripting or simple problems)

## 📅 My Goal
> 📌 Solve at least 1 problem every day and explain it in detail — for 365 days straight!

---

## ✅ Sample Problem Format

```cpp
// 📌 Problem: https://leetcode.com/problems/two-sum/
// ✅ Status: Solved
// 🧠 Approach: HashMap to store complements
// ⌛ TC: O(n), SC: O(n)

class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        unordered_map<int, int> map;
        for (int i = 0; i < nums.size(); i++) {
            int complement = target - nums[i];
            if (map.count(complement)) {
                return {map[complement], i};
            }
            map[nums[i]] = i;
        }
        return {};
    }
};
