---
title: "LeetCode 0763 Partition Labels"
categories: LeetCode Python TwoPointers Greedy
date: 2021-02-02 23:28:28 -0400
comments: true
---

### 1. Code
```python
class Solution:
    def partitionLabels(self, S: str) -> List[int]:
        last = defaultdict(int)
        id, ptr = -1, 0
        ans = [0]
        for i, s in enumerate(S): # Store the last location of each element.
            last[s] = i
        for i, s in enumerate(S):
            id = max(id, last[s]) # id refers to the backmost position of the elements in a bundle.
            if id == i: # If the elements so far are no longer behind.
                ans.append(i-ptr+1) # Append the length of the bundle to ans.
                ptr += ans[-1] # Move ptr to the next position of the bundle.
        return ans[1:] # The first element of ans is zero, so return the remaining element except it.
```

### 2. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 32 ms(95.98%), Memory usage : 14 MB(94.63%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
