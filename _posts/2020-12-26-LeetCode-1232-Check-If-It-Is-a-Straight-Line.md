---
layout: post
title: "LeetCode 1232 Check If It Is a Straight Line"
date: 2020-12-26 14:58:28 -0400
categories: SolveProblem
tags: [LeetCode, Array, Geometry, Math]
comments: true
---

### 1. Code
```python
class Solution:
    def checkStraightLine(self, coordinates: List[List[int]]) -> bool:
        # When the x-values of the first coordinate and the second coordinate are the same
        if coordinates[1][0] == coordinates[0][0]:
            for i in range(2,len(coordinates)):
                if coordinates[0][0]!=coordinates[i][0]:
                    return False

        # When the x-values of the first and second coordinates differ
        else:
            try: # The x-values of the coordinates must all be different, so if the x-values are the same, an exception occurs
                incline = (coordinates[1][1]-coordinates[0][1])/(coordinates[1][0]-coordinates[0][0])
                for i in range(2,len(coordinates)):
                    if incline != (coordinates[i][1]-coordinates[0][1])/(coordinates[i][0]-coordinates[0][0]):
                        return False
            except ZeroDivisionError:
                return False
        return True
```

### 2. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 56 ms(90.59%), Memory usage : 14.6 MB(52.42%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
