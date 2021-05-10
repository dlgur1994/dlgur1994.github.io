---
title: "BaekJoon 1330 Compare Two Numbers"
categories: BaekJoon C++ Implementation Math
date: 2021-05-10 19:56:28 -0400
comments: true
---

### 1. What I learned
#### &nbsp;&nbsp;&nbsp;&nbsp;How to print a message in C++
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;'iostream' header file was added first to print the message. I used 'std:cout < "MESSAGE"' to print messages, and used 'using namespace std' to reduce repeated use of 'std:'.  

### 2. Code
```cpp
#include <iostream>

using namespace std;

int main(void) {
    int num1, num2;
    cin >> num1 >> num2;

    if (num1 > num2)
        cout << ">";
    else if (num1 == num2)
        cout << "==";
    else   
        cout << "<";
    cout << "\n";
    return 0;
}
```

### 3. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 0 ms, Memory usage : 2016 KB  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
