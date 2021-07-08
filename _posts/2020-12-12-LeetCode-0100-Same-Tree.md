---
layout: post
title: "LeetCode 0100 Same Tree11 Minimum Depth of Binary Tree.py"
date: 2020-12-12 16:58:28 -0400
categories: [Problem Solving]
tags: [LeetCode, Python, DFS, Tree]
comments: true
---

### 1. Code
```python
class Solution:
    def isSameTree(self, p: TreeNode, q: TreeNode) -> bool:
        if not p and not q:
            return True

        # if only one node has a child or children
        if not p or not q:
            return False
        if p.val != q.val:
            return False

        # keep compare the left and right side of each node
        return self.isSameTree(p.left, q.left) and self.isSameTree(p.right, q.right)
```

### 2. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 24 ms(94.54%), Memory usage : 14.1 MB(50.13%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
