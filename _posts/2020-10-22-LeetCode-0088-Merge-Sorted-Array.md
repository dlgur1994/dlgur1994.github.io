---
title: "LeetCode 0088 Merge Sorted Array.py"
categories: LeetCode Array
date: 2020-10-22 23:33:28 -0400
---

#### 1. How I sloved
&nbsp;&nbsp;&nbsp;&nbsp;n is the number of characters to add to the first list. I kept looking for 0 in nums1 and switched it to element in nums2 in order. Then I sorted out nums1.

### 2. Code
```python
class Solution:
    def merge(self, nums1: List[int], m: int, nums2: List[int], n: int) -> None:
        """
        Do not return anything, modify nums1 in-place instead.
        """
        for i in range(n):
            nums1[nums1.index(0)] = nums2[i]
        nums1.sort()
```

### 3. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 32 ms(89.83%), Memory usage : 14 MB(100.00%)
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
