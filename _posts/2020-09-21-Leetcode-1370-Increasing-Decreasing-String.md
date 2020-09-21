---
title: "LeetCode 1370 Increasing Decreasing String.py"
categories: LeetCode solution
date: 2020-09-21 17:17:28 -0400
---

## 1. What I learned
### &nbsp;&nbsp;&nbsp;&nbsp;a. reversed for loop
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;To reverse 'for loop', write as follows.
```python
for i in range(5,0,-1):
  print(i)
#It will print '5,4,3,2,1'
```

### &nbsp;&nbsp;&nbsp;&nbsp;b. Counter class  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;'Counter(STRING)' from 'collections' returns a dictionary counting the frequency of each key in STRING.
```python
s = 'Hello'
char_dict = Counter(s)
print(char_dict)
#It will print 'Counter({'l': 2, 'H': 1, 'e': 1, 'o': 1})'
```

## 2. How I sloved
&nbsp;&nbsp;&nbsp;&nbsp;I counted each alphabet in 'S' using 'Counter()'. I defined each alphabet as 'key_list' to store it and sorted it alphabetically. Two for loops were executed until 'len(output)' was equal to 'len(s)'. The first for loop was the second and third condition of the problem, and the second for loop was the forth and fifth condition.  

## 3. Code
```python
class Solution:
    def sortString(self, s: str) -> str:
        char_dict = Counter(s)
        key_list = sorted(char_dict.keys())
        output = ""

        while len(output) < len(s):
            for e in key_list:
                if char_dict[e] > 0:
                    output += e
                    char_dict[e] -= 1
            for e in reversed(key_list):
                if char_dict[e] > 0:
                    output += e
                    char_dict[e] -= 1

        return output
```

```python
# my first version, but took too much time
# class Solution:
#     def sortString(self, s: str) -> str:
#         output = []
#         temp = sorted(list(s))
#
#         while len(temp)>0:
#             output.append(temp[0])
#             temp.remove(temp[0])
#             for e in temp:
#                 if e>output[-1]:
#                     output.append(e)
#                     temp[temp.index(e)] = ''
#             temp = [e for e in temp if e]
#
#             if len(temp)==0:
#                 break
#
#             output.append(temp[-1])
#             temp.remove(temp[-1])
#             for i in range(len(temp)-1,0,-1):
#                 if temp[i]<output[-1]:
#                     output.append(temp[i])
#                     temp[i] = ''
#             temp = [e for e in temp if e]
#
#         return ''.join(output)
```
## 4. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 64 ms(81.25%), Memory usage : 13.7 MB(86.61%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.

[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
