---
layout: post
title: "LeetCode 0022 Generate Parentheses"
date: 2021-03-18 16:24:28 -0400
categories: SolveProblem
tags: [LeetCode, Python, BackTracking, String]
comments: true
---

### 1. Code
```python
class Solution:
    def generateParenthesis(self, n: int) -> List[str]:
        def dfs(s, bal):
            if len(s) == 2*n: # when s is completed
                return result.append(s)
            else:
                if bal == 0:
                    dfs(s+"(", bal+1 )
                else :
                    if s.count("(") < n:
                        dfs(s+"(",bal+1)
                    dfs(s+")",bal-1)

        result = []
        dfs("(",1)
        return result
```

### 2. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 28 ms(96.03%), Memory usage : 14.6 MB(69.40%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
