<h1 align="center">121. Best Time to Buy and Sell Stock</h1>

<p align="center">
  <img src="https://img.shields.io/badge/Difficulty-Easy-brightgreen?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Status-Solved-success?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Language-C++-blue?style=for-the-badge" />
</p>

---

## 📘 Problem

🔗 [LeetCode - Best Time to Buy and Sell Stock](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/)  
> Find the maximum profit you can achieve from buying and selling a stock. You must buy before you sell.

---

## 💡 Approach

- Track the **lowest price** seen so far (`buy`).
- At each step, calculate `current price - buy` and update `profit` if it's better.
- Greedy approach to find the best time window.

---

## ✅ Code

```cpp
// 📌 Problem: https://leetcode.com/problems/best-time-to-buy-and-sell-stock/
// ✅ Status: Solved
// 🧠 Approach: Track min price so far, update max profit
// ⌛ TC: O(n), SC: O(1)
 
class Solution { 
public:
    int maxProfit(vector<int>& prices) {
        int buy = prices[0];
        int profit = 0;
        for (int i = 1; i < prices.size(); i++) {
            if (prices[i] < buy) {
                buy = prices[i];
            } else if (prices[i] - buy > profit) {
                profit = prices[i] - buy;
            }
        }
        return profit;
    }
};
