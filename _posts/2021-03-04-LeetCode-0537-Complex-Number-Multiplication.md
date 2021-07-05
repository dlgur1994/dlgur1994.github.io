---
title: "LeetCode 0537 Complex Number Multiplication"
categories: LeetCode Python Math String
date: 2021-03-04 23:50:28 -0400
comments: true
---

### 1. Code
```python
class Solution:
    def complexNumberMultiply(self, a: str, b: str) -> str:
        a, b = a[:-1], b[:-1] # Remove the 'i' at the back of a and b
        a_real, a_imag = map(int, a.split('+')) # Distinguish a real number from a imaginary number
        b_real, b_imag = map(int, b.split('+'))
        return str(a_real*b_real + -1*a_imag*b_imag) + "+" + str(a_real*b_imag + b_real*a_imag) + "i"
```

### 2. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 12 ms(100.00%), Memory usage : 14.1 MB(93.47%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
