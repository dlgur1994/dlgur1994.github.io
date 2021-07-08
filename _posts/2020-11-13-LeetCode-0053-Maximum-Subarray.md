---
layout: post
title: "LeetCode 0053 Maximum Subarray.py"
date: 2020-11-13 17:30:28 -0400
categories: ProblemSolving
tags: [LeetCode, Array, DivideAndConquer, DynamicProgramming]
comments: true
---

#### 1. How I sloved
&nbsp;&nbsp;&nbsp;&nbsp;The largest sum of successive subarrays had to be found. The first element was set to 'max', which temporarily stores the largest sum. All the elements were accessed one by one to check if they made the sum larger. If the sum ('temp') is less than zero, then 'temp' has been changed to the current element. Then 'temp' was compared to 'max' and the larger one became 'max'. Finally, 'max' was returned.

### 2. Code
```python
class Solution:
    def maxSubArray(self, nums: List[int]) -> int:
        max = temp = nums[0]
        for i in range(1,len(nums)):
            temp = temp+nums[i] if temp>0 else nums[i]
            max = temp if temp>max else max
        return max
```

### 3. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 48 ms(99.89%), Memory usage : 14.9 MB(41.41%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
