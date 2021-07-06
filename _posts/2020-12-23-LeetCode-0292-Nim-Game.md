---
layout: post
title: "LeetCode 0292 Nim Game"
date: 2020-12-23 23:30:28 -0400
categories: SolveProblem
tags: [LeetCode, Brainteaser, Minimax]
comments: true
---

### 1. Code
```python
class Solution:
    def canWinNim(self, n: int) -> bool:
        # If I make the opponent get a multiple of 4, I win and if I get a multiple of 4, I lose.
        return False if n%4 == 0 else True
```

### 2. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 20 ms(98.28%), Memory usage : 14.1 MB(82.97%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
