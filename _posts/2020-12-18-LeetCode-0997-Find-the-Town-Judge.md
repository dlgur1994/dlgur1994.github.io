---
layout: post
title: "LeetCode 0997 Find the Town Judge"
date: 2020-12-18 11:27:28 -0400
categories: [Problem Solving]
tags: [LeetCode, Python, Graph]
comments: true
---

### 1. Code
```python
class Solution:
    def findJudge(self, N: int, trust: List[List[int]]) -> int:
        # followers of each person
        followers = [[0] for i in range(N+1)]
        # candidates who can be a judge
        candidates = [i for i in range(0,N+1)]
        judge = -1
        # if there is only one person, the person is the judge
        if N == 1:
            judge = 1
        elif N > 1:
            for e in trust:
                followers[e[1]].append(e[0])
                # if a person follows someone, the person can't be a judge
                candidates[e[0]] = -1
                if len(followers[e[1]]) == N:
                    judge = e[1]
                if judge not in candidates:
                    judge = -1
        return judge
```

### 2. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 728 ms(67.86%), Memory usage : 19.2 MB(13.25%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
