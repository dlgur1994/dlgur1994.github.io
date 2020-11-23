---
title: "LeetCode 0121 Best Time to Buy and Sell Stock.py"
categories: LeetCode Array DynamicProgramming
date: 2020-11-22 14:39:28 -0400
---

#### 1. How I sloved
&nbsp;&nbsp;&nbsp;&nbsp;I had to find the biggest profit. The maximum profit, 'max_prof', was initially set at zero, and all prices were checked. The lowest price, 'min_buy' was compared with each price and the smaller one became 'min_buy'. 'max_prof' was updated when the previous 'max_prof' was less than (price-min_buy). Finally, 'max_prof' was returned after checking all prices.

### 2. Code
```python
class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        if prices == []:
            return 0
        max_prof = 0
        min_buy = prices[0]
        for price in prices:
            min_buy = min(min_buy,price)
            max_prof = max(max_prof,price-min_buy)
        return max_prof
```

### 3. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 56 ms(88.12%), Memory usage : 15.1 MB(16.08%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
