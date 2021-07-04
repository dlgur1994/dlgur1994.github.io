---
title: "LeetCode 1290 Convert Binary Number in a Linked List to Integer.py"
date: 2020-04-03 16:32:28 -0400
categories: LeetCode LinkedList BitManipulation
---

## 1. What I learned
### &nbsp;&nbsp;&nbsp;&nbsp;a. class LinkedList  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;'self.head' in 'def __init__(self)' of class 'LinkedList' refers to the head node.  

### &nbsp;&nbsp;&nbsp;&nbsp;b. int(num1,num2) method
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;It converts 'num1' in given based('num2').  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ex) int(101,2) --> 5

## 2. How I sloved
&nbsp;&nbsp;&nbsp;&nbsp;I sent a linked list to Class 'solution'. I add the node's value to 'num' and moved to the next node. I kept doing this for all the nodes, and I returned the result.  

## 3. Code
```python
class Solution:
    def getDecimalValue(self, head: ListNode) -> int:
        num = 0
        while head:
            num = 2*num+head.val
            head = head.next
        return num
```

```python
class Solution:
    def getDecimalValue(self, head: ListNode) -> int:
        num = ''
        while head:
            num += str(head.val)
            head = head.next
        return int(num,2)
```

## 4. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 20 ms(97.70%), Memory usage : 13.9 MB(100.00%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.

[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
