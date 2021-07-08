---
layout: post
title: "LeetCode 0111 Minimum Depth of Binary Tree.py"
date: 2020-12-11 11:23:28 -0400
categories: [Problem Solving]
tags: [LeetCode, Python, BFS, DFS, Tree]
comments: true
---

### 1. Code
```python
class Solution:
    def minDepth(self, root: TreeNode) -> int:
        # when root is null
        if not root:
            return 0
        depth = 1
        queue = deque([(root, depth)])
        while queue:
            node, dep = queue.popleft()

            # when a node is a leaf node
            if not node.left and not node.right:
                return dep
            if node.left:
                queue.append((node.left, dep+1))
            if node.right:
                queue.append((node.right, dep+1))
```

### 2. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 452 ms(89.43%), Memory usage : 49.1 MB(86.03%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
