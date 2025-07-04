# 🔁 Elimination Game – Explanation and Optimized Code
# TC - O(log n) SC - O(1)


## 📘 Problem Statement

You are given an integer `n`. Start with a list of numbers from `1` to `n`:


Every round, remove every second number. The direction of removal alternates:
- Round 1: left to right
- Round 2: right to left
- Round 3: left to right
- ...

Continue this elimination process until only **one number remains**. Return that number.

---

## ✅ Optimized C++ Code

```cpp
class Solution {
public:
    int lastRemaining(int n) {
        int x = 1;      // Direction: 1 = left to right, 0 = right to left
        int y = 1;      // First remaining number
        int step = 1;   // Step between surviving numbers
        
        while (n > 1) {
            // Update y when:
            // - Eliminating left to right
            // - OR n is odd (last element also removed in right to left)
            if (x || n % 2 != 0)
                y = y + step;

            n = n / 2;       // Half the elements are removed
            x = x ^ 1;       // Flip direction
            step *= 2;       // Step doubles after each round
        }
        
        return y;
    }
};
