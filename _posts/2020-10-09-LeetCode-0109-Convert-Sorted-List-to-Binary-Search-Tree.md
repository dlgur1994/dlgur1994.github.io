---
layout: post
title: "LeetCode 0109 Convert Sorted List to Binary Search Tree.py"
date: 2020-10-09 10:47:28 -0400
categories: ProblemSolving
tags: [LeetCode, DFS, LinkedList]
comments: true
---

## 1. What I learned
### &nbsp;&nbsp;&nbsp;&nbsp;Can't use only 'return' in Ternary Operator
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;In the Ternary Operator, only the 'return' statement cannot be used.
```python
print('H') if A else return
#There's an error
```

## 2. How I sloved
&nbsp;&nbsp;&nbsp;&nbsp;I used Tree and DFS to solve this problem. The input values came in order. So I went on to get the middle value of the values and split the list in two and repeated this process to create a tree. When making the tree, I used the binary tree concept to send a small value to the left and a large value to the right.

## 3. Code
```python
class Solution:
    def sortedListToBST(self, head: ListNode) -> TreeNode:
        def getValues(head):
            temp = []
            while head:
                temp.append(head.val)
                head = head.next
            return temp
        def makeTree(values,low,high):
            if low>high:
                return
            mid = (low+high)//2
            new_node = TreeNode(values[mid])
            new_node.left = makeTree(values,low,mid-1)
            new_node.right = makeTree(values,mid+1,high)
            return new_node
        value_list = getValues(head)
        root = makeTree(value_list,0,len(value_list)-1)
        return root
```

## 4. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 128 ms(83.86%), Memory usage : 20.1 MB(58.06%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.

[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
