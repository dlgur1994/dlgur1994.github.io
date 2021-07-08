---
layout: post
title: "LeetCode 0944 Delete Columns to Make Sorted.py"
date: 2020-12-03 10:16:28 -0400
categories: ProblemSolving
tags: [LeetCode, Greedy]
comments: true
---

## 1. What I learned
### &nbsp;&nbsp;&nbsp;&nbsp;zip()
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;It is used to bundle data types with the same number of elements.
```python
nums = [1,2,3,4,5]
strs = ['a','b','c','d','e']
print(list(zip(nums,strs)))
#[(1, 'a'), (2, 'b'), (3, 'c'), (4, 'd'), (5, 'e')]
```

### 2. Code
```python
class Solution:
    def minDeletionSize(self, A):
        count = 0
        #The * operator was used to unzip the list.
        for items in zip(*A):  
            if sorted(items) != list(items):
                count += 1
        return count
```

### 3. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 72 ms(100.00%), Memory usage : 14.8 MB(56.40%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
