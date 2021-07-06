---
layout: post
title: "LeetCode 1046 Last Stone Weight.py"
date: 2020-11-27 13:03:28 -0400
categories: SolveProblem
tags: [LeetCode, Greedy, Heap]
comments: true
---

## 1. What I learned
### &nbsp;&nbsp;&nbsp;&nbsp;heapq
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;There is "heapq" that supports heap structure in Python. The basic type of "heapq" is the minimum heap.
```python
import heapq

heap = []

heapq.heappush(heap,2)
heapq.heappush(heap,1)
heapq.heappush(heap,5)
heapq.heappush(heap,3)
heapq.heappush(heap,4)
print(heapq.heappop(heap))
#it will print '1'
```

### 2. How I sloved
&nbsp;&nbsp;&nbsp;&nbsp;While comparing the two biggest elements among the stones, the list had to be reduced by deleting elements. I used "heapq." I changed "heapq" to the maximum heap because "heapq" has a minimal heap structure. When the two biggest elements were picked up, if the two elements were different, the difference between the two elements was pushed into the heap. After the while loop, I returned the only element of the heap if the length of the heap is 1. Otherwise, I returend 0.

### 3. Code
```python
class Solution:
    def lastStoneWeight(self, stones: List[int]) -> int:
        heap = []
        for stone in stones:
            heapq.heappush(heap,(-stone, stone))
        while len(heap)>1:
            temp = []
            for _ in range(2):
                temp.append(heapq.heappop(heap)[1])
            if temp[0] != temp[1]:
                heapq.heappush(heap,(-(temp[0]-temp[1]), temp[0]-temp[1]))
        return heap[0][1] if len(heap)==1 else 0
```

### 4. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 28 ms(80.92%), Memory usage : 14.2 MB(37.74%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
