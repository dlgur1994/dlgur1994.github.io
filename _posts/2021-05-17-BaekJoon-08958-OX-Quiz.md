---
layout: post
title: "백준 08958 OX Quiz"
date: 2021-05-17 19:32:28 -0400
categories: ProblemSolving
tags: [백준, C++, Implementation, String]
comments: true
---

### 1. Code
```cpp
#include <iostream>

using namespace std;

int main(void) {
    int n, idx, cnt, sum;
    string str;
    cin >> n;

    for (int i=0 ; i<n ; i++) {
        cin >> str;
        idx = 0;
        cnt = 1;
        sum = 0;
        while(str[idx] != '\0') {
            if (str[idx] == 'O') {
                sum += cnt;
                cnt++;
            }
            else {
                cnt = 1;
            }
            idx++;
        }
        cout << sum << '\n';
    }

    return 0;
}
```

### 2. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 4 ms, Memory usage : 2016 KB  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
