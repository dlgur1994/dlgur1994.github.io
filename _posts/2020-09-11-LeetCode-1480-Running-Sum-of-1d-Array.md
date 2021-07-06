---
layout: post
title: "LeetCode 1480 Running Sum of 1d Array.py"
date: 2020-09-11 17:49:28 -0400
categories: SolveProblem
tags: [LeetCode, Array]
comments: true
---

## 1. How I sloved
&nbsp;&nbsp;&nbsp;&nbsp;I made a variable named 'sum', add it with each element of 'nums' and returned the sum of each element and 'sum'.

## 2. Code
```python
class Solution:
    def runningSum(self, nums: List[int]) -> List[int]:
        sum = 0
        output_list = []

        for num in nums:
            sum += int(num)
            output_list.append(sum)
        return output_list
```

## 3. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 40 ms(74.06%), Memory usage : 13.9 MB(84.57%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.

[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
