---
layout: post
title: "LeetCode 0206 Reverse Linked List.py"
date: 2020-11-05 17:42:28 -0400
categories: [Problem Solving]
tags: [LeetCode, Python, LinkedList]
comments: true
---

### 1. How I sloved
&nbsp;&nbsp;&nbsp;&nbsp;I had to reverse the order of the linked list. I used 'cur' and 'pre' to manipulate the linked list. 'cur' pointed to the next node of 'head' and 'pre' pointed to the previous node of 'head'. I repeated the process. First, 'cur' moved to the next node of 'head'. Second, the next node of 'head' was changed to 'pre'. Third, 'pre' moved to 'head'. Finally, 'head' moved to 'cur'. Before 'pre' moved to 'head', 'head' was returned when 'cur' pointed to 'None'.

### 2. Code
```python
class Solution:
    def reverseList(self, head: ListNode) -> ListNode:
        cur = None
        pre = None
        while head:
            cur = head.next
            head.next = pre
            if not cur:
                return head
            pre = head
            head = cur
```

### 3. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 32 ms(86.69%), Memory usage : 15.3 MB(8.03%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
