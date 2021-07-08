---
layout: post
title: "LeetCode 1365 How Many Numbers Are Smaller Than the Current Number.py"
date: 2020-03-16 23:26:28 -0400
categories: [Problem Solving]
tags: [LeetCode, Python, Array, HashTable]
comments: true
---

## 1. What I learned
### &nbsp;&nbsp;&nbsp;&nbsp;Find frequency
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;When we get the frequency of numbers, it is sometimes more efficient to list the range of numbers presented in the problem, and to increase the value of the element in which each number is indexed.  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ex) Find the frequency of each element of [4,1,1,2].   
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;sol) --> [0,2,1,0,1]

## 2. How I sloved
&nbsp;&nbsp;&nbsp;&nbsp;The range of numbers presented in the question ranged from 0 to 100, resulting in a 'countList' with 102 elements. Creating 102 elements was to prevent problems outside the scope of the index that may occur later. I increased the value of an element with an index (a+1) when accessing one element (a) in the 'num' list. Then I added all the values up to the front of the index and made them elements of the index. I made the list by approaching the value of countList with numbers in index and printed it.

## 3. Code
```python
class Solution:
    def smallerNumbersThanCurrent(self, nums: List[int]) -> List[int] :
        countList = [0] * 102
        for n in nums:
            countList[n+1] += 1
        for i in range(1,102):
            countList[i] += countList[i-1]
        return [countList[n] for n in nums]
```

## 4. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 40 ms(99.84%), Memory usage : 12.9 MB(100.00%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.

[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms/tree/master/leetcode
