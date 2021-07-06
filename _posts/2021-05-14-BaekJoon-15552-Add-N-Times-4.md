---
layout: post
title: "백준 15552 Add N Times 4"
date: 2021-05-14 13:53:28 -0400
categories: SolveProblem
tags: [백준, C++, Implementation, Math]
comments: true
---

### 1. Code
```cpp
#include <iostream>

using namespace std;

int main(void) {
    cin.tie(NULL); // stop flushing the stream
    ios::sync_with_stdio(false); // it asynchronizes the input and output of C and C++

    int n, a, b;
    cin >> n;

    for (int i=0 ; i<n ; i++) {
        cin >> a >> b;
        cout << a+b << "\n";
    }

    return 0;
}
```

### 2. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 232 ms, Memory usage : 2016 KB  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
