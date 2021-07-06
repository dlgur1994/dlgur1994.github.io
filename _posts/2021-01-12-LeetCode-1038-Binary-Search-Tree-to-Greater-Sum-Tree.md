---
layout: post
title: "LeetCode 1038 Binary Search Tree to Greater Sum Tree"
date: 2021-01-12 18:04:28 -0400
categories: SolveProblem
tags: [LeetCode, BST]
comments: true
---

### 1. Code
```python
class Solution:
    def __init__(self):
        self.sum = 0

    def addNode(self, node):
        # Calculate from the deepest node on the right and gradually move to the lower left node.
        if node.right:
            self.addNode(node.right)
        node.val += self.sum
        self.sum = node.val
        if node.left:
            self.addNode(node.left)

    def bstToGst(self, root: TreeNode) -> TreeNode:
        self.addNode
```

### 2. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 16 ms(99.69%), Memory usage : 14 MB(95.11%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
