---
layout: post
title: "백준 01110 Add Cycle"
date: 2021-05-16 13:48:28 -0400
categories: [Problem Solving]
tags: [백준, C++, Implementation, Math]
comments: true
---

### 1. Code
```cpp
#include <iostream>

using namespace std;

int main(void) {
    int num, fix;
    int sum=0, cnt=0;
    cin >> num;
    fix = num;

    while(true) {
        sum = num/10 + num%10;
        num = (num%10)*10 + sum%10;
        cnt++;
        if (fix==num)
            break;
    }

    cout << cnt << "\n";
    return 0;
}
```

### 2. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 0 ms, Memory usage : 2016 KB  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
