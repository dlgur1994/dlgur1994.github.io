---
layout: post
title: "LeetCode 0890 Find and Replace Pattern"
date: 2021-02-13 21:56:28 -0400
categories: [Problem Solving]
tags: [LeetCode, Python, String]
comments: true
---

### 1. What I learned
#### &nbsp;&nbsp;&nbsp;&nbsp;ord()
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; It is used when a character is converted to a ASCII code.   
```python
print(ord('a'))
print(ord('z'))
# 97
# 122
```

### 2. Code
```python
class Solution:
    def findAndReplacePattern(self, words: List[str], pattern: str) -> List[str]:
        output = []
        for word in words:
            if len(word) != len(pattern): # I don't have to check if the words and patterns don't match.
                continue
            mapping = {} # Dictionary to store letters and patterns
            ch = [] # List to store the characters I have verified so far
            flag = True
            for i in range(len(pattern)):
                if pattern[i] not in mapping:
                    if word[i] not in ch: # It's when a letter of the word first appears
                        mapping[pattern[i]] = word[i]
                        ch.append(word[i])
                    else: # It's when the letter of the word is mapped differently in the dictionary
                        flag = False
                        break
                else:
                    if mapping[pattern[i]] != word[i]: # This is when the letter of the word is different from that already stored in the dictionary
                        flag = False
                        break
            if flag == True:
                output.append(word)
        return output
```

### 3. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 24 ms(98.44%), Memory usage : 14.1 MB(88.46%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
