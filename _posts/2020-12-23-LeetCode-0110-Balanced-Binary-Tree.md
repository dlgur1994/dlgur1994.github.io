---
layout: post
title: "LeetCode 0110 Balanced Binary Tree"
date: 2020-12-23 17:47:28 -0400
categories: [Problem Solving]
tags: [LeetCode, Python, DFS, Recursion, Tree]
comments: true
---

## 1. What I learned
### &nbsp;&nbsp;&nbsp;&nbsp;try, except, else, raise
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;This is how to handle exceptions. 'try' is the action you want to try, 'except' is the result of an exception, and 'else' is the result of a normal situation. An exception can occur through 'raise Exception()'.
```python
try:
    ACTION
except:
    return ERROR RESULT
else:
    return RIGHT RESULT
```

### 2. Code
```python
class Solution:
    def dfs(self, node):
        if not node:
            return 0
        left = self.dfs(node.left) # Depth on the left
        right = self.dfs(node.right) # Depth on the right
        if abs(left-right) > 1: # If the difference between the depth on the left and the depth on the right is greater than 1, then the condition is not high-balance binary tree.
            raise Exception()
        return max(left, right) + 1

    def isBalanced(self, root: TreeNode) -> bool:
        try:
            self.dfs(root)
        except:
            return False
        else:
            return True
```

### 3. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 44 ms(92.17%), Memory usage : 18.4 MB(51.10%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
