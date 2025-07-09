<h1 align="center">128. Longest Consecutive Sequence</h1>

<p align="center">
  <img src="https://img.shields.io/badge/Difficulty-Medium-yellow?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Status-Solved-success?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Language-C++-blue?style=for-the-badge" />
</p>

---

## 📘 Problem   

🔗 [LeetCode - Longest Consecutive Sequence](https://leetcode.com/problems/longest-consecutive-sequence/)  
> Given an unsorted array of integers, find the length of the longest consecutive elements sequence.  
> You must write an algorithm that runs in O(n) time.

---

## 💡 Approach

- Use an unordered set to store all numbers.
- For every number, check if it’s the **start** of a sequence (i.e., `num - 1` not in set).
- From each sequence start, count its length using a while loop.
- Track the maximum sequence length found.

---

## ✅ Code

```cpp
// 📌 Problem: https://leetcode.com/problems/longest-consecutive-sequence/
// ✅ Status: Solved
// 🧠 Approach: Use set for O(1) lookups, expand from sequence starts
// ⌛ TC: O(n), SC: O(n)

class Solution {
public:
    int longestConsecutive(vector<int>& nums) {
        if (nums.empty()) return 0;

        unordered_set<int> num_set(nums.begin(), nums.end());
        int longest_streak = 0;

        for (const int& num : num_set) {
            if (!num_set.count(num - 1)) {
                int current = num;
                int streak = 1;

                while (num_set.count(current + 1)) {
                    current++;
                    streak++;
                }

                longest_streak = max(longest_streak, streak);
            }
        }

        return longest_streak;
    }
};