---
layout: post
title: "LeetCode 0885 Spiral Matrix III"
date: 2021-01-19 22:24:28 -0400
categories: ProblemSolving
tags: [LeetCode, Math]
comments: true
---

### 1. Code
```python
class Solution:
    def spiralMatrixIII(self, R: int, C: int, r0: int, c0: int) -> List[List[int]]:
        output = ([[r0,c0]])
        cnt = 0
        while len(output)< R*C: # Verify that all elements are in output
            for j in range(2*cnt+1): # go 2n+1 times to the right
                c0 += 1
                if r0>-1 and r0<R and c0>-1 and c0<C: # Check the coordinate is in range
                    output.append([r0, c0])
            for j in range(2*cnt+1): # go down 2n+1 times
                r0 += 1
                if r0>-1 and r0<R and c0>-1 and c0<C:
                    output.append([r0, c0])
            for j in range(2*cnt+2): # go 2n+1 times to the left
                c0 -= 1
                if r0>-1 and r0<R and c0>-1 and c0<C:
                    output.append([r0, c0])
            for j in range(2*cnt+2): # go up 2n+1 times
                r0 -= 1
                if r0>-1 and r0<R and c0>-1 and c0<C:
                    output.append([r0, c0])
            cnt += 1
        return output
```

### 2. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 100 ms(98.10%), Memory usage : 15.3 MB(44.78%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
