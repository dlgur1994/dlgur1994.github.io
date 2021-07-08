---
layout: post
title: "LeetCode 1395 Count Number of Teams"
date: 2021-01-01 10:13:28 -0400
categories: ProblemSolving
tags: [LeetCode, Array]
comments: true
---

### 1. Code
```python
'''
Check one by one from the back of the list.
Think of the case in which the number in front (ith) < the number in the back (jth) or 'ith' >= 'jth'.
If 'ith' is greater than 'jth', add 1 to list up[i].
Otherwise, add 1 to list down[i].
Add the number up/down [j] to 'result'.
This is to find something like this situation in the back when it is ith<jth or ith>=jth.
'''
class Solution:
    def numTeams(self, rating: List[int]) -> int:
        n = len(rating)
        up = [0] * n
        down = [0] * n
        result = 0
        for i in range(n-2, -1, -1):
            for j in range(i+1, n):
                if rating[i] < rating[j]:
                    up[i] += 1
                    result += up[j]
                else:
                    down[i] += 1
                    result += down[j]
        return result
```

### 2. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 56 ms(94.55%), Memory usage : 14.2 MB(73.62%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
