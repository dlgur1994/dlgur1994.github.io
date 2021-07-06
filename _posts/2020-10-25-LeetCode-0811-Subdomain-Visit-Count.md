---
layout: post
title: "LeetCode 0811 Subdomain Visit Count.py"
date: 2020-10-25 14:04:28 -0400
categories: SolveProblem
tags: [LeetCode, HashTable]
comments: true
---

### 1. What I learned
#### &nbsp;&nbsp;&nbsp;&nbsp;a. Quotes
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;There is no difference between single and double quotes in Python. However, in general, single quotes are used for symbols and identifiers, and double quotes are used for text. In addition, when using different quotes between quotes, the backspace (\) should be added as follows.
```python
print('It\'s me')
#It will print 'It's me'
```
#### &nbsp;&nbsp;&nbsp;&nbsp;b. Making a list a string
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;To make a list a string, write as follows.
```python
mess_list = ['H','e','l','l','o']
mess = ''.join(mess_list)
print(mess)
#I will print 'Hello world'
```
#### &nbsp;&nbsp;&nbsp;&nbsp;c. Extracting keys and values in a dictionary
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;.items() extracts a key and a value pair at once.
```python
samp_dict = {'a': 0, 'b': 1}
for key, value in samp_dict.items():
  print(key, value)
#I will print (a 0) and (b 1)
```

### 2. How I sloved
&nbsp;&nbsp;&nbsp;&nbsp;I had to count the number of times for each domain. So I used a dictionary. The input was a list of the factors being a pair of counts and domains. I divided each element into counts and domains. And the domain was divided based on '.'. I combined domains divided by '.' to create sub-domains. Counts were added if subdomains existed in the dictionary; otherwise, new elements were added. The output was a list of counts and pairs of subdomains.

### 3. Code
```python
class Solution:
    def subdomainVisits(self, cpdomains: List[str]) -> List[str]:
        dom_dict = {}
        for e in cpdomains:
            cnt, subdomain = e.split(' ')
            sub = subdomain.split('.')
            for i in range(len(sub)):
                domain = '.'.join(sub[i:len(sub)])
                if domain in dom_dict:
                    dom_dict[domain] += int(cnt)
                else: dom_dict[domain] = int(cnt)
        output_list = []
        for subdom, cnt in dom_dict.items():
            output_list += [str(cnt)+ ' '+ subdom]
        return output_list
```

### 4. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 44 ms(97.28%), Memory usage : 14.2 MB(100.00%)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.

[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms
