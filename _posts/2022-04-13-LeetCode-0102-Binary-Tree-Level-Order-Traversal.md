---
layout: post
title: "LeetCode 0102 Binary Tree Level Order Traversal"
date: 2022-04-13 23:49:28 -0400
categories: [Problem Solving]
tags: [LeetCode, Python, Tree, BFS]
comments: true
---

### 1. Code
```python
class Solution:
    def levelOrder(self, root: Optional[TreeNode]) -> List[List[int]]:
        if root == None:
            return []
        
        ans = [[root.val]]
        nodes = [root]
        cnt = 0

        parents = [[nodes[cnt]]]
        while True:
            children = []
            vals = []
            if len(parents) == cnt:
                break
            
            for parent in parents[cnt]:
                if parent.left:
                    children.append(parent.left)
                    vals.append(parent.left.val)
                if parent.right:
                    children.append(parent.right)
                    vals.append(parent.right.val)

            if children == []:
                return ans

            parents.append(children)
            ans.append(vals)
            cnt += 1
```

### 2. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 31 ms(96.47%), Memory usage : 14.1 MB(98.87%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
