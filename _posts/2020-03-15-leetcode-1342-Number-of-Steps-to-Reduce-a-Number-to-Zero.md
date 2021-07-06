---
layout: post
title: "LeetCode 1342 Number of Steps to Reduce a Number to Zero.py"
date: 2020-03-15 23:55:28 -0400
categories: SolveProblem
tags: [LeetCode, BitManipulation]
comments: true
---

## 1. What I learned
### &nbsp;&nbsp;&nbsp;&nbsp;'/=' vs '//='
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;'/' is dividing the first operand by the second and the result always has type float. '//' is a division, rounded to the next smallest whole number.  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ex) 5/2 = 2.5   
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ex) 5//2 = 2

## 2. How I sloved
&nbsp;&nbsp;&nbsp;&nbsp;When the number is even, I divided the number in half. And when the number is odd, I took one out of it. Whenever that happened, I added one to the 'count'.

## 3. Code
```python
class Solution:
    def numberOfSteps (self, num: int) -> int:
        count = 0
        while num > 0:
            if num%2 == 0:
                num //= 2
            else:
                num -= 1
            count += 1
        return count
```

## 4. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 16 ms(99.31%), Memory usage : 12.7 MB(100.00%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.

[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms/tree/master/leetcode
