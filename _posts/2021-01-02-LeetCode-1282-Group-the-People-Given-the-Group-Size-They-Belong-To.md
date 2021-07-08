---
layout: post
title: "LeetCode 1282 Group the People Given the Group Size They Belong To"
date: 2021-01-02 15:05:28 -0400
categories: ProblemSolving
tags: [LeetCode, Greedy]
comments: true
---

## 1. What I learned
### &nbsp;&nbsp;&nbsp;&nbsp;defaultdict()
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; When you first create a dictionary and insert a value, make sure that the value corresponding to the key is present or not. However, this process can be omitted through defaultdict().
```python
from colletions import defaultdict
dic = defaultdict()
lists = [1,2,3,4,5]
for e in lists:
  dic[e] = e*e
print(dic)
# defaultdict(None, {1: 1, 2: 4, 3: 9, 4: 16, 5: 25})
```

### 2. Code
```python
from collections import defaultdict

class Solution:
    def groupThePeople(self, groupSizes: List[int]) -> List[List[int]]:
        # Store the group size of each element in the dictionary.
        check = defaultdict(list)
        for i,e in enumerate(groupSizes):
            check[e].append(i)

        # If the value of the check is greater than the key, divide it and extend it to the result. If not, extend it to the result.
        result = []
        for e in check:
            if len(check[e]) > e:
                for i in range(0,len(check[e]),e):
                    result.append(check[e][i:i+e])
            else:
                result.append(check[e])
        return result
```

### 3. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 64 ms(99.23%), Memory usage : 14.3 MB(81.38%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
