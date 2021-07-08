---
layout: post
title: "LeetCode 0118 Pascal's Triangle.py"
date: 2020-10-22 16:18:28 -0400
categories: ProblemSolving
tags: [LeetCode, Array]
comments: true
---

#### 1. How I sloved
&nbsp;&nbsp;&nbsp;&nbsp;I made all elements '1' in each line. The elements except the first and last from the third row are the sum of the elements in the previous row. So I added the former elements, and it became an element of a new row, and added the new row to the list. When the number of rows was equal to the input, I returned the list.

### 2. Code
```python
class Solution:
    def generate(self, numRows: int) -> List[List[int]]:
        triangle = []
        for i in range(1,numRows+1):
            row = [1 for _ in range(i)]
            if i>2:
                for j in range(1,i-1):
                    row[j]=triangle[i-2][j-1]+triangle[i-2][j]
            triangle.append(row)
        return triangle
```

### 3. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 20 ms(98.68%), Memory usage : 14.1 MB(99.98%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
