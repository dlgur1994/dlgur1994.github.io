---
layout: post
title: "백준 02675 Repeat String"
date: 2021-05-20 22:58:28 -0400
categories: ProblemSolving
tags: [백준, C++, Implementation]
comments: true
---

### 1. What I learned
#### &nbsp;&nbsp;&nbsp;&nbsp;How to get the length of a string
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;In order to get the length of a string, '.length()' can be used. ex) 'STR.length()'  

### 2. Code
```cpp
#include <iostream>

using namespace std;

int main(void) {
    int N;
    cin >> N;
    int num;
    string str;
    string result;
    
    for (int i=0 ; i<N ; i++) {
        cin >> num >> str;
        result = "";
        for (int j=0 ; j<str.length() ; j++) {
            for (int k=0 ; k<num ; k++) {
                result += str[j];
            }
        }
        cout << result << '\n';
    }

    return 0;
}
```

### 3. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 0 ms, Memory usage : 2024 KB  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
