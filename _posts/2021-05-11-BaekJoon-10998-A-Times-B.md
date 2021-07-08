---
layout: post
title: "백준 10998 A Times B"
date: 2021-05-11 11:08:28 -0400
categories: ProblemSolving
tags: [백준, C++, Implementation, Math]
comments: true
---

### 1. What I learned
#### &nbsp;&nbsp;&nbsp;&nbsp;How to write multiple outputs on a single line
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;To write down multiple outputs at once, continue with '<<'. ex) cout << "Hello" << "World;  

### 2. Code
```cpp
#include <iostream>

using namespace std;

int main(void) {
    int a, b;
    cin >> a >> b;
    cout << a*b << "\n";

    return 0;
}
```

### 3. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 0 ms, Memory usage : 2016 KB  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
