---
layout: post
title: "백준 02562 Maximum"
date: 2021-05-16 13:47:28 -0400
categories: SolveProblem
tags: [백준, C++, Implementation, Math]
comments: true
---

### 1. Code
```cpp
#include <iostream>

using namespace std;

int main(void) {
    int nums[9];
    int max=0 ,idx=0;

    for (int i=0 ; i<9 ; i++) {
        cin >> nums[i];
    }
    for (int i=0 ; i<9 ; i++) {
        if (nums[i] > max) {
            max = nums[i];
            idx = i;
        } 
    }

    cout << max << "\n" << idx+1 << "\n";
    return 0;
}
```

### 2. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 0 ms, Memory usage : 2016 KB  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
