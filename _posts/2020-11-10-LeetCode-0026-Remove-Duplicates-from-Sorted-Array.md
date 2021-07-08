---
layout: post
title: "LeetCode 0026 Remove Duplicates from Sorted Array.py"
date: 2020-11-10 16:36:28 -0400
categories: ProblemSolving
tags: [LeetCode, Array, TwoPointers]
comments: true
---

### 1. How I sloved
&nbsp;&nbsp;&nbsp;&nbsp;Repeated numbers had to be moved backward from the list. When checking the numbers in the list, they were added to it if the numbers were not in 'num_dict'. And the number was moved to the n-th on the list. The number of non-repeated numbers was then returned. 

### 2. Code
```python
class Solution:
    def removeDuplicates(self, nums: List[int]) -> int:
        num_dict = {}
        cnt = 0
        for i,e in enumerate(nums):
            if e not in num_dict.keys():
                num_dict[e] = i
                nums[cnt] = e
                cnt += 1
        return cnt
```

### 3. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 68 ms(99.07%), Memory usage : 16.5 MB(92.65%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
