---
layout: post
title: "LeetCode 1374 Generate a String With Characters That Have Odd Counts.py"
date: 2020-09-20 14:49:28 -0400
categories: SolveProblem
tags: [LeetCode, String]
comments: true
---

## 1. How I sloved
&nbsp;&nbsp;&nbsp;&nbsp;I declared 'output'. If 'n' is even, 'a' is appended to 'output'. And 'b' is appended to 'output' for 'n-1' times.

## 2. Code
```python
class Solution:
    def generateTheString(self, n: int) -> str:
        output = ''
        if n%2==0:
            output += 'a'
        else:
            output += 'b'
        for _ in range(1,n):
            output += 'b'
        return output
```

## 3. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 28 ms(78.92%), Memory usage : 13.8 MB(52.75%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.

[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
