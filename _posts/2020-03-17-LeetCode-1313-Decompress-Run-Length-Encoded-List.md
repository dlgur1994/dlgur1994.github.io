---
layout: post
title: "LeetCode 1313 Decompress Run-Length Encoded List.py"
date: 2020-03-17 23:26:28 -0400
categories: ProblemSolving
tags: [LeetCode, Array]
comments: true
---

## 1. What I learned
### &nbsp;&nbsp;&nbsp;&nbsp;Create a list with a repeated number when I know the length of a list
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Write a number in a []. Multiply it by the length of the list.  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ex) numList = [5]*3  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;--> numList = [5,5,5]

## 2. How I sloved
&nbsp;&nbsp;&nbsp;&nbsp;I made a list and repeated 'nums//2' to make the final list. Because the list had a pattern that odd numbers were the frequency of even numbers. Then I concatenated the even numbers to the 'result' list as many odd numbers.  

## 3. Code
```python
class Solution:
    def decompressRLElist(self, nums):
        result = []
        for i in range(0,len(nums)//2):
            result += [nums[2*i+1]] * nums[2*i]
        return result
```

## 4. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 64 ms(87.63%), Memory usage : 13.3 MB(100.00%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.

[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms/tree/master/LeetCode
