---
layout: post
title: "LeetCode 0016 3Sum Closest"
date: 2022-04-14 21:44:28 -0400
categories: [Problem Solving]
tags: [LeetCode, Python, TwoPointers, Sorting]
comments: true
---

### 1. Code
```python
class Solution:
    def threeSumClosest(self, nums: List[int], target: int) -> int:
        nums = sorted(nums)
        ans = sum(nums[0:3]) 

        for i in range(len(nums)-2):
            j, k = i+1, len(nums)-1
            while j < k:
                temp = nums[i] + nums[j] + nums[k]
                if abs(target-ans) > abs(temp-target):
                    ans = temp
                if temp < target:
                    j += 1
                elif temp > target:
                    k -= 1
                else:
                    return ans

        return ans
```

### 2. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 230 ms(92.54%), Memory usage : 13.9 MB(72.68%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
