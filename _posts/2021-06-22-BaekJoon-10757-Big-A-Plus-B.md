---
title: "BaekJoon 10757 Big A Plus B"
categories: BaekJoon C++ Math Implementation
date: 2021-06-22 13:53:28 -0400
comments: true
---

### 1. What I learned
#### &nbsp;&nbsp;&nbsp;&nbsp;STRING.length()
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;It is used to get a length of a string  
#### &nbsp;&nbsp;&nbsp;&nbsp;swap(A,B)
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;It is used to exchange values 
#### &nbsp;&nbsp;&nbsp;&nbsp;STRING[i] - '0'
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;To replace a character in a string with a number, the string '0' must be subtracted. ex) STRING[i] - '0' 

### 2. Code
```cpp
#include <iostream>
#include <algorithm>

using namespace std;

int main(void) {
    string a, b;
    int ans[10001] = {0,};

    cin >> a >> b;
    if (b.length() > a.length()) {
        swap(a,b);
    }
    reverse(a.begin(), a.end());
    reverse(b.begin(), b.end());
    
    for (int i=0 ; i<a.length() ; i++) {
        if (i < b.length()) {
            ans[i] += a[i]-'0' + b[i]-'0';
        }
        else {
            ans[i] += a[i]-'0';
        }
        if (ans[i] > 9) {
            ans[i] = ans[i]-10;
            ans[i+1]++;
        }
    }

    for (int i=a.length() ; i>-1 ; i--) {
        if (i==a.length() && ans[i]==0) {
            continue;
        }
        cout << ans[i];
    }
    cout << '\n';
    return 0;
}
```

### 3. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 0 ms, Memory usage : 2024 KB  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
