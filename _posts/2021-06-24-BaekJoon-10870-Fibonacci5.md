---
layout: post
title: "백준 10870 Fibonacci5"
date: 2021-06-22 13:53:28 -0400
categories: [Problem Solving]
tags: [백준, C++, DynamicProgramming, Math]
comments: true
---

### 1. What I learned
#### &nbsp;&nbsp;&nbsp;&nbsp;printf(), scanf()
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;printf() and scanf() is faster and use less memory than cout and cin.   

### 2. Code
```cpp
#include <stdio.h>

int fib(int num) {
    if (num<2) return num;
    return (fib(num-1)+fib(num-2));
}

int main(void) {
    int n;
    scanf("%d", &n);
    printf("%d\n", fib(n));
    return 0;
}
```

### 3. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 0 ms, Memory usage : 1116 KB  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
