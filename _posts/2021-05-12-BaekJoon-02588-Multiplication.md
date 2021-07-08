---
layout: post
title: "백준 02588 Multiplication"
date: 2021-05-12 22:47:28 -0400
categories: [Problem Solving]
tags: [백준, C++, Math]
comments: true
---

### 1. Code
```cpp
#include <iostream>

using namespace std;

int main(void) {
    int a, b, mult;
    cin >> a >> b;
    mult = a*b;

    for (int i=0 ; i<3 ; i++) {
        cout << a*(b%10) << "\n";
        b /= 10;
    }
    cout << mult << "\n";
    return 0;
}
```

### 2. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 0 ms, Memory usage : 2016 KB  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
