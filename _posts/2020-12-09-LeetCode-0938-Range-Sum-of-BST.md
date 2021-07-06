---
layout: post
title: "LeetCode 0938 Range Sum of BST.py"
date: 2020-12-09 17:16:28 -0400
categories: SolveProblem
tags: [LeetCode, DFS, Recursion, Tree]
comments: true
---

### 1. Code
```python
class Solution:
    def rangeSumBST(self, root: TreeNode, low: int, high: int) -> int:
        def getNode(node):
            # this is a break condition
            if node == None:
                return

            # when the value is in the range
            elif node.val >= low and node.val <= high:
                vals.append(node.val)
                getNode(node.left)
                getNode(node.right)

            # if the value is less than low, the right node of the node should be checked
            elif node.val < low:
                getNode(node.right)

            # if the value is greater than high, the left node of the node should be checked
            elif node.val > high:
                getNode(node.left)

        vals = []
        getNode(root)
        return sum(vals)
```

### 2. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 196 ms(94.68%), Memory usage : 22.4 MB(18.98%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
