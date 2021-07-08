---
layout: post
title: "LeetCode 0204 Count Primes.py"
date: 2020-11-01 15:43:28 -0400
categories: ProblemSolving
tags: [LeetCode, HashTable]
comments: true
---

### 1. What I learned
#### &nbsp;&nbsp;&nbsp;&nbsp;Sieve of Eratosthenes
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Eratosthenes sieve is the fastest way to find the prime numbers. It is to erase the multiples of that number from the smallest number. And the last remaining numbers are the pirme numbers.

### 2. How I sloved
&nbsp;&nbsp;&nbsp;&nbsp;I had to count the prime number before the input. So I used the sieve of Eratosthenes, and when I checked each number, I only had to check the root value of that number. I marked the unchecked number with one. If the number is not a prime number, it has been changed to zero. And I wrote as below because I didn't have to check the number smaller than the number I was checking.
```python
eratos[i*i:n:i] = [0] * (1 + (n-1-i*i)//i)
```  

### 3. Code
```python
class Solution:
    def countPrimes(self, n: int) -> int:
        if n < 3:
            return 0
        eratos = [1] * n
        eratos[0] = 0
        eratos[1] = 0
        i = 2
        while i*i < n:
            if eratos[i] == 1:
                eratos[i*i:n:i] = [0] * (1 + (n-1-i*i)//i)
            i += 1
        return sum(eratos)
```

### 4. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 112 ms(99.05%), Memory usage : 37.2 MB(5.03%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
