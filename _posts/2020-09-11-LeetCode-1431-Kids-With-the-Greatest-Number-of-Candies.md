---
layout: post
title: "LeetCode 1431 Kids With the Greatest Number of Candies.py"
date: 2020-09-11 17:29:28 -0400
categories: [Problem Solving]
tags: [LeetCode, Python, Array]
comments: true
---

## 1. What I learned
### &nbsp;&nbsp;&nbsp;&nbsp;a. method max()  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;'max(List)' returns the largest value in List.   

## 2. How I sloved
&nbsp;&nbsp;&nbsp;&nbsp;I added elements of 'candies' and 'extraCandies' and compared them with the largest value in 'candies'. If the sum of elements and 'extraCandies' exceeds the largest value, return 'True' otherwise return 'False'.  

## 3. Code
```python
class Solution:
    def kidsWithCandies(self, candies: List[int], extraCandies: int) -> List[bool]:
        output_list = []
        for candy in candies:
            if candy+extraCandies >= max(candies):
                output_list.append(True)
            else:
                output_list.append(False)
        return output_list
```

## 4. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 40 ms(59.94%), Memory usage : 13.9 MB(30.43%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.

[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
