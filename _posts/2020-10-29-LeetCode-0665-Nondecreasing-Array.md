---
layout: post
title: "LeetCode 0665 Non-decreasing Array.py"
date: 2020-10-29 17:29:28 -0400
categories: ProblemSolving
tags: [LeetCode, Array]
comments: true
---

### 1. What I learned
#### &nbsp;&nbsp;&nbsp;&nbsp;a. Shallow Copy vs Deep Copy
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;A shallow copy creates a new object which stores the reference of the original elements. And a deep copy creates a new object and recursively adds the copies of nested objects present in the original elements.
```python
num = [1,2,3,4,5]
temp1 = num[:]
temp1[0] = 6
print(num)
#It will print [1,2,3,4,5]

temp2 = num
temp2[0] = 6
print(num)
#It will print [6,2,3,4,5]
```
#### &nbsp;&nbsp;&nbsp;&nbsp;b. del LIST[i]
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;It erases the i-th element from the list.
```python
sample_list = [1,2,3,4,5]
del sample_list[2]
print(sample_list)
#I will print [1,2,4,5]
```

### 2. How I sloved
&nbsp;&nbsp;&nbsp;&nbsp;The list had to be sorted in order by changing up to one element. When there were less than three elements, the conditions could always be met. I checked all the elements from the beginning and added one to the cnt if the element was greater than the next element and checked the previous and next elements. If the previous element was greater than the next element, I changed the next element to the previous one. This was for when the next element was abnormal. If there were more than one odd number, false was returned, otherwise true.

### 3. Code
```python
class Solution:
    def checkPossibility(self, nums: List[int]) -> bool:
        cnt = 0
        if len(nums)<3:
            return True
        for i in range(len(nums)-1):
            if nums[i]>nums[i+1]:
                if cnt>0:
                    return False
                cnt += 1
                if i>0 and nums[i-1]>nums[i+1]:
                    nums[i+1] = nums[i]
        return True
```

### 4. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 168 ms(98.67%), Memory usage : 15.3 MB(100.00%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
