---
layout: post
title: "LeetCode 0973 K Closest Points to Origin"
date: 2021-03-12 15:32:28 -0400
categories: SolveProblem
tags: [LeetCode, Python, DivideAndConquer, Heap, Sort]
comments: true
---

### 1. Code
```python
class Solution:
    def kClosest(self, points: List[List[int]], k: int) -> List[List[int]]:
        points.sort(key = lambda p:p[0]*p[0]+p[1]*p[1]) # sort by the distance
        return points[:k]
```

### 2. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 588 ms(99.59%), Memory usage : 19.5 MB(95.82%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
