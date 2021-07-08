---
layout: post
title: "LeetCode 1669 Merge In Between Linked Lists"
date: 2021-01-19 00:05:28 -0400
categories: [Problem Solving]
tags: [LeetCode, Python, LinkedList]
comments: true
---

### 1. Code
```python
class Solution:
    def mergeInBetween(self, list1: ListNode, a: int, b: int, list2: ListNode) -> ListNode:
        cur = list1
        for i in range(b): # Point to ptr1 and ptr2 at each front of a and b.
            if i == a-1:
                ptr1 = cur
            cur = cur.next
        ptr2 = cur.next
        ptr1.next = list2 # Connect the following from ptr1 to list2.
        while ptr1.next: # Go to the last node of the connected list2.
            ptr1 = ptr1.next
        ptr1.next = ptr2 # Connect the rest of list1 to its most end node.
        return list1
```

### 2. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 436 ms(88.35%), Memory usage : 20.2 MB(47.43%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
