---
layout: post
title: "LeetCode 0122 Best Time to Buy and Sell Stock II.py"
date: 2020-12-04 11:54:28 -0400
categories: [Problem Solving]
tags: [LeetCode, Python, rray, Greedy]
comments: true
---

### 1. Code
```python
class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        profit = 0
        #If the next price is larger than the current price, add the next price minus the current price.
        for i in range(len(prices)-1):
            if prices[i+1] > prices[i]:
                profit += prices[i+1] - prices[i]
        return profit
```

### 2. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 48 ms(98.83%), Memory usage : 15.2 MB(9.27%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
