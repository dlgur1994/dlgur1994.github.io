---
layout: post
title: "LeetCode 1033 Moving Stones Until Consecutive"
date: 2020-12-24 00:22:28 -0400
categories: [Problem Solving]
tags: [LeetCode, Python, Brainteaser]
comments: true
---

### 1. Code
```python
class Solution:
    def numMovesStones(self, a: int, b: int, c: int) -> List[int]:
        a,b,c = sorted([a,b,c])
        min = 2
        if b==a+1 or b==a+2 or c==b+1 or c==b+2: # Either two of a,b,c are side by side or two of a,b,c are two spaces apart.
            min = 1
        if b==a+1 and c==b+1: # when a,b and c are next to each other
            min = 0
        lmax = (b-a-1) if b>a+1 else 0 # Number of all cases that can come from the left
        rmax = (c-b-1) if c>b+1 else 0 # Number of all cases that can come from the right
        return min, lmax+rmax
```

### 2. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 24 ms(98.05%), Memory usage : 14.1 MB(48.83%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
