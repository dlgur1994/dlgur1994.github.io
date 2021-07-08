---
layout: post
title: "LeetCode 0559 Maximum Depth of N-ary Tree.py"
date: 2020-12-17 16:58:28 -0400
categories: ProblemSolving
tags: [LeetCode, BFS, DFS, Tree]
comments: true
---

### 1. Code
```python
class Solution:
    def maxDepth(self, root: 'Node') -> int:
        depth = 0
        # when root exists
        if root:
            # depth of the root is 1
            depth += 1
            queue = deque([(root,depth)])
            while queue:
                node, dep = queue.popleft()
                for e in node.children:
                    # append node's children and the depth of them to the queue
                    queue.append((e, dep+1))
            # update depth to the deepest child
            depth = dep    
        return depth
```

### 2. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 36 ms(97.88%), Memory usage : 16.3 MB(20.12%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
