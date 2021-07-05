---
title: "LeetCode 0797 All Paths From Source to Target.py"
categories: LeetCode BackTracking DFS Graph
date: 2020-10-11 14:21:28 -0400
---

## 1. What I learned
### &nbsp;&nbsp;&nbsp;&nbsp;Insert two different elements into a list
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;To insert different elements into a list, write as follows.
```python
stack = [(e,[LIST])]
#don't forget to write ().
```

## 2. How I sloved
&nbsp;&nbsp;&nbsp;&nbsp;I used DFS to get all the routes from 0 to node n-1. Start was always zero and end was n-1. Each node had several routes to other nodes. So I kept storing the previous route on the stack. Because the output was a double-list, when I reached the end node I added a route that was a list to the output list.

## 3. Code
```python
class Solution:
    def allPathsSourceTarget(self, graph: List[List[int]]) -> List[List[int]]:
        def findPath(start):
            route= []
            stack = [(start,[start])]
            while stack:
                node,route = stack.pop()
                if node==len(graph)-1:
                    routes.append(route)
                for e in graph[node]:
                    stack.append((e,route+[e]))
        routes = []
        findPath(0)
        return routes
```

## 4. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 96 ms(92.80%), Memory usage : 15.3 MB(25.16%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.

[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
