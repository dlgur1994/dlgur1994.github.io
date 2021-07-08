---
layout: post
title: "LeetCode 0121 Best Time to Buy and Sell Stock.py"
date: 2020-11-16 17:11:28 -0400
categories: ProblemSolving
tags: [LeetCode, Array, DynamicProgramming]
comments: true
---

#### 1. How I sloved
&nbsp;&nbsp;&nbsp;&nbsp;I had to find the biggest profit through stock trading, ie the biggest difference between buying and selling. I made the maximum profit 'max_prop' and zero initial value, and the smallest purchase price was 'min_buy' and the initial value was the first element of 'prices'. And I checked all the elements of 'prices'. 'min_buy' and 'max_prop' were updated each time the elements were checked one by one, and finally 'max_prop' was returned.

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
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 56 ms(90.82%), Memory usage : 15 MB(50.52%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
