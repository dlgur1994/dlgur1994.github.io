---
title: "leetcode 1108 Defanging-an-IP-Address.py"
date: 2020-01-07 23:55:28 -0400
categories: leetcode solution
---

### 1. What's new
    a. function "replace"
    b. function "join"

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
