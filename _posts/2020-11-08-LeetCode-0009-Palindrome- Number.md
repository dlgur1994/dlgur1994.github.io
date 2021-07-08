---
layout: post
title: "LeetCode 0009 Palindrome Number.py"
date: 2020-11-08 15:34:28 -0400
categories: ProblemSolving
tags: [LeetCode, Math]
comments: true
---

## 1. What I learned
### &nbsp;&nbsp;&nbsp;&nbsp;reversing a string
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;To reverse a string, write as follows.
```python
str_sam = 'hello'
print(str_sam[::-1])
#It will print 'olleh'
```

### 2. How I sloved
&nbsp;&nbsp;&nbsp;&nbsp;I had to check if the number was symmetrical. If the number was negative, it could not be symmetrical. So if the number was zero or positive, then the number was compared to the upside-down number to confirm that it was symmetrical.

### 3. Code
```python
class Solution:
    def isPalindrome(self, x: int) -> bool:
            if x>=0 and str(x)==str(x)[::-1]:
                return True
            return False
```

### 4. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 48 ms(94.78%), Memory usage : 14.2 MB(100.00%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
