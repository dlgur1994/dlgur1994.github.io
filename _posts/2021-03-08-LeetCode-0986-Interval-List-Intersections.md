---
title: "LeetCode 0986 Interval List Intersections"
categories: LeetCode Python TwoPointers
date: 2021-03-08 23:57:28 -0400
comments: true
---

### 1. Code
```python
class Solution:
    def intervalIntersection(self, first_list: List[List[int]], second_list: List[List[int]]) -> List[List[int]]:
        if first_list==[] or second_list==[]: # if either of the two is empty
            return []
        ans = []
        cnt1, cnt2 = 0, 0
        while True:
            if first_list[cnt1][1] < second_list[cnt2][0]: # when the range of the second list element is greater than the range of the first list element
                cnt1 += 1
            elif first_list[cnt1][0] > second_list[cnt2][1]: # when the range of the first list element is greater than the range of the second list element
                cnt2 += 1
            elif first_list[cnt1][0]<=second_list[cnt2][0] and first_list[cnt1][1]>=second_list[cnt2][1]: # when the first list element contains the second list element
                ans.append(second_list[cnt2])
                cnt2 += 1
            elif first_list[cnt1][0]>=second_list[cnt2][0] and first_list[cnt1][1]<=second_list[cnt2][1]: # when the second list element contains the first list element
                ans.append(first_list[cnt1])
                cnt1 += 1
            elif first_list[cnt1][0]<=second_list[cnt2][0] and first_list[cnt1][1]<=second_list[cnt2][1]: # when the two elements overlap
                ans.append([second_list[cnt2][0],first_list[cnt1][1]])
                cnt1 += 1
            elif first_list[cnt1][0]>=second_list[cnt2][0] and first_list[cnt1][1]>=second_list[cnt2][1]: # when the two elements overlap
                ans.append([first_list[cnt1][0],second_list[cnt2][1]])
                cnt2 += 1
            if cnt1==len(first_list) or cnt2==len(second_list): # if either list ends
                return ans
```

### 2. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 144 ms(88.60%), Memory usage : 14.7 MB(99.74%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
