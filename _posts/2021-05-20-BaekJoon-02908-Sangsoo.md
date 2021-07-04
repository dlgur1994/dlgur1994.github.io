---
title: "BaekJoon 02908 Sangsoo"
categories: BaekJoon C++ Implementation
date: 2021-05-20 22:54:28 -0400
comments: true
---

### 1. What I learned
#### &nbsp;&nbsp;&nbsp;&nbsp;How to initialize multiple variables
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;When initializing multiple variables in a single line, they should be written separately. ex) 'int a=0, b=1, c=2;' 

### 2. Code
```cpp
#include <iostream>

using namespace std;

int main(void) {
    int num1, num2;
    int rev1=0, rev2=0;
    cin >> num1 >> num2;

    for (int i=0 ; i<3 ; i++) {
        rev1 *= 10;
        rev2 *= 10;
        rev1 += num1%10;
        rev2 += num2%10;
        num1 /= 10;
        num2 /= 10;
    }

    if (rev1 > rev2) {
        cout << rev1 << '\n';
    }
    else {
        cout << rev2 << '\n';
    }
    return 0;
}
```

### 3. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 0 ms, Memory usage : 2020 KB  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
