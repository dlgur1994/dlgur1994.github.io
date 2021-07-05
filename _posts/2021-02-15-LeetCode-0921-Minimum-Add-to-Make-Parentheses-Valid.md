---
title: "LeetCode 0921 Minimum Add to Make Parentheses Valid"
categories: LeetCode Python Stack Greedy
date: 2021-02-15 21:54:28 -0400
comments: true
---

### 1. Code
```python
class Solution:
    def minAddToMakeValid(self, S: str) -> int:
        stack, need = 0, 0 # 'stack' is the number of '(', and 'need' is the number of '(' required to make a parenthesis valid
        for e in S:
            if e == ')': # when the character is ')'
                if stack > 0: # when '(' appeared before
                    stack -= 1
                else: # it means '(' is needed to make a parenthesis valid
                    need += 1
            else: # when the character is '(', add one to 'stack'
                stack += 1
        return need+stack
```

### 2. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 20 ms(99.59%), Memory usage : 14.2 MB(73.03%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
