---
title: "BaekJoon 01316 Group Word Checker"
categories: BaekJoon C++ Implementation String
date: 2021-06-14 00:07:28 -0400
comments: true
---

### 1. What I learned
#### &nbsp;&nbsp;&nbsp;&nbsp;Get the length of a string
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;To find out the length of a string, '.length() can be used. ex) WORD.length()  

### 2. Code
```cpp
#include <iostream>
#include <string>

using namespace std;

int main(void) {
    int N;
    int cnt = 0;

    cin >> N;
    
    for (int i=0 ; i<N ; i++) {
        int checker[26] = {0,};
        string word;
        char cur = 'A';
        cin >> word;
        for (int j=0 ; j<word.length() ; j++) {
            if (j == word.length()-1) {
                if (word[j]==cur || checker[word[j]-97] == 0) {
                    cnt++;
                }
            }
            else if (word[j] == cur) {
                continue;
            }
            else if (checker[word[j]-97] == 0) {
                checker[word[j]-97]++;
                cur = word[j];
            }
            else {
                break;
            }
        }
    }

    cout << cnt << '\n';
    return 0;
}
```

### 3. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 0 ms, Memory usage : 2024 KB  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
