---
layout: post
title: "LeetCode 0104 Maximum Depth of Binary Tree.py"
date: 2020-10-04 14:18:28 -0400
categories: ProblemSolving
tags: [LeetCode, DFS, Tree]
comments: true
---

## 1. What I learned
### &nbsp;&nbsp;&nbsp;&nbsp;Making a tree without any rule
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;To insert nodes into the tree, write as follows.
```python
def insertNode(self,node,left_node,right_node):
        if self.root is None:
            self.root = node
        if left_node is not None and left_node.val != 'null':
            node.left = left_node
        if right_node is not None and right_node.val != 'null':
            node.right = right_node
if len(input) == 1:
    input.append(None)
    input.append(None)
if len(input) == 2:
    input.append(None)
for i in range(len(input)//2):
     binary_tree.insertNode(input[i],input[2*i+1],input[2*i+2])
```

## 2. How I sloved
&nbsp;&nbsp;&nbsp;&nbsp;I used recursive to get the maximum depth of the tree. I compared the depth of the left side with the depth of the right side and updated the larger one as depth of the tree.

## 3. Code
```python
class Solution:
    def maxDepth(self, root: TreeNode) -> int:
        def getDepth(node):
            if node is None:
                return 0
            left_depth = getDepth(node.left)
            right_depth = getDepth(node.right)
            return left_depth+1 if left_depth>right_depth else right_depth+1

        return getDepth(root)
```

## 4. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 24 ms(99.99%), Memory usage : 16.2 MB(5.06%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.

[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
