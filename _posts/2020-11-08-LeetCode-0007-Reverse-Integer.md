---
title: "LeetCode 0007 Reverse Integer.py"
categories: LeetCode Math
date: 2020-11-08 16:18:28 -0400
comments: true
---

### 1. How I sloved
&nbsp;&nbsp;&nbsp;&nbsp;The order of numbers had to be reversed. I reversed the number using '[::-1]'. The most important thing was to check if the number was within the 32-bit range of numbers. If the number was not in range, zero was returned. Otherwise the reversed number was returned. 

### 2. Code
```python
class Solution:
    def reverse(self, x: int) -> int:
        if x<0:
            x = -int(str(-x)[::-1])
        else:
            x = int(str(x)[::-1])
        if x>2**31-1 or x<-(2**31):
            return 0
        return x
```

### 3. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 28 ms(84.99%), Memory usage : 14.1 MB(99.99%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
