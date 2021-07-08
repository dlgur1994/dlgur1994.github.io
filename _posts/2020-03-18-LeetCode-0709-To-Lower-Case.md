---
layout: post
title: "LeetCode 0709 To Lower Case.py"
date: 2020-03-18 23:26:28 -0400
categories: [Problem Solving]
tags: [LeetCode, Python, String]
comments: true
---

## 1. What I learned
### &nbsp;&nbsp;&nbsp;&nbsp;a. .lower()  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;It changes every character to lower case. But using '.lower()' takes a lot of time.  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ex) print('HELLO'.lower()) --> 'hello'

### &nbsp;&nbsp;&nbsp;&nbsp;b. ord()  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;It returns an integer representing the Unicode character.  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ex) print(ord('a)) --> 97

## 2. How I sloved
&nbsp;&nbsp;&nbsp;&nbsp;Using '.lower()' took longer, so I approached all the letters. I checked if the letters were capital letters. In capital letters I changed the letter to Unicode and added 32. If it wasn't capital letters, I just connected them.  

## 3. Code
```python
class Solution:
    def toLowerCase(self, str: str) -> str:
        return ''.join([chr(ord(c)+32) if c.isupper() else c for c in str])
```

```python
class Solution:
    def toLowerCase(self, str: str) -> str:
        return str.lower()
```

## 4. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 16 ms(99.52%), Memory usage : 12.9 MB(100.00%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.

[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms/tree/master/LeetCode
