---
title: "LeetCode 0107 Binary Tree Level Order Traversal II.py"
categories: LeetCode solution
date: 2020-10-14 15:48:28 -0400
---

## 1. What I learned
### &nbsp;&nbsp;&nbsp;&nbsp;Insert two different elements into a list
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;To reverse the order of elements in a list, write as follows.
```python
LIST = [1,2,3,4,5]
print(list(reversed(LIST)))
#I will print [5,4,3,2,1]
```

## 2. How I sloved
&nbsp;&nbsp;&nbsp;&nbsp;Values of the same height should be in the same element of the list. I used the BFS and added the height of the value when I put the value in the queue. When pop-up a queue, I checked the height first. If the value is the first at that height, I put it in "visited" list. Otherwise, this value was added to the same height element in the list. 

## 3. Code
```python
class Solution:
    def levelOrderBottom(self, root: TreeNode) -> List[List[int]]:
        if root == None:
            return []
        visited = []
        queue = deque([(root,0)])
        while queue:
            node,height = queue.popleft()
            if height>=len(visited):
                visited.append([node.val])
            else:
                visited[height].append(node.val)
            if node.left:
                queue.append((node.left,height+1))
            if node.right:
                queue.append((node.right,height+1))
        return list(reversed(visited))
```

## 4. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 32 ms(83.93%), Memory usage : 14.2 MB(16.09%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.

[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
