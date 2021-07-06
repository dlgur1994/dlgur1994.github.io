---
layout: post
title: "LeetCode 0771 Jewels and Stones.py"
date: 2020-01-16 18:59:28 -0400
categories: SolveProblem
tags: [LeetCode, HashTable]
comments: true
---

## 1. What I learned
### &nbsp;&nbsp;&nbsp;&nbsp;a. for e in 'String'
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;When I use "for e in 'String'", e means each character in 'String'.    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ex)
```python
for e in 'Hello'
  print (e)
```
--> H,e,l,l,o (actually, each character is printed on each line)

### &nbsp;&nbsp;&nbsp;&nbsp;b. count() method
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;This method counts 'keyword' in 'target'.  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ex) 'target'.count('keyword')  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;cf) I can use either ' ' or " "

### &nbsp;&nbsp;&nbsp;&nbsp;c. map() method
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;This method executes 'function' in 'target'.  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ex) map('function', 'target')  

### &nbsp;&nbsp;&nbsp;&nbsp;c. sum() method
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;This adds everything in ().  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ex)  
```python
list = [1,2,3]
print (sum(list))
```  
--> 6 is printed.

## 2. How I sloved
&nbsp;&nbsp;&nbsp;&nbsp;I have to count the number of each character of J in S. So I use a 'for loop'. The number of repetitions of 'for loop' was the number of characters in J. And for each loop, the frequency of each charater in S was added.

## 3. Code
```python
class Solution:
    def numJewelsInStones(self, J: str, S: str) -> int:
        numOfJew = 0
        for e in J:
            numOfJew += S.count(e)
        return numOfJew
```
---

```python
class Solution:
    def numJewelsInStones(self, J: str, S: str) -> int:
        return sum(map(J.count, S))
```

## 4. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 24 ms(88.17%), Memory usage : 12.7 MB(100.00%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.

[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms/tree/master/leetcode
