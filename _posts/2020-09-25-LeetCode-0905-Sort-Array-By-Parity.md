---
layout: post
title: "LeetCode 0905 Sort Array By Parity.py"
date: 2020-09-25 17:21:28 -0400
categories: [Problem Solving]
tags: [LeetCode, Python, Array]
comments: true
---

## 1. What I learned
### &nbsp;&nbsp;&nbsp;&nbsp;a. LIST.insert(INDEX, e)
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;To insert an element in a list where you want, write as follows.
```python
LIST = [1,2,3]
LIST.insert(0,4)
print LIST
#It will print '4,1,2,3'
```

## 2. How I sloved
&nbsp;&nbsp;&nbsp;&nbsp;I added two lists, one with even numbers as element and the other with odd numbers.

## 3. Code
```python
class Solution:
    def sortArrayByParity(self, A: List[int]) -> List[int]:
        return [e for e in A if e%2==0] + [e for e in A if e%2==1]
```

## 4. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 64 ms(99.93%), Memory usage : 14.6 MB(5.67%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.

[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
