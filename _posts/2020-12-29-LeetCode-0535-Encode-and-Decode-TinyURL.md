---
title: "LeetCode 0535 Encode and Decode TinyURL"
categories: LeetCode HashTable Math
date: 2020-12-29 10:45:28 -0400
comments: true
---

## 1. What I learned
### &nbsp;&nbsp;&nbsp;&nbsp;hash()
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; It returns the hash value of an object if it has one. Even if you give the same value as a variable, the hash value always changes with each run.
```python
msg = "hello"
print(hash(msg))
# -3167519980713740997 (1st try)
# -1242044876459104822 (2nd try)
```

### 2. Code
```python
class Codec:
    def __init__(self):
        self.dict = {}

    def encode(self, longUrl: str) -> str:
        shortUrl = hash(longUrl) # Create a hash value through hash()
        self.dict[shortUrl] = longUrl
        return shortUrl

    def decode(self, shortUrl: str) -> str:
        return self.dict[shortUrl]
```

### 3. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 28 ms(90.43%), Memory usage : 14.1 MB(90.43%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
