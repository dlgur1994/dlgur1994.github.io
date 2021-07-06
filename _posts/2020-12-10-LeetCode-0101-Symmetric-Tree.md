---
layout: post
title: "LeetCode 0101 Symmetric Tree.py"
date: 2020-12-10 17:01:28 -0400
categories: SolveProblem
tags: [LeetCode, BFS, DFS, Tree]
comments: true
---

### 1. Code
```python
class Solution:
    def isSymmetric(self, root: TreeNode) -> bool:
        def checkSymmetric(left, right):
            # it's a leaf, so it's symmetrical
            if not left and not right:
                return True

            # having only one left or right means asymmetric
            elif not left or not right:
                return False

            # repeat if left and right values are equal
            elif left.val == right.val:
                return checkSymmetric(left.left, right.right) and checkSymmetric(left.right, right.left)

            else:
                return False

        # if root empty, just return False
        if not root:
            return False
        return checkSymmetric(root.left, root.right)
```

### 2. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 24 ms(98.60%), Memory usage : 14.3 MB(68.25%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
