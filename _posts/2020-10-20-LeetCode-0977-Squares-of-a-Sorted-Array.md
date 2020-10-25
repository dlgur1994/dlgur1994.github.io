---
title: "LeetCode 0977 Squares of a Sorted Array.py"
categories: LeetCode Array TwoPointers
date: 2020-10-20 17:48:28 -0400
---
#### 1. How I sloved
&nbsp;&nbsp;&nbsp;&nbsp;I squared each number and put it in a sorted list.

### 2. Code
```python
class Solution:
    def sortedSquares(self, A: List[int]) -> List[int]:
        num_squares = []
        for e in A:
            num_squares.append(e*e)
        return sorted(num_squares)
        # return sorted(list(map(lambda x: x*x, A)))
```

### 3. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 200 ms(96.64%), Memory usage : 16 MB(87.74%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
