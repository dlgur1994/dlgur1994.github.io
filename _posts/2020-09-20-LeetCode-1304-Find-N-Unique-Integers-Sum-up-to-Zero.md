---
title: "LeetCode 1304 Find N Unique Integers Sum up to Zero.py"
categories: LeetCode solution
date: 2020-09-20 00:30:28 -0400
---

## 1. How I sloved
&nbsp;&nbsp;&nbsp;&nbsp;I declared 'output' and 'k'. If 'n' is odd, 0 is appended to 'output'. And 'k' is appended to 'output' and I added 1 to 'k'. This process was repeated 'n/2' times.

## 2. Code
```python
class Solution:
    def sumZero(self, n: int) -> List[int]:
        output,k = [],1
        if n%2==1:
            output.append(0)
        for _ in range(0,int(n/2)):
            output.append(k)
            output.append(-k)
            k += 1
        return output
```

## 3. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 28 ms(91.03%), Memory usage : 13.9 MB(60.34%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.

[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
