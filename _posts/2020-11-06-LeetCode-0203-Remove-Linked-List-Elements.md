---
layout: post
title: "LeetCode 0203 Remove Linked List Elements.py"
date: 2020-11-06 22:12:28 -0400
categories: ProblemSolving
tags: [LeetCode, LinkedList]
comments: true
---

### 1. How I sloved
&nbsp;&nbsp;&nbsp;&nbsp;It was necessary to clear the same value as 'value' from the linked list. I used 'cur' and 'pre' as pointers to do it. I made a 'dummy' node and made 'pre' point it out. If the value differed from the value while 'cur' navigated through the linked list, 'pre.next' was set to point to that node. And I kept checking to see if 'cur' was pointing to the last node. If it pointed to the last one, 'dummy.next' was returned as a new head node.

### 2. Code
```python
class Solution:
    def removeElements(self, head: ListNode, val: int) -> ListNode:
        dummy = ListNode('dummy')
        cur = head
        pre = dummy
        while cur:
            if cur.val != val:
                pre.next = cur
                pre = pre.next
            if cur.next == None:
                pre.next = None
                return dummy.next
            cur = cur.next
```

### 3. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 64 ms(89.52%), Memory usage : 16.8 MB(5.54%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
