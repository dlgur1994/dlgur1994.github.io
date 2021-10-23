---
layout: post
title: "LeetCode 0498 Diagonal Traverse"
date: 2021-10-23 16:29:28 -0400
categories: [Problem Solving]
tags: [LeetCode, Python, Array, Matrix, Simulation]
comments: true
---

### 1. Code
```python
class Solution:
    def findDiagonalOrder(self, mat: List[List[int]]) -> List[int]:
        result = []
        row, col = len(mat), len(mat[0])
        x, y = 0, 0
        dir = 'up'
        
        while True:
            result.append(mat[x][y])
            if x==row-1 and y==col-1: break
            if dir == 'up':
                if x > 0 and y < col-1: x, y = x-1, y+1
                else:
                    dir = 'down'
                    if y < col-1: y += 1
                    else: x += 1
            else:
                if x < row-1 and y > 0: x, y = x+1, y-1
                else:
                    dir = 'up'
                    if x < row-1: x += 1
                    else: y += 1

        return result
```

### 2. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 184 ms(95.05%), Memory usage : 16.7 MB(84.60%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
