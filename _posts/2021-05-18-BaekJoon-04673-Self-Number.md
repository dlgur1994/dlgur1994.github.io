---
layout: post
title: "BaekJoon 04673 Self Number"
date: 2021-05-18 14:38:28 -0400
categories: [Problem Solving]
tags: [백준, C++, Implementation, Math]
comments: true
---

### 1. Code
```cpp
#include <iostream>

using namespace std;

bool flags[10001] = {false, };

void countNum(int num) {
    int temp = 0;
    int cpy = num;
    while (cpy > 0) {
        temp += cpy%10;
        cpy /= 10;
    }
    flags[num+temp] = true; 
}

int main(void) {
    for (int i=0 ; i<10001 ; i++) {
        countNum(i);
    }

    for (int i=1 ; i<10001 ; i++) {
        if (flags[i]==false) {
            cout << i << '\n';
        }
    } 
    
    return 0;
}
```

### 2. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 0 ms, Memory usage : 2028 KB  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
