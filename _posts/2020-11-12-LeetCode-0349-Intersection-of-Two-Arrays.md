---
layout: post
title: "LeetCode 0349 Intersection of Two Arrays.py"
date: 2020-11-12 16:46:28 -0400
categories: SolveProblem
tags: [LeetCode, BinarySearch, HashTable, Sort, TwoPointers]
comments: true
---

## 1. What I learned
### &nbsp;&nbsp;&nbsp;&nbsp;Finding common values in lists
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Converting a list to a set clears duplicate values and the '&' operator selects common values from lists.

### 2. How I sloved
&nbsp;&nbsp;&nbsp;&nbsp;Common values in the lists had to be found. So I just used 'set' and the '&' operator.

### 3. Code
```python
class Solution:
    def intersection(self, nums1: List[int], nums2: List[int]) -> List[int]:
        return set(nums1) & set(nums2)
```

### 4. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 44 ms(72.73%), Memory usage : 14.3 MB(100.00%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
