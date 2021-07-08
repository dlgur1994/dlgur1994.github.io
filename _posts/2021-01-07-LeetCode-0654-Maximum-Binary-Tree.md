---
layout: post
title: "LeetCode 0654 Maximum Binary Tree"
date: 2021-01-07 13:16:28 -0400
categories: ProblemSolving
tags: [LeetCode, Tree]
comments: true
---

## 1. What I learned
### &nbsp;&nbsp;&nbsp;&nbsp;To check if a list is empty
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; The empty list is not the same as False, but "if not LIST" is used to check whether the list is empty.  
```python
l = []
print(l == True)
print(l == False)
if l:
  print("1")
if not l:
  print("2")
# False
# False
# 2
```

### 2. Code
```python
class Solution:
    def makeNodes(self, l):
        if not l:
            return None
        else:
            node = TreeNode(max(l)) # find the largest number and make it a treenode
            id = l.index(max(l)) # find the index of the biggest number
            node.left = self.makeNodes(l[:id]) # the node's left
            node.right = self.makeNodes(l[id+1:]) # the node's right
            return node

    def constructMaximumBinaryTree(self, nums: List[int]) -> TreeNode:
        root = self.makeNodes(nums)
        return root
```

### 3. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 204 ms(66.45%), Memory usage : 14.7 MB(92.94%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
