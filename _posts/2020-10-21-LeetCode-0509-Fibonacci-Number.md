---
title: "LeetCode 0509 Fibonacci Number.py"
categories: LeetCode Array
date: 2020-10-21 11:02:28 -0400
---

### 1. What I learned
#### &nbsp;&nbsp;&nbsp;&nbsp;Array vs Recursion in Fibonacci Sequence
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Using the array is much faster than using the recursion.
```python
if N==0: return 0;
if N==1: return 1;
fib_list = [0 for _ in range(N+1)]
fib_list[0] = 0
fib_list[1] = 1
for i in range(2,N+1):
    fib_list[i] = fib_list[i-2] + fib_list[i-1]
return fib_list[N]
# 28ms
```
```python
if N==0: return 0
elif N==1: return 1
else: return self.fib(N-1)+self.fib(N-2)
# 1000ms
```

#### 2. How I sloved
&nbsp;&nbsp;&nbsp;&nbsp;Each number in Fibonacci sequence is the sum of the two preceding ones, starting from 0 and 1. So I went on with this process, with the first of the two consecutive numbers being the next number and the other being the sum of the two consecutive numbers.

### 3. Code
```python
class Solution:
    def fib(self, N: int) -> int:
    	a, b = 0, 1
    	for _ in range(N):
        a, b = b, a + b
    	return a

'''
      if N==0: return 0;
      if N==1: return 1;
      fib_list = [0 for _ in range(N+1)]
      fib_list[0] = 0
      fib_list[1] = 1
      for i in range(2,N+1):
          fib_list[i] = fib_list[i-2] + fib_list[i-1]
      return fib_list[N]
'''

'''
      if N==0: return 0
      elif N==1: return 1
      else: return self.fib(N-1)+self.fib(N-2)
'''
```

### 4. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 20 ms(98.71%), Memory usage : 14.1 MB(99.99%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
