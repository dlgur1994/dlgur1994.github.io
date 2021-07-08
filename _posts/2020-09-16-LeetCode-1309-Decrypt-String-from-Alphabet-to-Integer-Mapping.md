---
layout: post
title: "LeetCode 1309 Decrypt String from Alphabet to Integer Mapping.py"
date: 2020-09-16 16:51:28 -0400
categories: [Problem Solving]
tags: [LeetCode, Python, String]
comments: true
---

## 1. What I learned
### &nbsp;&nbsp;&nbsp;&nbsp;a. method chr()  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;'chr(NUMBER)' returns the character of ASCII code(NUMBER).   
### &nbsp;&nbsp;&nbsp;&nbsp;a. method ord()  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;'ord(CHARACTER)' returns the ASCII code of CHARACTER.  

## 2. How I sloved
&nbsp;&nbsp;&nbsp;&nbsp;I made a stack and pushed all the elements into it. When the element was '#', I didn't push it, popped an element twice. The Popped elements are combined and pushed back in the correct order. Then I changed all the elements into characters using 'chr()' method.   

## 3. Code
```python
class Solution:
    def freqAlphabets(self, s: str) -> str:
        stack = []
        output = ''

        s = list(s)
        for e in s:
            if e == '#':
                a,b = stack.pop(), stack.pop()
                stack.append(b+a)
            else:
                stack.append(e)

        for e in stack:
            output += chr(int(e)+96)

        return output
```

## 4. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 36 ms(34.69%), Memory usage : 13.7 MB(90.95%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.

[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
