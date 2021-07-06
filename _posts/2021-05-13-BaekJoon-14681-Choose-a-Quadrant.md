---
layout: post
title: "백준 14681 Choose a Quadrant"
date: 2021-05-13 22:53:28 -0400
categories: SolveProblem
tags: [백준, C++, Geometry, Implementation, Math]
comments: true
---

### 1. Code
```cpp
#include <iostream>

using namespace std;

int main(void) {
    int a, b;
    cin >> a;
    cin >> b;

    if (a>0 && b>0)
        cout << "1";
    else if (a<0 && b>0)
        cout << "2";
    else if (a<0 && b<0)
        cout << "3";
    else    
        cout << "4";
    cout << "\n";

    return 0;
}
```

### 2. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 0 ms, Memory usage : 2016 KB  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
