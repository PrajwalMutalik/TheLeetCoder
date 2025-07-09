<h1 align="center">2149. Rearrange Array Elements by Sign</h1>

<p align="center">
  <img src="https://img.shields.io/badge/Difficulty-Medium-yellow?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Status-Solved-success?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Language-C++-blue?style=for-the-badge" />
</p>

---

## 📘 Problem

🔗 [LeetCode - Rearrange Array Elements by Sign](https://leetcode.com/problems/rearrange-array-elements-by-sign/)  
> Rearrange the array so that positives and negatives alternate. The first element should be positive.

---

## 💡 Approach

- Split the array into two vectors: `positive` and `negative`.
- Use a loop to alternate inserting one positive and one negative into the result vector.
- Since problem guarantees equal count, no bounds checking needed.

---

## ✅ Code

```cpp
// 📌 Problem: https://leetcode.com/problems/rearrange-array-elements-by-sign/
// ✅ Status: Solved
// 🧠 Approach: Use two separate lists and merge them alternately
// ⌛ TC: O(n), SC: O(n)

class Solution {
public:
    vector<int> rearrangeArray(vector<int>& nums) {
        vector<int> ans;
        vector<int> positive, negative;

        for (int num : nums) {
            if (num > 0)
                positive.push_back(num);
            else
                negative.push_back(num);
        }

        for (int i = 0; i < positive.size(); i++) {
            ans.push_back(positive[i]);
            ans.push_back(negative[i]);
        }

        return ans;
    }
};