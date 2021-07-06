---
layout: post
title: "LeetCode 0401 Binary Watch.py"
date: 2020-12-02 11:44:28 -0400
categories: SolveProblem
tags: [LeetCode, BackTracking, BitManipulation]
comments: true
---

## 1. What I learned
### &nbsp;&nbsp;&nbsp;&nbsp;a. from itertools import combinations
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;We can use a combination with this.
```python
from itertools import combinations
nums = [1,2,3,4,5]
print(list(combinations(nums, 2)))
#[(1, 2), (1, 3), (1, 4), (1, 5), (2, 3), (2, 4), (2, 5), (3, 4), (3, 5), (4, 5)]
```
### &nbsp;&nbsp;&nbsp;&nbsp;b. "%d:%02d" %(hour, minut)
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;It returns a string with a format.
```python
#"%d" means an integer number and "%02d" means double-digit integer number
print("%d:%02d" %(2, 4))
#"2:04"
```

### 2. Code
```python
class Solution:
    def readBinaryWatch(self, num: int) -> List[str]:
        bits = ['0','1','2','3','4','5','6','7','8','9']
        minuts = {'0':1, '1':2, '2':4, '3':8, '4':16, '5':32}
        hours = {'6':1, '7':2, '8':4, '9':8}

        #Use all possible combinations of numbers
        ons = list(combinations(bits, num))
        times = []
        for on in ons:
            hour = 0
            minut = 0
            for e in on:
                if e in minuts:
                    minut += minuts[e]
                else:
                    hour += hours[e]
            if hour>11 or minut>59:
                continue
            #to fit the two-digit format in minutes
            times.append("%d:%02d" % (hour, minut))
        return times
```

### 3. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 28 ms(85.40%), Memory usage : 14.2 MB(53.24%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
