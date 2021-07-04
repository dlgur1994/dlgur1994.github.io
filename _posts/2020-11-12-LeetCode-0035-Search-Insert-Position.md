---
title: "LeetCode 0035 Search Insert Position.py"
categories: LeetCode Array BinarySearch
date: 2020-11-12 17:06:28 -0400
comments: true
---

### 1. How I sloved
&nbsp;&nbsp;&nbsp;&nbsp;If 'target' was in 'nums', the index of that number had to be returned. Otherwise, it had to return an index that could place a 'target'. So I separated the three cases. First, if 'target' was in 'nums', the index was returned. Second, if 'target' is not in 'nums' and was greater than the last element of 'nums', the (last index+1) of 'nums' was returned. Finally, if 'target' was not in 'nums' and 'target' was within 'nums' range, then the (largest index+1) of the elements smaller than 'target' was returned.

### 2. Code
```python
class Solution:
    def searchInsert(self, nums: List[int], target: int) -> int:
        if target in nums:
            return nums.index(target)
        elif target > nums[len(nums)-1]:
            return len(nums)
        else:
            for i in range(len(nums)):
                if nums[i] > target:
                    return i
```

### 3. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 40 ms(96.43%), Memory usage : 14.6 MB(85.98%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
