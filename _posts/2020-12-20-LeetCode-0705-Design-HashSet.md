---
title: "LeetCode 0705 Design HashSet"
categories: LeetCode HashTable Design
date: 2020-12-20 16:25:28 -0400
comments: true
---

### 1. Code
```python
class MyHashSet:
    def __init__(self):
        self.my_hash = {}

    def add(self, key: int) -> None:
        self.my_hash[key] = "dummy"

    def remove(self, key: int) -> None:
        if key in self.my_hash:
            del self.my_hash[key]

    def contains(self, key: int) -> bool:
        if key in self.my_hash:
            return True
        else:
            return False
```

### 2. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 136 ms(98.60%), Memory usage : 19 MB(54.50%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
