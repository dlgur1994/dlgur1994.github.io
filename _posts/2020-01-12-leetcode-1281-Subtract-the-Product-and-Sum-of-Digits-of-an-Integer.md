---
layout: post
title: "LeetCode 1281 Subtract the Product and Sum of Digits of an Integer.py"
date: 2020-01-12 14:53:28 -0400
categories: [Problem Solving]
tags: [LeetCode, Python, Math]
comments: true
---

## 1. What I learned
    a. def subtractProductAndSum(self, n: int) -> int:
    b. how to use class
    c. how to declare a list
    d. difference in the runtime   

## 2. Code
```python
class Solution:
    def subtractProductAndSum(self, n: int) -> int:
        lenOfNum = len(str(n))
        arr = [None] * lenOfNum

        i=0
        product = 1
        sum = 0
        for _ in range(0,lenOfNum):
            arr[i] = int(n%10)
            n = n/10
            product *= arr[i]
            sum += arr[i]
            i = i+1

        return product-sum
```

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.  
[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms/tree/master/leetcode
