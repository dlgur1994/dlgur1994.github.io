---
layout: post
title: "LeetCode 1379 Find a Corresponding Node of a Binary Tree in a Clone of That Tree"
date: 2021-01-11 23:04:28 -0400
categories: ProblemSolving
tags: [LeetCode, BFS, DFS, Recursion, Tree]
comments: true
---

### 1. Code
```python
class Solution:
    def getTargetCopy(self, original: TreeNode, cloned: TreeNode, target: TreeNode) -> TreeNode:
        q = deque([(original, cloned)]) # Store the original and cloned nodes together.
        while q:
            origin, clon = q.popleft()
            if origin is target: # When the target node is found, returns the cloned node.
                return clon
            if origin.left:
                q.append((origin.left, clon.left))
            if origin.right:
                q.append((origin.right, clon.right))
```

### 2. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 596 ms(96.15%), Memory usage : 24 MB(82.41%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
