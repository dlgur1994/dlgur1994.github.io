---
title: "LeetCode 0202 Happy Number.py"
categories: LeetCode HashTable
date: 2020-11-02 16:31:28 -0400
comments: true
---

### 1. How I sloved
&nbsp;&nbsp;&nbsp;&nbsp;I had to find out if the input number was a happy number described in the problem. So I kept splitting the input and repeated it until the sum of the squares of each number was one. If there was a cycle, the number couldn't be the happy number. So if the sum was in cycle_list, False was returned.

### 2. Code
```python
class Solution:
    def isHappy(self, n: int) -> bool:
        cycle_list = []
        while True:
            sum = 0
            for i in range(len(str(n))):
                sum += (int(n%10))**2
                n /= 10
            if sum in cycle_list:
                return False
            cycle_list.append(sum)
            if sum == 1:
                return True
            n = sum
```

### 3. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 20 ms(99.74%), Memory usage : 14.1 MB(99.96%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
