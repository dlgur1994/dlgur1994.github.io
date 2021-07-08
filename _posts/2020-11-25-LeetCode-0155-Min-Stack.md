---
layout: post
title: "LeetCode 0155 Min Stack.py"
date: 2020-11-25 13:38:28 -0400
categories: [Problem Solving]
tags: [LeetCode, Python, Design, Stack]
comments: true
---

## 1. What I learned
### &nbsp;&nbsp;&nbsp;&nbsp;Time complexity in List
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;O(1): append(), pop()
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;O(n): del[], min(), max()

### 2. How I sloved
&nbsp;&nbsp;&nbsp;&nbsp;The time complexity of each function of the stack had to be all O(1). For use in the 'pop()'' function, 'mins' to store the minimum values and 'min_value' to store the minimum value were used. In the function 'push()', the input value was stored in 'stack' was entered, and if 'min_value' was 'none' or equal to the input value, the input was stored in 'mins'. In 'pop()', if the popped value from 'stack' was the same as the last element of 'mins', the built-in function 'pop()' occured in 'mins', and if there was an element in 'mins', 'min_value' pointed to the last element of 'mins'. 'top()' referred to the last element of 'stack'. 'getMin()' returned 'min_value'.  

### 3. Code
```python
class MinStack:
    def __init__(self):
        self.stack = []
        self.mins = []
        self.min_value = None

    def push(self, x: int) -> None:
        if self.min_value==None or self.min_value>=x:
            self.min_value = x
            self.mins.append(x)
        self.stack.append(x)

    def pop(self) -> None:
        if self.stack.pop() == self.mins[-1]:
            self.mins.pop()
            self.min_value = self.mins[-1] if self.mins != [] else None

    def top(self) -> int:
        return self.stack[-1]

    def getMin(self) -> int:
        return self.min_value
```

### 4. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 48 ms(98.45%), Memory usage : 18.1 MB(35.26%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
