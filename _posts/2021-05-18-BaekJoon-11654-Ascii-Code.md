---
layout: post
title: "백준 11654 Ascii Code"
date: 2021-05-18 22:58:28 -0400
categories: ProblemSolving
tags: [백준, C++, Implementation]
comments: true
---

### 1. What I learned
#### &nbsp;&nbsp;&nbsp;&nbsp;How to change a data type
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;When changing a data type, use 'static_cast<CHANGED_DATA_TYPE>(DATA_TYPE_TO_CHANGE)'.  

### 2. Code
```cpp
#include <iostream>

using namespace std;

int main(void) {
    char ch;
    cin >> ch;

    cout << static_cast<int>(ch) << '\n';
    return 0;
}
```

### 3. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 0 ms, Memory usage : 2016 KB  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
