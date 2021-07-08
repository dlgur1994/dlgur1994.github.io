---
layout: post
title: "LeetCode 0083 Remove Duplicates from Sorted List.py"
date: 2020-11-03 17:30:28 -0400
categories: [Problem Solving]
tags: [LeetCode, Python, LinkedList]
comments: true
---

### 1. How I sloved
&nbsp;&nbsp;&nbsp;&nbsp;I had to make a linked list without duplicate values. So if the value of 'cur' was equal to the value of 'cur.next', 'cur' was connected to 'cur.next.next'. Otherwise, 'cur' just moved to 'next'. Then head was returned. 

### 2. Code
```python
class Solution:
    def deleteDuplicates(self, head: ListNode) -> ListNode:
        if head == None:
            return
        cur = head
        while cur:
            if cur.val == cur.next.val:
                cur.next = cur.next.next
            else:
                cur = cur.next
        return head
```

### 3. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 36 ms(93.93%), Memory usage : 14 MB(100.00%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
