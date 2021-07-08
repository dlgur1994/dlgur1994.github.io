---
layout: post
title: "LeetCode 0338 Counting Bits" 
date: 2021-02-15 00:24:28 -0400
categories: ProblemSolving
tags: [LeetCode, Python, BitManipulation, DynamicProgramming]
comments: true
---

### 1. What I learned
#### &nbsp;&nbsp;&nbsp;&nbsp;bin()
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; It is used when a number is converted to a binary number.   
```python
print(bin(4))
print(bin(5))
# 100
# 101
```

### 2. Code
```python
class Solution:
    def countBits(self, num: int) -> List[int]:
        dp = [0]
        for i in range(1, num+1): # You have to find the rules by writing it yourself
            if i%2 == 1:
                dp.append(dp[i-1]+1)
            else:
                dp.append(dp[i//2])
        return dp
```

### 3. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 76 ms(89.95%), Memory usage : 20.8 MB(78.32%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
