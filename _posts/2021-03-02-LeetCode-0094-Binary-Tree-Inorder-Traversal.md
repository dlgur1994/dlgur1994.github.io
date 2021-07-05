---
title: "LeetCode 0094 Binary Tree Inorder Traversal"
categories: LeetCode Python HashTable Tree Stack Tree
date: 2021-03-02 15:18:28 -0400
comments: true
---

### 1. Code
```python
class Solution:
    def __init__(self):
        self.ans = []

    def inorderTraversal(self, root: TreeNode) -> List[int]:
        if not root:
            return
        if root.left:
            self.inorderTraversal(root.left)
        self.ans.append(root.val)
        if root.right:
            self.inorderTraversal(root.right)
        return self.ans
```

### 2. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 24 ms(96.24%), Memory usage : 14.2 MB(49.64%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
