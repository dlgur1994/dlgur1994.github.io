---
layout: post
title: "LeetCode 0167 Two Sum II - Input array is sorted.py" 
date: 2020-11-09 15:21:28 -0400
categories: [Problem Solving]
tags: [LeetCode, Python, Array, BinarySearch, TwoPointers]
comments: true
---

### 1. How I sloved
&nbsp;&nbsp;&nbsp;&nbsp;I had to figure out a pair whose total was 'target'. I used the dictionary to save time. I checked from the first element of 'numbers' to see if there was any number in the dictionary that could make 'target' in addition to the element. If not, the number and index were added to the dictionary. Otherwise, the indexes were returned.

### 2. Code
```python
class Solution:
    def twoSum(self, numbers: List[int], target: int) -> List[int]:
        val_dict = {}
        for i, e in enumerate(numbers):
            if target-e in val_dict.keys():
                return [val_dict[target-e], i+1]
            val_dict[e] = i+1
```

### 3. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 52 ms(98.34%), Memory usage : 14.3 MB(11.89%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
