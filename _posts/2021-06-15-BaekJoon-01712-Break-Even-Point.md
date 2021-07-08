---
layout: post
title: "백준 01712 Break Even Point"
date: 2021-06-15 22:42:28 -0400
categories: ProblemSolving
tags: [백준, C++, Math]
comments: true
---

### 1. What I learned
#### &nbsp;&nbsp;&nbsp;&nbsp;Round a number upward
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;To round a number upward, 'ceil()' can be used. ex) ceil(NUMBER)  

### 2. Code
```cpp
#include <iostream>
#include <cmath>

using namespace std;

int main(void) {
    int fixed;
    int vari;
    int price;
    int point;

    cin >> fixed >> vari >> price;
    // if 'price' is equal to or less than 'vari', there is no break-even point
    if (price==vari || price<vari) {
        cout << -1 << '\n';
        return 0;
    }

    point = fixed/(price-vari);
    // it is when revenue and expenditure are at the same point
    if (point == ceil(point)) {
        point++;
    }
    else {
        point = ceil(point);
    }
    cout << point << '\n';
    return 0;
}
```

### 3. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 0 ms, Memory usage : 2020 KB  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
