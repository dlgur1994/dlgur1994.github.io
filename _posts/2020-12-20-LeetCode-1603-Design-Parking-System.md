---
layout: post
title: "LeetCode 1603 Design Parking System"
date: 2020-12-20 15:50:28 -0400
categories: SolveProblem
tags: [LeetCode, Design]
comments: true
---

### 1. Code
```python
class ParkingSystem:
    def __init__(self, big: int, medium: int, small: int):
        self.options = [big, medium, small]

    def addCar(self, carType: int) -> bool:
        # inputs are 1 or 2 or 3
        if self.options[carType-1] > 0:
            self.options[carType-1] -= 1
            return True
        else:
            return False
```

### 2. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 128 ms(96.48%), Memory usage : 14.8 MB(11.14%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
