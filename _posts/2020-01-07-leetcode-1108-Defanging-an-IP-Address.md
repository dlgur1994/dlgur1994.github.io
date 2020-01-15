---
title: "leetcode 1108 Defanging-an-IP-Address.py"
date: 2020-01-07 23:55:28 -0400
categories: leetcode solution
---

### 1. What I learned
##### &nbsp;&nbsp;&nbsp;&nbsp;a. replace() method
              When I want to replace one with another in a string, I can use replace() method.
              ex) sample.replace("from", "to")  
              cf) I can use '' or ""
              
##### &nbsp;&nbsp;&nbsp;&nbsp;b. join() method
              This method divides the sample into "from" and combines it into "to" instead of "from".
              ex) "to".join(sample.split("from"))    
              cf) I can use '' or ""
### 2. Code
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

Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.

[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms/tree/master/leetcode
