---
layout: post
title: "LeetCode 0021 Merge Two Sorted Lists.py"
date: 2020-11-03 16:18:28 -0400
categories: ProblemSolving
tags: [LeetCode, LinkedList]
comments: true
---

### 1. How I sloved
&nbsp;&nbsp;&nbsp;&nbsp;I had to combine two linked lists into one linked list. So I kept comparing the values of the two linked lists and the smaller one was linked to the combined linked lists. If one of the linked lists became none, the other was all linked to the linked list. Then the head of the combined linked list was returned.

### 2. Code
```python
class Solution:
    def mergeTwoLists(self, l1: ListNode, l2: ListNode) -> ListNode:
        if l1 == None: return l2
        if l2 == None: return l1
        if l1.val < l2.val:
            head = l1
            l1 = l1.next
        else:
            head = l2
            l2 = l2.next
        cur = head
        while l1 and l2:
            if l1.val > l2.val:
                cur.next = l2
                l2 = l2.next
            else:
                cur.next = l1
                l1 = l1.next
            cur = cur.next
        if l1 == None: cur.next = l2
        if l2 == None: cur.next = l1
        return head
```

### 3. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 28 ms(97.90%), Memory usage : 14.1 MB(100.00%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
