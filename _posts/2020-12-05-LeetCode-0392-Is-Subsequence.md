---
title: "LeetCode 0392_Is_Subsequence.py"
categories: LeetCode BinarySearch DynamicProgramming Greedy
date: 2020-12-05 15:37:28 -0400
comments: true
---

### 1. Code
```python
class Solution:
    def isSubsequence(self, s: str, t: str) -> bool:
        for e in s:
            if e in t:
                # index(e) indicates the first e in a list
                idx = t.index(e)
                # make t short
                t = t[idx+1:]
            else:
                return False
        return True
```

### 2. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 24 ms(95.08%), Memory usage : 14 MB(95.27%)
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
