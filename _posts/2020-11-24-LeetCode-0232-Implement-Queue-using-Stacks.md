---
layout: post
title: "LeetCode 0232 Implement Queue using Stacks.py"
date: 2020-11-24 10:57:28 -0400
categories: ProblemSolving
tags: [LeetCode, Design, Stack]
comments: true
---

#### 1. How I sloved
&nbsp;&nbsp;&nbsp;&nbsp;Heap had to be made into two stacks: 'stackin' and 'stackout'. 'stackin' was used for push(), peek(), empty(), and pop(), and 'stackout' was used only for pop(). The new element was added at the end of the 'stackin' using the built-in function 'append()' in 'push()', the first element was pointed in 'peek()', and the length of 'stackin' was checked to be 0 or not in 'empty()'. All elements were copied from 'stackin' to 'stackout', the built-in function 'pop()' was used in 'stackout'. And the first element of 'stackin' was deleted. 

### 2. Code
```python
class MyQueue:
    def __init__(self):
        self.stackin = []
        self.stackout = []

    def push(self, x: int) -> None:
        self.stackin.append(x)

    def pop(self) -> int:
        self.stackout = self.stackin[::-1]
        self.stackin = self.stackin[1::]
        return self.stackout.pop()

    def peek(self) -> int:
        return self.stackin[0]

    def empty(self) -> bool:
        return True if len(self.stackin)==0 else False
```

### 3. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 20 ms(98.36%), Memory usage : 14.2 MB(9.87%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
