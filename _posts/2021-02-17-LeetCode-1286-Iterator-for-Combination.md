---
title: "LeetCode 1286 Iterator for Combination"
categories: LeetCode Python BackTracking Design
date: 2021-02-17 21:36:28 -0400
comments: true
---

### 1. What I learned
#### &nbsp;&nbsp;&nbsp;&nbsp;combinations()
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; It is used when a combination is needed to get from a list.   
```python
from itertools import combinations
l = list(combinations("abcd", 3))
print(l)
# [('a', 'b', 'c'), ('a', 'b', 'd'), ('a', 'c', 'd'), ('b', 'c', 'd')]
```

### 2. Code
```python
class CombinationIterator:
    def __init__(self, characters: str, combinationLength: int):
        self.l = list(combinations(characters, combinationLength))
        self.ptr = 0
        for i in range(len(self.l)): # If a list is made with the combination function, each element must be replaced with a word because each element consists of letters connected by ',' rather than words.
            self.l[i] = ''.join(self.l[i])

    def next(self) -> str:
        self.ptr += 1
        return self.l[self.ptr-1]

    def hasNext(self) -> bool:
        return True if self.ptr<len(self.l) else False
```

### 3. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 36 ms(100.00%), Memory usage : 17 MB(8.55%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
