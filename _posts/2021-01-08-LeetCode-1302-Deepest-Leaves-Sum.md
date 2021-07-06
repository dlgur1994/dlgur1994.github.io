---
layout: post
title: "LeetCode 1302 Deepest Leaves Sum"
date: 2021-01-08 12:37:28 -0400
categories: SolveProblem
tags: [LeetCode, DFS, Tree]
comments: true
---

### 1. Code
```python
class Solution:
    def deepestLeavesSum(self, root: TreeNode) -> int:
        def dfs(node, cnt):
            # store the depth and value of a leaf node
            if not node.left and not node.right:
                self.deep.append(cnt)
                self.values.append(node.val)
            if node.left:
                dfs(node.left, cnt+1)
            if node.right:
                dfs(node.right, cnt+1)

        self.deep, self.values = [], []
        sum = 0
        dfs(root, 0)

        # Find the depth of the deepest and add values of the deepest nodes.
        maxdep = max(self.deep)
        for i in range(len(self.deep)):
            if self.deep[i] == maxdep:
                sum += self.values[i]
        return sum
```

### 2. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 92 ms(69.82%), Memory usage : 17.6 MB(82.42%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
