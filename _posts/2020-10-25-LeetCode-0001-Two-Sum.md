---
title: "LeetCode 0001 Two Sum.py"
categories: LeetCode Solution Hash Array
date: 2020-10-25 15:00:28 -0400
---
### 1. How I sloved
&nbsp;&nbsp;&nbsp;&nbsp;I had to find a pair of numbers with a sum of the target. I looked in turn from the beginning. If (target-number) were in num_dict, I returned the indexes, otherwise (number: index) was added to num_dict.

### 2. Code
```python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        num_dict = {}
        for i in range(len(nums)):
            if (target-nums[i]) in num_dict:
                return num_dict[target-nums[i]],i
            else:
                num_dict[nums[i]] = i
```

### 3. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 44 ms(91.93%), Memory usage : 15.3 MB(16.52%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.

[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
