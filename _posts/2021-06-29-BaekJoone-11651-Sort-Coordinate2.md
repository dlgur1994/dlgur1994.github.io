---
title: "BaekJoon 11651 Sort Coordinate2"
categories: BaekJoon C++ Sort
date: 2021-06-29 21:47:28 -0400
comments: true
---

### 1. What I learned
#### &nbsp;&nbsp;&nbsp;&nbsp;a. Vector<>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Vector is simply an array of dynamically changing lengths.   
#### &nbsp;&nbsp;&nbsp;&nbsp;b. sort(Vector<>)
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;To sort the internal values of vectors in ascending order, sort() in the 'algorithm' header file can be used.   

### 2. Code
```cpp
#include <stdio.h>
#include <vector>
#include <algorithm>

using namespace std;

int main(void) {
    int num_of_points, x, y;
    vector<pair<int,int> > points;

    scanf("%d", &num_of_points);
    for (int i=0 ; i<num_of_points ; i++) {
        scanf("%d %d", &x, &y);
        points.push_back(pair<int,int>(y,x));
    }

    sort(points.begin(), points.end());

    for (int i=0 ; i<num_of_points ; i++) {
        printf("%d %d\n", points[i].second, points[i].first);
    }
    return 0;
}

### 3. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 64 ms, Memory usage : 2776 KB  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
