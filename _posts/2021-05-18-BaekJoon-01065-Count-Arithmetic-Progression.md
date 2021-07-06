---
layout: post
title: "백준 01065 Count Arithmetic Progression"
date: 2021-05-18 14:40:28 -0400
categories: SolveProblem
tags: [백준, C++, BruteForce]
comments: true
---

### 1. Code
```cpp
#include <iostream>

using namespace std;

int countRule(int num) {
    if (num < 100) {
        return 1;
    }
    else if ((num<1000) && (num%10-num/10%10 == num/10%10-num/100%10)) {
        return 1;
    }
    else {
        return 0;
    }
}

int main(void) {
    int num;
    int cnt = 0;
    cin >> num;

    for (int i=1 ; i<num+1 ; i++) {
        cnt += countRule(i);
    }

    cout << cnt << '\n';
    return 0;
}
```

### 2. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 0 ms, Memory usage : 2016 KB  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
