---
layout: post
title: "LeetCode 1025 Divisor Game.py"
date: 2020-11-22 14:12:28 -0400
categories: SolveProblem
tags: [LeetCode, DynamicProgramming, Math]
comments: true
---

#### 1. How I sloved
&nbsp;&nbsp;&nbsp;&nbsp;While checking each number from 2, I found out that Alice's turn must be even to win. So True was returned when the input value, N, was even. Otherwise, False was returned.

### 2. Code
```python
class Solution:
    def divisorGame(self, N: int) -> bool:
        if N%2 == 0:
            return True
        else:
            return False
```

### 3. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 20 ms(98.02%), Memory usage : 14.1 MB(34.36%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
