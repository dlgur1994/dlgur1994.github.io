---
layout: post
title: "LeetCode 0169 Majority Element.py"
date: 2020-11-13 10:30:28 -0400
categories: SolveProblem
tags: [LeetCode, Array, BitManipulation, DivideAndConquer]
comments: true
---

## 1. What I learned
### &nbsp;&nbsp;&nbsp;&nbsp;a. man(iterable, key)
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;It returns the biggest 'key' among 'iterable'.
```python
max(-5, 1, 2)
#It will return 2
nums = {'h': 1, 'e': 1, 'l': 2, 'o': 1}
max(nums, key = lambda x : nums[x])
 #It will return 'l'
```
### &nbsp;&nbsp;&nbsp;&nbsp;b. Counter()
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;It counts the number of each element. And the Counter().most_common(1) returns the key with the most frequent value.
```python
print(Counter('hello'))
#it will print Counter({'l': 2, h': 1, 'e': 1, 'o': 1})
print(Counter([1,2,2,3]))
#it will print Counter({'2': 2, '1': 1, '3': 3})
print(Counter([1,2,2,2,3]).most_common(1))
#it will print [(2, 3)]
print(Counter([1,2,2,2,3]).most_common(1)[0][0])
#it will print 2
```

### 2. How I sloved
&nbsp;&nbsp;&nbsp;&nbsp;I had to find an element that appeared more than half the length of the array. So I used 'Counter(') to get the frequency of all the elements. And a key value with a value greater than half the length of the array was returned.

### 3. Code
```python
class Solution:
    def majorityElement(self, nums: List[int]) -> int:
        counts = Counter(nums)
        half = len(nums)//2
        for e in counts:
            if counts[e] > half:
                return e
```

### 4. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 152 ms(94.39%), Memory usage : 15.2 MB(75.60%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
