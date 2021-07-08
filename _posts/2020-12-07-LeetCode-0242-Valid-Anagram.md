---
layout: post
title: "LeetCode 0242 Valid Anagram.py"
date: 2020-12-07 9:59:28 -0400
categories: ProblemSolving
tags: [LeetCode, HashTable, Sort]
comments: true
---

## 1. What I learned
### &nbsp;&nbsp;&nbsp;&nbsp;Counter()
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;It makes a dictionary that counts the number of each element. And it is O(n).
```python
from collections import Counter
nums = [1,2,3,2,1,5,4]
print(Counter(nums))
# Counter({1: 2, 2: 2, 3: 1, 5: 1, 4: 1})
```

### 2. Code
```python
class Solution:
    def isAnagram(self, s, t):
        return Counter(s) == Counter(t)
#sort() is O(nlogn) / Counter() is O(n) --> So I used Counter()
```

### 3. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 40 ms(84.32%), Memory usage : 14.5 MB(44.13%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
