---
title: "LeetCode 0013 Roman to Integer.py"
categories: LeetCode Array TwoPointers
date: 2020-11-10 17:30:28 -0400
comments: true
---

### 1. How I sloved
&nbsp;&nbsp;&nbsp;&nbsp;Roman characters had to be changed to numbers. I made two dictionaries to do it. First, I checked if it was in 'num_dict1' by two letters. When the characters were changed to numbers, they were changed to 'x' stored as 0 in 'num_dict2'. Then, using 'num_dict2', all the characters were changed to numbers. The numbers were added to 'sum', and 'sum' was returned.

### 2. Code
```python
class Solution:
    def romanToInt(self, s: str) -> int:
        num_dict1 = {'IV':4, 'IX':9, 'XL':40, 'XC':90, 'CD':400, 'CM':900}
        num_dict2 = {'x':0, 'I':1, 'V':5, 'X':10, 'L':50, 'C':100, 'D':500, 'M':1000}
        str_list = list(s)
        sum = 0
        for i in range(len(str_list)-1):
            if str_list[i]+str_list[i+1] in num_dict1.keys():
                sum += num_dict1[str_list[i]+str_list[i+1]]
                str_list[i] = 'x'
                str_list[i+1] = 'x'
        for e in str_list:
            sum += num_dict2[e]
        return sum
```

### 3. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 36 ms(97.10%), Memory usage : 14.2 MB(100.00%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
