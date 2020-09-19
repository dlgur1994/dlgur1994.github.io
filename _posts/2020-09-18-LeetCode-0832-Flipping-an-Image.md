---
title: "LeetCode 0832 Flipping an Image.py"
categories: LeetCode solution
date: 2020-09-18 17:03:28 -0400
---

## 1. What I learned
### &nbsp;&nbsp;&nbsp;&nbsp;a. Swap
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;If you want to exchange two numbers, write as follows.
```python
a,b = b,a
```

### &nbsp;&nbsp;&nbsp;&nbsp;b. method reverse()  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;'LIST.reverse()' returns a list of elements in reverse order.  

## 2. How I sloved
&nbsp;&nbsp;&nbsp;&nbsp;I approached each row and used reverse() method. It reversed the order of all elements in the row. And if each element was 0, it was changed to 1, otherwise to 0.   

## 3. Code
```python
class Solution:
    def flipAndInvertImage(self, A: List[List[int]]) -> List[List[int]]:
        for row in A:
            row.reverse()
            for i in range(0,len(A[0])):
                row[i] ^= 1
        return A
```

```python
class Solution:
   def flipAndInvertImage(self, A: List[List[int]]) -> List[List[int]]:
       for i in range(0, len(A)):
           for j in range(0,int(len(A[0])/2)):
               A[i][j], A[i][len(A[0])-1-j] = A[i][len(A[0])-1-j], A[i][j]
       for i in range(0, len(A)):
           for j in range(0,len(A[0])):
               if A[i][j] == 0:
                   A[i][j] = 1
               else:
                   A[i][j] = 032
       return A
```
## 4. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 52 ms(73.65%), Memory usage : 13.6 MB(96.41%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.

[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
