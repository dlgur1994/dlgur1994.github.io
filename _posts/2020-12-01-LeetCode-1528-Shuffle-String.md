---
title: "LeetCode 1528 Shuffle String.py"
categories: LeetCode Sort
date: 2020-12-01 13:19:28 -0400
comments: true
---

### 1. Code
```python
class Solution:
    def restoreString(self, s: str, indices: List[int]) -> str:
        new_str = [""] * len(indices)
        for i, index in enumerate(indices):
            new_str[index] = s[i]
        return "".join(new_str)
```

### 2. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 48 ms(90.10%), Memory usage : 14.2 MB(14.33%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
