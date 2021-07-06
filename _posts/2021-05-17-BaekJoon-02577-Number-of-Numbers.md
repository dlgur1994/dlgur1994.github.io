---
layout: post
title: "백준 02577 Number of Numbers"
date: 2021-05-17 19:27:28 -0400
categories: SolveProblem
tags: [백준, C++, Implementation, Math, String]
comments: true
---

### 1. Code
```cpp
#include <iostream>

using namespace std;

int main(void) {
    int A,B,C, mul;
    int cnts[10] = {0,};
    cin >> A >> B >> C;

    mul = A*B*C;
    while(mul>0) {
        cnts[mul%10]++;
        mul /= 10;
    }
    
    for (int i=0 ; i<10 ; i++) {
        cout << cnts[i] << "\n";
    } 
    return 0;
}
```

### 2. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 0 ms, Memory usage : 2016 KB  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
