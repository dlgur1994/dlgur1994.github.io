---
layout: post
title: "LeetCode 0038 Count and Say.py"
date: 2020-11-11 10:58:28 -0400
categories: SolveProblem
tags: [LeetCode, String]
comments: true
---

### 1. How I sloved
&nbsp;&nbsp;&nbsp;&nbsp;The number had to be changed for 'n' times. The rule was to write the number of repeated numbers and that number for all numbers. I used 'pre' to store the number before it when the number was different. All elements were checked for each iteration. The number of repeated numbers and that number were added to 'temp' when the number was different or when the index was the end of the list. 'output' was changed to 'temp'. I did this process for 'n' times and the 'output' changed to the string was returned.

### 2. Code
```python
class Solution:
    def countAndSay(self, n: int) -> str:
        output = [1]
        for i in range(1,n):
            temp = []
            pre = 0
            for j in range(len(output)):
                if output[j] != output[pre]:
                    temp.extend([j-pre,output[pre]])
                    pre = j
                if j == len(output)-1:
                    temp.extend([j-pre+1,output[pre]])
            output = temp
        return ''.join(map(str,output))
```

### 3. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 28 ms(96.10%), Memory usage : 14.5 MB(99.98%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
