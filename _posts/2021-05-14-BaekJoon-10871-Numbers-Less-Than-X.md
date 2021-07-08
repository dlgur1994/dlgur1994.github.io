---
layout: post
title: "백준 10871 Numbers Less Than X"
date: 2021-05-14 13:50:28 -0400
categories: [Problem Solving]
tags: [백준, C++, Implementation, Math]
comments: true
---

### 1. Code
```cpp
#include <iostream>

using namespace std;

int main(void) {
    int N, X;
    cin >> N >> X;
    int nums[N];

    for (int i=0 ; i<N ; i++) {
        cin >> nums[i];
    }

    for (int i=0 ; i<N ; i++) {
        if (nums[i] < X) {
            cout << nums[i] << " ";
        }
    }
    
    cout << "\n";
    return 0;
}
```

### 2. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 4 ms, Memory usage : 2016 KB  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
