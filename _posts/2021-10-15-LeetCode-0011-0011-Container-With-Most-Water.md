---
layout: post
title: "LeetCode 0011 Container With Most Water"
date: 2021-10-15 18:31:28 -0400
categories: [Problem Solving]
tags: [LeetCode, Python, Array, Greedy, TwoPointers]
comments: true
---

### 1. How I Solved
When I checked the all cases, a timeout occurred. So I identified all the possible cases, but adopted a faster method. First of all, it was narrowed inward from both ends of the line, which used the property that the longer the length of the bottom, the larger it becomes. And the higher the height, the larger the area of the rectangle, so the height of the two points was compared to change the position of the smaller points. In this way, the maximum area was found.

### 2. Code
```python
class Solution:
    def maxArea(self, height: List[int]) -> int:
        max_area = 0
        head, tail = 0, len(height)-1
        while head < tail:
            area = (tail-head) * min(height[head], height[tail])
            max_area = max(max_area, area)
            if height[head] > height[tail]:
                tail -= 1
            else:
                head += 1
        return max_area
```

### 3. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 728 ms(79.78%), Memory usage : 27.7 MB(22.75%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
