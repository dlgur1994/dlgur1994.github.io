---
layout: post
title: "백준 11022 Add N Times 3"
date: 2021-05-14 13:48:28 -0400
categories: SolveProblem
tags: [백준, C++, Implementation, Math]
comments: true
---

### 1. Code
```cpp
#include <iostream>

using namespace std;

int main(void) {
    int n, a, b;
    cin >> n;

    for (int i=0 ; i<n ; i++) {
        cin >> a >> b;
        cout << "Case #" << i+1 << ": " << a << " + " << b << " = " << a+b << "\n";
    }

    return 0;
}
```

### 2. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 4 ms, Memory usage : 2016 KB  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
