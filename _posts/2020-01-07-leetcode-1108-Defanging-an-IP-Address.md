---
title: "leetcode 1108 Defanging-an-IP-Address.py"
date: 2020-01-07 23:55:28 -0400
categories: leetcode solution
---

## 1. What I learned
### &nbsp;&nbsp;&nbsp;&nbsp;a. replace() method
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;When I want to replace one with another in a string, I can use replace() method.  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ex) sample.replace("from", "to")  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;cf) I can use either ' ' or " "

### &nbsp;&nbsp;&nbsp;&nbsp;b. join() method
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;This method divides the sample into "from" and combines it into "to" instead of "from".  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ex) "to".join(sample.split("from"))  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;cf) I can use either ' ' or " "

## 2. How I sloved
&nbsp;&nbsp;&nbsp;&nbsp;All I have to do is replacing "." with "[.]". So there are two ways. One is to replace, the other is to divide into ".", and then combines everything by adding "[.]".

## 3. Code
```python
class Solution:  
    def defangIPaddr(self, address: str) -> str:  
        return address.replace(".","[.]")  
```
---

```python
class Solution:  
    def defangIPaddr(self, address: str) -> str:  
        return "[.]".join(address.split('.'))  
```

## 4. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 16 ms(99.51%), Memory usage : 12.7 MB(100.00%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.

[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms/tree/master/leetcode
