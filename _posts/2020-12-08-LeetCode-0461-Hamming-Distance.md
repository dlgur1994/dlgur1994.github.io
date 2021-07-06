---
layout: post
title: "LeetCode 0461 Hamming Distance.py"
date: 2020-12-08 11:48:28 -0400
categories: SolveProblem
tags: [LeetCode, BitManipulation]
comments: true
---

## 1. What I learned
### &nbsp;&nbsp;&nbsp;&nbsp;format(Number, "b") and bin(Number)
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;They change a number to binary.
```python
print(format(10, "b"))
#1010
print(bin(10))
#0b1010
```

### 2. Code
```python
class Solution:
    def hammingDistance(self, x: int, y: int) -> int:
        cnt = 0
        # change x and y to binary
        new_x, new_y = format(x, "b"), format(y, "b")
        # new_x, new_y = bin(x)[2:], bin(y)[2:]

        #find the short binary and the long binary
        if len(new_x)<len(new_y):
            short, long = new_x, new_y
        else:
            short, long = new_y, new_x

        #add the number of 1 in the long over length of the short to cnt
        cnt += long[:-(len(short))].count("1")

        #Compare the binary number of the short and the long and add 1 to cnt if different.
        for i in range(1,len(short)+1):
            if short[-i] != long[-i]:
                cnt += 1
        return cnt
```

### 3. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 28 ms(76.19%), Memory usage : 14.4 MB(14.20%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
