---
layout: post
title: "LeetCode 0059 Spiral Matrix II"
date: 2021-10-16 00:45:28 -0400
categories: [Problem Solving]
tags: [LeetCode, Python, Array, Matrix, Simulation]
comments: true
---

### 1. Code
```python
class Solution:
    def generateMatrix(self, n: int) -> List[List[int]]:
        matrix = [[0] * n for i in range(n)]
        x, y = 0, 0
        num, cnt = 1, n
        while num < n*n+1:
            for _ in range(0, cnt):
                matrix[y][x] = num
                num += 1
                x += 1
            x -= 1
            y += 1
            cnt -= 1
        
            for _ in range(0, cnt):
                matrix[y][x] = num
                num += 1
                y += 1
            x -= 1
            y -= 1

            for _ in range(0, cnt):
                matrix[y][x] = num
                num += 1
                x -= 1
            x += 1
            y -= 1
            cnt -= 1
           
            for _ in range(0, cnt):
                matrix[y][x] = num
                num += 1
                y -= 1
            x += 1
            y += 1

        return matrix
```

### 2. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 24 ms(97.26%), Memory usage : 14.3 MB(75.31%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
