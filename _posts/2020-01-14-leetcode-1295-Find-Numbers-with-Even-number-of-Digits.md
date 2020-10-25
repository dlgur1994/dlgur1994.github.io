---
title: "LeetCode 1295 Find Numbers with Even Number of Digits.py"
date: 2020-01-14 11:53:28 -0400
categories: LeetCode Array
---

### 1. What's new
    a. rstrip() method

### 2. Code
```python
class Solution:
    def findNumbers(self, nums) -> int:
        numOfEven = 0

        for e in nums:
            if len(str(e))%2 == 0:
                numOfEven += 1

        return numOfEven
```

Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.  

[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms/tree/master/leetcode
