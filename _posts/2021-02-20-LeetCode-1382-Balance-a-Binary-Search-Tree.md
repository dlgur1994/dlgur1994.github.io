---
layout: post
title: "LeetCode 1382 Balance a Binary Search Tree"
date: 2021-02-20 23:34:28 -0400
categories: SolveProblem
tags: [LeetCode, Python, BinarySearchTree]
comments: true
---

### 1. Code
```python
class Solution:
    def __init__(self):
        self.nodes = []

    def getNodes(self, node): # create a list of nodes in ascending order of node values.
        if node.left:
            self.getNodes(node.left)
        self.nodes.append(node)
        if node.right:
            self.getNodes(node.right)

    def makeTree(self, start, end): # create a binary search tree
        if start >= end:
            return None
        mid = (start+end)//2
        mid_node = self.nodes[mid]
        mid_node.left = self.makeTree(start, mid)
        mid_node.right = self.makeTree(mid+1, end)
        return mid_node

    def balanceBST(self, root: TreeNode) -> TreeNode:
        self.getNodes(root)
        return self.makeTree(0, len(self.nodes))
```

### 2. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 304 ms(94.09%), Memory usage : 19 MB(80.39%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
