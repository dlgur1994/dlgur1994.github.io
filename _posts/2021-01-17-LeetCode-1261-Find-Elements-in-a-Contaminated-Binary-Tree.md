---
layout: post
title: "LeetCode 1261 Find Elements in a Contaminated Binary Tree"
date: 2021-01-17 16:54:28 -0400
categories: [Problem Solving]
tags: [LeetCode, Python, HashTable, Tree]
comments: true
---

### 1. Code
```python
class FindElements:
    def __init__(self, root: TreeNode):
        self.values = {'0' : 0} # The dictionary to store the values of the modified tree.
        root.val = 0
        self.editNode(root) # Modify the values of the tree.

    def find(self, target: int) -> bool:
        if str(target) in self.values: # Check whether the dictionary has a value or not.
            return True
        else:
            return False

    def editNode(self, node):
        if node.left: # If the node has left, modify the value of the left node and save it in the dictionary.
            node.left.val = 2*node.val + 1
            self.values[str(node.left.val)] = 0
            self.editNode(node.left)
        if node.right: # If the node has right, modify the value of the right node and save it in the dictionary.
            node.right.val = 2*node.val + 2
            self.values[str(node.right.val)] = 0
            self.editNode(node.right)
```

### 2. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 72 ms(100.00%), Memory usage : 19.7 MB(30.73%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
