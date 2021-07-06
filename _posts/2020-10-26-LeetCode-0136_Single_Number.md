---
layout: post
title: "LeetCode 0136 Single Number.py"
date: 2020-10-26 09:45:28 -0400
categories: SolveProblem
tags: [LeetCode, BitManipulation, HashTable]
comments: true
---

### 1. How I sloved
&nbsp;&nbsp;&nbsp;&nbsp;I had to find the number that appeared only once. I made a dictionary, and if the number first came out, it was added to the dictionary. Otherwise the number was erased from the dictionary. Then the only number in the dictionary was returned.

### 2. Code
```python
class Solution:
    def singleNumber(self, nums: List[int]) -> int:
        check_dict = {}
        for e in nums:
            if e not in check_dict:
                check_dict[e] = 1
            else:
                del check_dict[e]
        return list(check_dict.keys())[0]
```

### 3. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 120 ms(50.75%), Memory usage : 16.3 MB(30.65%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.

[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
