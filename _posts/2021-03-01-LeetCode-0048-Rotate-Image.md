---
title: "LeetCode 0048 Rotate Image"
categories: LeetCode Python Array
date: 2021-03-01 23:44:28 -0400
comments: true
---

### 1. Code
```python
class Solution:
    def rotate(self, matrix: list) -> None:
        l = len(matrix)-1
        for i in range(len(matrix)//2): # the number of edges
            for j in range(i, len(matrix[0])-i-1): # the number of times an array must be rotated from that edge
                # the rotating elements change continuously
                temp = matrix[i][j]
                matrix[i][j] = matrix[l-j][i]
                matrix[l-j][i] = matrix[l-i][l-j]
                matrix[l-i][l-j] = matrix[j][l-i]
                matrix[j][l-i] = temp
```

### 2. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 28 ms(96.02%), Memory usage : 14.1 MB(96.08%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
