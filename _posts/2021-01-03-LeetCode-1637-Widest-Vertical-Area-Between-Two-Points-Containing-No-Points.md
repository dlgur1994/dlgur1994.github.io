---
title: "LeetCode 1637 Widest Vertical Area Between Two Points Containing No Points"
categories: LeetCode Sort
date: 2021-01-03 13:42:28 -0400
comments: true
---

### 1. Code
```python
class Solution:
    def maxWidthOfVerticalArea(self, points: List[List[int]]) -> int:
        xs = sorted(x for x,y in points) # Extract only the x-coordinates because you need to find neighboring x-coordinates that make the biggest difference among x-coordinates.
        maxlen = 0
        for i in range(len(xs)-1): # Find two points that show the biggest difference.
            maxlen = max(maxlen, xs[i+1]-xs[i])
        return maxlen
```

### 2. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 828 ms(75.49%), Memory usage : 55.3 MB(15.92%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
