---
layout: post
title: "LeetCode 0049 Group Anagrams"
date: 2021-10-10 13:34:28 -0400
categories: [Problem Solving]
tags: [LeetCode, Python, Combinatorics, DynamicProgramming, Math]
comments: true
---

### 1. What I learned
- ''.join(sorted(STR))
    - With only sorted(STR), each alphabet of STR is sorted and returned in the form of a list. 'join()' has to be used to sort the alphabets and merge them back into the string.

### 2. Code
```python
class Solution:
    def groupAnagrams(self, strs: List[str]) -> List[List[str]]:
        ana_dic = dict()
        for e in strs:
            temp = ''.join(sorted(e))
            if temp in ana_dic:
                ana_dic[temp].append(e)
            else:
                ana_dic[temp] = [e]
        return list(ana_dic.values())
```

### 3. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 88 ms(97.70%), Memory usage : 17.2 MB(86.46%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
