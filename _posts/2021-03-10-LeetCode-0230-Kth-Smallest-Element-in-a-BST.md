---
layout: post
title: "LeetCode 0230 Kth Smallest Element in a BST" 
date: 2021-03-10 00:21:28 -0400
categories: SolveProblem
tags: [LeetCode, Python, BinarySearch, Tree]
comments: true
---

### 1. Code
```python
class Solution:
    def __init__(self):
        self.ans = 0
        self.cnt = 0
        self.flag = True

    def inOrder(self, node, k):
        if self.flag: # it's an inorder traversal
            if node.left:
                self.inOrder(node.left, k)
            self.cnt += 1
            if self.cnt == k: # it's the stopping point
                self.ans = node.val
                self.flag = False
            if node.right:
                self.inOrder(node.right, k)
        else:
            return self.ans

    def kthSmallest(self, root: TreeNode, k: int) -> int:
        self.inOrder(root, k)
        return self.ans
```

### 2. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 44 ms(92.44%), Memory usage : 17.8 MB(95.60%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
