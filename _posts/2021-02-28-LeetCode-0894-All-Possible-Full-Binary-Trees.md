---
layout: post
title: "LeetCode 0894 All Possible Full Binary Trees"
date: 2021-02-28 19:41:28 -0400
categories: [Problem Solving]
tags: [LeetCode, Python, Recursion, Tree]
comments: true
---

### 1. Code
```python
class Solution:
    def allPossibleFBT(self, N: int) -> List[TreeNode]:
        if N == 1: # If N is 1, only one case is possible
            return [TreeNode(0)]
        elif N%2 == 0: # When N is a multiple of 2, the number of children cannot be zero or two
            return []
        else:
            ans = []
            l = N-2 # When the root and right nodes were subtracted from the tree of three nodes
            r = 1 # the right node
            while l > 0:
                left = self.allPossibleFBT(l) # Save every possible case on the left
                right = self.allPossibleFBT(r) # Save every possible case on the right
                for i in range(len(left)):
                    for j in range(len(right)):
                        root = TreeNode(0)
                        root.left = left[i]
                        root.right = right[j]
                        ans.append(root)
                l -= 2
                r += 2
            return ans
```

### 2. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 220 ms(53.63%), Memory usage : 23 MB(43.64%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
