<h1 align="center">136. Single Number</h1>

<p align="center">
  <img src="https://img.shields.io/badge/Difficulty-Easy-brightgreen?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Status-Solved-success?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Language-C++-blue?style=for-the-badge" />
</p>

---

## 📘 Problem

🔗 [Single Number - LeetCode](https://leetcode.com/problems/single-number/)  
> Given a non-empty array of integers `nums`, every element appears **twice** except for one. Find that single one.

You must implement a solution with **linear runtime** and **constant space**.

---

## 💡 Approach

### ✅ Approach 1: Hash Map (Counting Frequency)
- Use a hash map (`unordered_map`) to store the frequency of each number.
- Traverse the map and return the element with frequency `1`.

### ✅ Approach 2: Bit Manipulation (XOR Trick)
- Leverage the fact that: `a ^ a = 0`, and `a ^ 0 = a`.
- XOR all numbers together → all duplicate pairs cancel out → only the single number remains.

---

## ✅ Code

### 🔹 C++ — Approach 1 (Hash Map)

```cpp
// 📌 Problem: https://leetcode.com/problems/single-number/
// ✅ Status: Solved
// 🧠 Approach: Frequency count using unordered_map
// ⌛ TC: O(n), SC: O(n)

class Solution {
public:
    int singleNumber(vector<int>& nums) {
        unordered_map<int, int> check;
        for (auto x : nums) {
            check[x]++;
        }
        int res = 0;
        for (auto y : check) {
            if (y.second == 1) res = y.first;
        }
        return res;
    }
};

// 📌 Problem: https://leetcode.com/problems/single-number/
// ✅ Status: Solved
// 🧠 Approach: XOR cancels duplicates, leaves single
// ⌛ TC: O(n), SC: O(1)

class Solution {
public:
    int singleNumber(vector<int>& nums) {
        int res = 0;
        for (auto &i : nums) {
            res ^= i;
        }
        return res;
    }
};
