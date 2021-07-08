---
layout: post
title: "백준 10430 Remainder"
date: 2021-05-12 22:49:28 -0400
categories: [Problem Solving]
tags: [백준, C++, Implementation, Math]
comments: true
---

### 1. Code
```cpp
#include <iostream>

using namespace std;

int main(void) {
    int a, b, c;
    cin >> a >> b >> c;

    cout << (a+b)%c << "\n";
    cout << ((a%c)+(b%c))%c << "\n";
    cout << (a*b)%c << "\n";
    cout << ((a%c)*(b%c))%c << "\n";
    return 0;
}
```

### 2. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 0 ms, Memory usage : 2016 KB  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
