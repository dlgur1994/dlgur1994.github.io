---
layout: post
title: "LeetCode 0605 Can Place Flowers.py"
date: 2020-12-06 21:45:28 -0400
categories: [Problem Solving]
tags: [LeetCode, Python, Array, Greedy]
comments: true
---

### 1. Code
```python
class Solution:
    def canPlaceFlowers(self, flowerbed: List[int], n: int) -> bool:
        cnt = 0
        # to apply the same conditions when the front or the back of the list is zero, put zero on the front and back of the list.
        flowerbed = [0] + flowerbed + [0]
        for i in range(1,len(flowerbed)-1):
            if flowerbed[i] == 1:
                continue
            if flowerbed[i-1]+flowerbed[i+1] == 0:
                flowerbed[i] = 1
                cnt += 1
        return cnt >= n
```

### 2. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 160 ms(73.33%), Memory usage : 14.6 MB(66.08%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
