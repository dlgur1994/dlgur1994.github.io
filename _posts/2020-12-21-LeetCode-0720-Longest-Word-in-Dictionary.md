---
title: "LeetCode 0720 Longest Word in Dictionary"
categories: LeetCode HashTable Trie
date: 2020-12-21 17:06:28 -0400
comments: true
---

## 1. What I learned
### &nbsp;&nbsp;&nbsp;&nbsp;Trie
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Trie is a tree structure called prefix tree that stores a string in a tree format so that it does not overlap if it contains the same alphabet. It is efficient because it takes O(n) to retrieve strings.
```python
class Node:
    def __init__(self, key):
        self.key = key
        self.children = {}
        self.isEnd = False

class Trie:
    def __init__(self):
        self.head = Node(None)

    def insertWord(self, word):
        cur = self.head
        for e in word:
            if e not in cur.children:
                cur.children[e] = Node(e)
            cur = cur.children[e]
        cur.isEnd = True

trie = Trie()
trie.insert("hello")
trie.insert("helloworld")
# None --> "h" --> "e" --> "l" --> "l" --> "o" --> "w" --> "o" --> "r" --> "l" --> "d"
```

### 2. Code
```python
class Solution:
    def longestWord(self, words: List[str]) -> str:
        word_set = set()
        result = ""
        words.sort() # to obtain result in the smallest lexical order
        for word in words:
          if len(word)==1 or word[:-1] in word_set: # This is a trie concept, which means that word[:-1] is in word_set.
            if len(result) < len(word):
              result = word
            word_set.add(word)
        return result
```

### 3. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 64 ms(98.64%), Memory usage : 14.5 MB(79.08%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
