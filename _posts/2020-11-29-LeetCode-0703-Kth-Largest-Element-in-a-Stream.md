---
layout: post
title: "LeetCode 0703 Kth Largest Element in a Stream.py"
date: 2020-11-29 12:07:28 -0400
categories: ProblemSolving
tags: [LeetCode, Design, Heap]
comments: true
---

## 1. What I learned
### &nbsp;&nbsp;&nbsp;&nbsp;a. heapq.heapify(LIST)
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;It changes a list to heap. It takes nlog(n)
```python
import heapq
nums = [4,2,5,3,1]
heapq.heapify(nums)
```
### &nbsp;&nbsp;&nbsp;&nbsp;b. heapq.nlargest(NUM, HEAP)
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;It returns a list with largest NUM numbers.
```python
import heapq
nums = [4,2,5,3,1]
new_list = heapq.nlargest(3, nums)
print(new_list)
#it will print [5,4,3]
```
### &nbsp;&nbsp;&nbsp;&nbsp;c. float('inf') and float('-inf')
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;It represents an infinite float. 

### 2. Code
```python
class KthLargest:
    def __init__(self, k: int, nums: List[int]):
        #changed nums to the heap with largest k numbers
        heapq.heapify(nums)
        self.heap = heapq.nlargest(k, nums)
        heapq.heapify(self.heap)
        self.k = k

    def add(self, val: int) -> int:
        #if the length of the heap is smaller less than k, push val into the heap
        if len(self.heap)<self.k:
            heapq.heappush(self.heap, val)
            return self.heap[0]
        #if val is bigger than the smallest number of the heap, pop the heap and push val into the heap
        if val > self.heap[0]:
            heapq.heappushpop(self.heap, val)
        return self.heap[0]
```

### 3. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 90 ms(69.07%), Memory usage : 19 MB(5.59%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
