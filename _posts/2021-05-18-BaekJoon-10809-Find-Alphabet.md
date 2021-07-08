---
layout: post
title: "백준 10809 Find Alphabet"
date: 2021-05-18 23:07:28 -0400
categories: [Problem Solving]
tags: [백준, C++, Implementation, String]
comments: true
---

### 1. What I learned
#### &nbsp;&nbsp;&nbsp;&nbsp;How to initialize an array
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;When initializing an array with a single number, 'fill_n(ARRAY, LENGTH_OF_ARRAY, NUMBER_TO_INITIALIZE)' can be used.  

### 2. Code
```cpp
#include <iostream>

using namespace std;

int main(void) {
    string str;
    int idx = 0;
    int chs[26];
    fill_n(chs, 26, -1);
    
    cin >> str;

    while (str[idx] != '\0') {
        if (chs[str[idx]-97] == -1) {
            chs[str[idx]-97] = idx;
        }
        idx++;
    }

    for (int i=0 ; i<26 ; i++) {
        if (i == 25) {
            cout << chs[i] << '\n';
            break;
        }
        cout << chs[i] << ' ';
    }
    return 0;
}
```

### 3. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 0 ms, Memory usage : 2016 KB  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
