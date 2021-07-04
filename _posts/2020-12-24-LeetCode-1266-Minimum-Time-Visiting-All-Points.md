---
title: "LeetCode 1266 Minimum Time Visiting All Points"
categories: LeetCode Array Geometry
date: 2020-12-24 11:41:28 -0400
comments: true
---

### 1. Code
```python
class Solution:
    def minTimeToVisitAllPoints(self, points: List[List[int]]) -> int:
        '''
        Diagonal movement allows coordinates to be moved with minimal movement.
        Therefore, I obtain the maximum number of diagonal movements between two points.
        This is the smaller of the x-coordinates or the y-coordinates.
        Then add a move that cannot be made diagonally.
        '''
        cnt = 0
        for i in range(len(points)-1):
            x = abs(points[i][0]-points[i+1][0])
            y = abs(points[i][1]-points[i+1][1])
            min_val = min(x,y)
            cnt += x+y-min_val
        return cnt
```

### 2. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 52 ms(93.53%), Memory usage : 14 MB(92.71%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
