---
layout: post
title: "백준 01546 Average"
date: 2021-05-14 19:30:28 -0400
categories: ProblemSolving
tags: [백준, C++, Implementation, Math]
comments: true
---

### 1. Code
```cpp
#include <iostream>

using namespace std;

int main(void) {
    int N;
    int max = 0;
    double sum = 0;
    cin >> N;
    int scores[N];
    for (int i=0 ; i<N ; i++) {
        cin >> scores[i];
        if (scores[i] > max)
            max = scores[i];
    }

    for (int i=0 ; i<N ; i++) {
        sum += double(scores[i])/max*100;
    }

    cout << sum/double(N) << "\n";
    return 0;
}
```

### 2. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 0 ms, Memory usage : 2016 KB  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
