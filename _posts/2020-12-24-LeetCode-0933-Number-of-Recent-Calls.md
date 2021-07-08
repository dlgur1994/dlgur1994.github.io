---
layout: post
title: "LeetCode 0933 Number of Recent Calls"
date: 2020-12-24 10:46:28 -0400
categories: [Problem Solving]
tags: [LeetCode, Python, Queue]
comments: true
---

### 1. Code
```python
class RecentCounter:
    def __init__(self):
        self.queue = deque()

    def ping(self, t: int) -> int:
        self.queue.append(t) # This prevents the queue from being empty
        while self.queue[0] < t-3000:
            self.queue.popleft()
        return len(self.queue)
```

### 2. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 264 ms(99.10%), Memory usage : 19 MB(48.38%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
