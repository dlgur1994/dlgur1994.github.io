---
layout: post
title: "LeetCode 0563 Binary Tree Tilt"
date: 2020-12-22 14:16:28 -0400
categories: [Problem Solving]
tags: [LeetCode, Python, DFS, Recursion, Tree]
comments: true
---

## 1. What I learned
### &nbsp;&nbsp;&nbsp;&nbsp;abs()
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;It changes a number to an absolute value.
```python
num = -3
print(abs(num))
# 3
```

### 2. Code
```python
class Solution:
    def findSumAndTilt(self, node):
        if not node:
            return 0, 0
        left_sum, left_tilt = self.findSumAndTilt(node.left)
        right_sum, right_tilt = self.findSumAndTilt(node.right)
        return node.val+left_sum+right_sum, left_tilt+right_tilt+abs(left_sum-right_sum)

    def findTilt(self, root: TreeNode) -> int:
        return self.findSumAndTilt(root)[1]
```

### 3. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 40 ms(99.84%), Memory usage : 15.9 MB(72.50%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
