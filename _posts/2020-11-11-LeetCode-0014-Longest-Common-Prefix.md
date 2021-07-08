---
layout: post
title: "LeetCode 0014 Longest Common Prefix.py"
date: 2020-11-11 16:24:28 -0400
categories: [Problem Solving]
tags: [LeetCode, Python, String]
comments: true
---

### 1. How I sloved
&nbsp;&nbsp;&nbsp;&nbsp;A common prefix had to be found. \"\" was returned if there were no elements in the list. The first element was set as the reference point, all the words were checked from the first letter to the other letter, and the common prefix was set before the other characters were present.The prefix so found was returned. But if any one element was empty, \"\" returned.

### 2. Code
```python
class Solution:
    def longestCommonPrefix(self, strs: List[str]) -> str:
        if len(strs) == 0:
            return ""
        for i in range(len(strs[0])):
            for e in strs:
                if len(e)==i or e[i] != strs[0][i]:
                    return strs[0][:i]
        return strs[0]
```

### 3. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 28 ms(91.60%), Memory usage : 14.3 MB(100.00%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
