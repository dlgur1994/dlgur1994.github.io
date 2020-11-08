---
title: "LeetCode 0868 Binary Gap.py"
categories: LeetCode Math
date: 2020-11-08 16:45:28 -0400
comments: true
---

### 1. How I sloved
&nbsp;&nbsp;&nbsp;&nbsp;I had to figure out the longest distance between the two adjacent ones. First, when the number was changed to binary, the index was stored in the list if it was 1. The difference in adjacent indices was then compared and the greatest difference was returned.

### 2. Code
```python
class Solution:
    def binaryGap(self, n: int) -> int:
        cnt = 0
        check_list = []
        while n>1:
            if int(n%2) == 1:
                check_list.append(cnt)
            cnt += 1
            n //= 2
        if n == 1:
            check_list.append(cnt)

        max_len = 0
        for i in range(len(check_list)-1):
            lens = check_list[i+1] - check_list[i]
            if lens>max_len:
                max_len = lens
        return max_len
```

### 3. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 24 ms(93.89%), Memory usage : 14 MB(100.00%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
