---
layout: post
title: "LeetCode 0859 Buddy Strings.py"
date: 2020-11-12 11:10:28 -0400
categories: [Problem Solving]
tags: [LeetCode, Python, String]
comments: true
---

### 1. How I sloved
&nbsp;&nbsp;&nbsp;&nbsp;If two strings exchanged two characters, it was necessary to make sure that the two strings were equal. First, if the lengths of the two strings were different, no matter what, they could not be the same. And the index of the location where the strings were different was stored. If the two strings were the same, but each string contained the same character, it could have been the same string. It meant that if the number of the indexes were not 2, even swapping the text would not make them the same. Finally, when the two letters corresponding to the index I had previously discovered were exchanged, 'True' was returned if the two lines were the same. Otherwise 'False' was returned.

### 2. Code
```python
class Solution:
    def buddyStrings(self, A: str, B: str) -> bool:
        if len(A) != len(B) or len(A)==1 or len(B)==1: return False
        diff = []
        for i in range(len(A)):
            if A[i] != B[i]: diff.append(i)
        if len(diff)==0:
            for e in A:
                temp = list(A[:])
                temp.remove(e)
                if e in temp: return True
        if len(diff) != 2: return False
        if A[diff[0]]==B[diff[1]] and A[diff[1]] == B[diff[0]]: return True
        return False
```

### 3. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 24 ms(96.73%), Memory usage : 14.1 MB(100.00%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
