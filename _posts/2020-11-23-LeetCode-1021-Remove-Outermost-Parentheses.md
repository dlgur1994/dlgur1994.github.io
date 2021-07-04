---
title: "LeetCode 1021 Remove Outermost Parentheses.py"
categories: LeetCode Stack
date: 2020-11-23 10:53:28 -0400
---

#### 1. How I sloved
&nbsp;&nbsp;&nbsp;&nbsp;The outer parentheses had to be removed from the bundle of several parentheses. The string, S elements were approached one by one, push it into the stack if the element was "(", else sold in the stack if that was the one. The elements of the string S were approached one by one, and if it was "(" the element was pushed into the stack, and if it was ")" the stack was poped. This was to remove the "(" that paired with ")". And each element was stored in a temporary list, 'temp'. When the stack became empty, the first and the last elements of 'temp' were deleted and 'temp' was added to the output list, 'output'. 'output' changed to a string was returned after all elements were checked.

### 2. Code
```python
class Solution:
    def removeOuterParentheses(self, S: str) -> str:
        stack = []
        temp = []
        output = []
        for e in S:
            stack.pop() if e == ')' else stack.append(e)
            temp.append(e)
            if stack == []:
                del temp[0]
                temp.pop()
                output.extend(temp)
                temp = []
        return ''.join(output)
```

### 3. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 28 ms(97.90%), Memory usage : 14.2 MB(57.03%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
