---
layout: post
title: "LeetCode 0062 Unique Paths"
date: 2021-10-09 13:20:28 -0400
categories: [Problem Solving]
tags: [LeetCode, Python, Combinatorics, DynamicProgramming, Math]
comments: true
---

### 1. Code
```python
class Solution:
  def uniquePaths(self, m: int, n: int) -> int:
    map = [1 for i in range(m*n)]
    for i in range(n, m*n):
      if (i%n) != 0:
        map[i] = map[i-1] + map[i-n]  
    return map[-1]
```

### 2. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 24 ms(96.88%), Memory usage : 14.2 MB(85.96%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
