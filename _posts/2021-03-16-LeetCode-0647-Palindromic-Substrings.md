---
layout: post
title: "LeetCode 0647 Palindromic Substrings"
date: 2021-03-16 15:57:28 -0400
categories: SolveProblem
tags: [LeetCode, Python, DynamicProgramming, String]
comments: true
---

### 1. Code
```python
class Solution:
    def countSubstrings(self, s: str) -> int:
        ans = 0
        for i in range(len(s)):
            mid1,mid2 = i,i # suppose the length of the string looked for is odd
            while mid1>-1 and mid2<len(s) and s[mid1]==s[mid2]:
                mid1 -= 1
                mid2 += 1
                ans += 1
            mid1,mid2 = i,i+1 # suppose the length of the string looked for is even
            while mid1>-1 and mid2<len(s) and s[mid1]==s[mid2]:
                mid1 -= 1
                mid2 += 1
                ans += 1
        return ans
```

### 2. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 124 ms(85.56%), Memory usage : 14 MB(96.38%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
