---
layout: post
title: "LeetCode 1351 Count Negative Numbers in a Sorted Matrix.py"
date: 2020-09-17 22:52:28 -0400
categories: SolveProblem
tags: [LeetCode, Array, BinarySearch]
comments: true
---

## 1. What I learned
### &nbsp;&nbsp;&nbsp;&nbsp;a. Way to change STIRNG to TWO DIMENSIONAL LIST
```python
INPUT_STRING = [[4,3,2,-1],[3,2,1,-1],[1,1,-1,-2],[-1,-1,-2,-3]]
input_matrix = INPUT_STRING.rstrip().lstrip('[[').rstrip(']]').split('],[')  
refined_matrix = [[int(e) for e in row.split(',') ]for row in input_matrix]
```

### &nbsp;&nbsp;&nbsp;&nbsp;b. method index(' ')  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;'LIST.index(ELEMENT)' returns the index number of ELEMENT from LIST.  

## 2. How I sloved
&nbsp;&nbsp;&nbsp;&nbsp;I declared 'count' to count the negative numbers and defined it 0. I used 'for loop' twice. I checked when the negative number began for all rows of grids. When the negative number started, I stopped that loop and added 'len(row)-row.index(NEGATIVE_NUMBER)' to 'count'.   

## 3. Code
```python
class Solution:
    def countNegatives(self, grid: List[List[int]]) -> int:
        count = 0

        for row in grid:
            for e in row:
                if e<0:
                    count += len(row)-row.index(e)
                    break

        return count
```

## 4. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 136 ms(43.02%), Memory usage : 14.7 MB(59.77%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.

[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
