---
layout: post
title: "LeetCode 0113 Path Sum III"
date: 2022-04-12 23:08:28 -0400
categories: [Problem Solving]
tags: [LeetCode, Python, Backtracking, Tree, DFS]
comments: true
---

### 1. Code
```python
class Solution:
    def dfs(self, node, target, visited, ans):
        if node == None:
            return
        
        visited.append(node.val)
        if not node.left and not node.right:
            total = sum(visited)
            if total == target:
                temp = visited[:]
                ans.append(temp)
            visited.pop()
            return

        if node.left:
            self.dfs(node.left, target, visited, ans)
        if node.right:
            self.dfs(node.right, target, visited, ans)

        visited.pop()

    def pathSum(self, root: Optional[TreeNode], targetSum: int) -> List[List[int]]:   
        ans = []
        self.dfs(root, targetSum, [], ans)
        return ans
```

### 2. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 28 ms(100.00%), Memory usage : 15.6 MB(56.45%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
