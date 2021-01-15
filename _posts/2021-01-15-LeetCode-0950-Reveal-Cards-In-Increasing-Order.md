---
title: "LeetCode 0950 Reveal Cards In Increasing Order"
categories: LeetCode Array Simulation
date: 2021-01-15 23:02:28 -0400
comments: true
---

### 1. Code
```python
class Solution:
    def deckRevealedIncreasing(self, deck: List[int]) -> List[int]:
        id = deque(range(len(deck)))
        output = [-1] * len(deck)

        # It is a way of simulating the conditions of the problem as they are.
        for e in sorted(deck):
            output[id.popleft()] = e
            if id: # If the list id is present, send the first element to the back.
                id.append(id.popleft())
        return output
```

### 2. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 40 ms(92.20%), Memory usage : 14.3 MB(92.59%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
