---
layout: post
title: "LeetCode 0513 Find Bottom Left Tree Value.py"
date: 2020-10-15 16:52:28 -0400
categories: [Problem Solving]
tags: [LeetCode, Python, BFS, DFS]
comments: true
---

### 1. What I learned
#### &nbsp;&nbsp;&nbsp;&nbsp;a. deque
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;This is the same as the queue, but popleft() can be used in the deque. The time it takes to popleft() is much shorter than pop().
#### &nbsp;&nbsp;&nbsp;&nbsp;b. extend vs append
```python
list1 = ['A','B']
list2 = ['C']
word = 'word'
list1.append(list2) --> list1 = ['A','B',['C']]
list1.extend(list2) --> list1 = ['A','B','C']
list1.append(word) --> list1 = ['A','B','word']
list1.extend(word) --> list1 = ['A','B','w','o','r','d']
#it should be run one by one, not all at once.
```

#### 2. How I sloved
&nbsp;&nbsp;&nbsp;&nbsp;I needed to find the leftmost value in the last row of the tree. So I used BFS and stored values at the same height as the same element. Then the first value of the last element was returned.

### 3. Code
```python
class Solution:
    def findBottomLeftValue(self, root: TreeNode) -> int:
        if root == None:
            return
        visited = []
        queue = deque([(root,0)])
        while queue:
            node,height = queue.popleft()
            if len(visited)<=height:
                visited.append([node.val])
            else:
                visited[height].append(node.val)
            if node.left:
                queue.append((node.left,height+1))
            if node.right:
                queue.append((node.right,height+1))
        return visited[-1][0]
```

### 4. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 40 ms(88.51%), Memory usage : 16.2 MB(23.22%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
