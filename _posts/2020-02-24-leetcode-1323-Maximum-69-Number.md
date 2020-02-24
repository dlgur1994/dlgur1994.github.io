---
title: "leetcode 1323 Maximum 69 Number.py"
date: 2020-02-24 22:52:28 -0400
categories: leetcode solution
---

## 1. What I learned
### &nbsp;&nbsp;&nbsp;&nbsp;a. numList = [int(x) for x in str(num)]  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;It changes 'num' which is a number to a string list.  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;when num=9923, numList = [9,9,2,3]

### &nbsp;&nbsp;&nbsp;&nbsp;b. numList = list(map(int, str(num))) 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;It changes 'num' which is a number to a string list.  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;when num=9923, numList = [9,9,2,3]

### &nbsp;&nbsp;&nbsp;&nbsp;c. numList2 = numList[:] 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;'[:]' is a shallow copy operation. It copies only the values in the list and does not copy the addresses

### &nbsp;&nbsp;&nbsp;&nbsp;d. numList2[i]=9 if numList2[i]==6 else 6  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;It is a 'ternary operator'. Once the conditional expression is satisfied, the first expression is the result. Otherwise, the last expression becomes the result.  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ex) numList2[i]=9 if numList2[i]==6 else 6  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;if numList2[i] == 6, numList2[i] = 9, but if numList2[i] != 6, numList2[i] = 6

### &nbsp;&nbsp;&nbsp;&nbsp;e. temp = int("".join(map(str,numList2))) 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;It changes a list of numbers to a string, and then changes the string to a number.
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ex) numList2 = [1,2,3,4] --> temp = 1234  

## 2. How I sloved
&nbsp;&nbsp;&nbsp;&nbsp;I have to find the maximum value by switching from 6 to 9 or 9 to 6 in the number. First, I get a number and then change it to a list and create a list copied through shallow copying. And by switching 6 and 9 for each digit, the maximum value was saved. I also maintained the number that was first entered through shallow copying each loop. After turning the loop, I returned the maximum value.

## 3. Code
```python
class Solution:
    def maximum69Number (self, num: int) -> int:
        max = int(num)
        #numList = [int(x) for x in str(num)]
        numList = list(map(int, str(num)))
        numList2 = numList[:]
        for i in range(0,len(numList2)):
            numList2[i] = 9 if numList2[i]==6 else 6
            temp = int("".join(map(str,numList2)))
            if temp > max:
                max = temp
            numList2 = numList[:]
        return max
```

## 4. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 20 ms(95.97%), Memory usage : 12.8 MB(100.00%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.

[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms/tree/master/leetcode
