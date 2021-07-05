---
title: "LeetCode 1305 All Elements in Two Binary Search Trees"
categories: LeetCode Python Sort Tree
date: 2021-02-16 14:48:28 -0400
comments: true
---

### 1. Code
```python
class Solution:
    def __init__(self):
        self.buf = [] # it is a buffer to store values from trees

    def getVals(self, node): # store values in ascending order
        if node.left:
            self.getVals(node.left)
        self.buf.append(node.val)
        if node.right:
            self.getVals(node.right)

    def getAllElements(self, root1: TreeNode, root2: TreeNode) -> List[int]:
        if root1: # get every value in the first tree
            self.getVals(root1)
        if root2: # get every value in the second tree
            self.getVals(root2)
        return sorted(self.buf)
```

### 2. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 288 ms(100.00%), Memory usage : 21.6 MB(60.89%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
