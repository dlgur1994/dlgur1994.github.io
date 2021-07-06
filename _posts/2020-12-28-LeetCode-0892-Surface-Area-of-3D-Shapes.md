---
layout: post
title: "LeetCode 0892 Surface Area of 3D Shapes"
date: 2020-12-28 16:13:28 -0400
categories: SolveProblem
tags: [LeetCode, Geometry, Math]
comments: true
---

### 1. Code
```python
class Solution:
    def surfaceArea(self, grid: List[List[int]]) -> int:
        n = len(grid)
        bottom = 0
        row = 0
        col = 0
        for i in range(n):
            for j in range(n):
                # If a block exists, there are upper and lower sides. Therefore, add 1 to the width of the lower face and eventually double the area of the lower face to obtain the area of the upper and lower sides.
                if grid[i][j] > 0:
                    bottom += 1

                # Obtain the area of the first and last rows.
                if i==0 or i==n-1:
                    if j==0 or j==n-1:
                        row += grid[i][j]
                    col += grid[i][j]

                # Obtain the side area of the blocks except the first and last blocks of both sides.
                if j==0 or j==n-1:
                    if i>0 and i<n-1:
                        row += grid[i][j]

                # Both side areas can be obtained by the difference between the number of blocks in the next space.
                if j>0 and j<n:
                    row += abs(grid[i][j] - grid[i][j-1])

                # The area of the front and back is obtained by the difference between the number of blocks in the next space.
                if i>0 and i<n:
                    col += abs(grid[i][j] - grid[i-1][j])

        # If the length of the grid is 1, double the width of the front, back, and sides.
        if n == 1:
            row *= 2
            col *= 2
        return bottom*2 + row + col
```

### 2. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 76 ms(96.72%), Memory usage : 14.5 MB(10.58%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
