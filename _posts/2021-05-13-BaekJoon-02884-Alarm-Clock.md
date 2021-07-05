---
title: "BaekJoon 02884 Alarm Clock"
categories: BaekJoon C++ Implementation Math
date: 2021-05-13 22:50:28 -0400
comments: true
---

### 1. Code
```cpp
#include <iostream>

using namespace std;

int main(void) {
    int hr, min;
    cin >> hr >> min;

    // Subtract 45 minutes from min
    min -= 45;

    // if min is less than zero, borrow an hour and convert it to 60 minutes
    if (min < 0) {
        min += 60;
        hr -= 1;

        // if hr becomes less than zero, change it to 23
        if (hr < 0)
        hr = 23;
    }
    
    cout << hr << " " << min << "\n";
    return 0;
}
```

### 2. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 0 ms, Memory usage : 2016 KB  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
