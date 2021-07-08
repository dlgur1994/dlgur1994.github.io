---
layout: post
title: "LeetCode 0897 Increasing Order Search Tree.py"
date: 2020-09-30 22:14:28 -0400
categories: ProblemSolving
tags: [LeetCode, DFS, Tree]
comments: true
---

## 1. What I learned
### &nbsp;&nbsp;&nbsp;&nbsp;a. A function in another function
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;We can define a different function within a function.
```python
def fuctionA(self,ex):
  def functionB(self,pp):
#There's no error
```

### &nbsp;&nbsp;&nbsp;&nbsp;b. LIST.pop(0)
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;To remove the first element in a list, write as follows.
```python
LIST = [1,2,3]
LIST.pop(0)
print LIST
#It will print '2,3'
```

## 2. How I sloved
&nbsp;&nbsp;&nbsp;&nbsp;I used DFS to arrange the elements in ascending order. Then I made a BST using the sorted list. That BST stretched only to the right.

## 3. Code
```python
class Solution:
    def increasingBST(self, root: TreeNode) -> TreeNode:
        def dfs(root):
            if root is None:
                pass
            else:
                dfs(root.left)
                elements.append(root.data)
                dfs(root.right)

        def createBST(elist):
            new_root = TreeNode(elist[0])
            cur_root = new_root
            elist.pop(0)
            for e in elist:
                cur_root.right = TreeNode(e)
                cur_root = cur_root.right
            return new_root

        elements = []
        dfs(root)
        return createBST(elements)
```

## 4. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 24 ms(96.34%), Memory usage : 14.2 MB(5.14%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.

[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
