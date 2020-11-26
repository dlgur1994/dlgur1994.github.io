---
title: "LeetCode 0020 Valid Parentheses.py"
categories: LeetCode String Stack
date: 2020-11-26 10:42:28 -0400
---

#### 1. How I sloved
&nbsp;&nbsp;&nbsp;&nbsp;When the string was entered, it was necessary to check if the parentheses matched. So, I pushed each character of the sting into the stack. If the stack was empty or the element was "(" or "[" or "{", I pushed the element into the stack. If the element was ")" or "]" or "}", I checked that it matched the last element of the stack. I popped from the stack if it was a match, or I returned False if it was not. After checking all the characters, I returned True if the stack was empty. Otherwise, I returned False.

### 2. Code
```python
class Solution:
    def isValid(self, s: str) -> bool:
        stack = []
        for e in s:
            if stack==[] or e=="(" or e=="[" or e=="{":
                stack.append(e)
            elif e==")":
                if stack[-1] == "(":
                    stack.pop()
                else:
                    return False
            elif e=="]":
                if stack[-1] == "[":
                    stack.pop()
                else:
                    return False
            elif e=="}":
                if stack[-1] == "{":
                    stack.pop()
                else:
                    return False
        return True if stack ==[] else False
```

### 3. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 28 ms(79.63%), Memory usage : 14.2 MB(18.57%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
