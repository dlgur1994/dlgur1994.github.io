---
layout: post
title: "백준 03052 Remainder"
date: 2021-05-17 19:28:28 -0400
categories: ProblemSolving
tags: [백준, C++, Implementation, Math]
comments: true
---

### 1. Code
```cpp
#include <iostream>

using namespace std;

int main(void) {
    int temp;
    int cnt = 0; 
    int nums[42] = {0,};
    for (int i=0 ; i<10 ; i++) {
        cin >> temp;
        nums[temp%42] = 1;
    }

    for (int i=0 ; i<42 ; i++) {
        if (nums[i] == 1) {
            cnt++;
        }
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
