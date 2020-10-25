---
title: "LeetCode 1221 Split a String in Balanced Strings.py"
date: 2020-01-20 23:55:28 -0400
categories: LeetCode String Greedy
---

## 1. What I learned
### &nbsp;&nbsp;&nbsp;&nbsp;"command" if "condition" else "B"
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"command" will be executed if "condition" is met. In the other case "B" will be executed.  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ex) num += 1 if c == 'L' else -1  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;if c == 'L', num += 1, but if c != 'L', num += -1

## 2. How I sloved
&nbsp;&nbsp;&nbsp;&nbsp;I have to count the number of pairs of 'L' and 'R'.
I set 'first' as the first letter of s.
If the next letter of 's' is same as 'first', I add one to 'numOfSame'.
In the opposite case I subtract one from 'numOfSame'.
And if 'numOfSame' is 0, meaning 'L' and 'R' are balanced, I add one to 'numOfBal'.
I do it 'len(s)-1' times over through for loop.

## 3. Code
```python
class Solution:
    def balancedStringSplit(self, s: str) -> int:
        first = s[0]
        numOfSame = 1
        numOfBal = 0

        for i in range(1,len(s)):
            if first == s[i]:
                numOfSame += 1
            else:
                numOfSame -= 1
            if numOfSame == 0:
                numOfBal += 1

        return numOfBal
```

## 4. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 24 ms(88.15%), Memory usage : 12.8 MB(100.00%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.

[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms/tree/master/leetcode
