---
title: "LeetCode 1299 Replace Elements with Greatest Element on Right Side.py"
date: 2020-09-22 17:09:28 -0400
categories: LeetCode Array
---
## 1. How I sloved
&nbsp;&nbsp;&nbsp;&nbsp;Because I had to find the biggest number after the designated element, I found the biggest number from the back. Then it was much easier because all I had to do was just compare the designated element with the very next. I started the comparing from 'len(arr)-2' and returned the second to last element of 'arr' and attached '-1' to the end.  

## 2. Code
```python
class Solution:
    def replaceElements(self, arr: List[int]) -> List[int]:
        for i in range(len(arr)-2,-1,-1):
            arr[i] = max(arr[i],arr[i+1])
        return arr[1:] + [-1]
```
```python
# my first version, but took too much time
# class Solution:
#     def replaceElements(self, arr: List[int]) -> List[int]:
        # output = []
        #
        # for i in range(0,len(arr)-1):
        #     arr[i] = 0
        #     output.append(max(arr))
        # output.append(-1)
        #
        # return output
```
## 3. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 128 ms(82.97%), Memory usage : 14.9 MB(54.37%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.

[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
