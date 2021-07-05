---
title: "LeetCode 1721 Swapping Nodes in a Linked List"
categories: LeetCode Python LinkedList
date: 2021-03-03 15:19:28 -0400
comments: true
---

### 1. Code
```python
class Solution:
    def swapNodes(self, head: ListNode, k: int) -> ListNode:
        nodes = []
        cur = head
        while cur != None: # store all nodes in the list
            nodes.append(cur)
            cur = cur.next
        nodes[k-1].val, nodes[len(nodes)-k].val = nodes[len(nodes)-k].val, nodes[k-1].val # swap the value of the corresponding location nodes
        return head
```

### 2. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 1032 ms(91.39%), Memory usage : 48.9 MB(31.79%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
