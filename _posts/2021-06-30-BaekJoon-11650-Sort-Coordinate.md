---
layout: post
title: "백준 11650 Sort Coordinate"
date: 2021-06-30 18:07:28 -0400
categories: ProblemSolving
tags: [백준, C++, Sort]
comments: true
---

### 1. What I learned
#### &nbsp;&nbsp;&nbsp;&nbsp;a. pair<>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;This is a class that binds two objects together so that they can be treated as one object.   
#### &nbsp;&nbsp;&nbsp;&nbsp;a. Vector vs Array
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The array is faster than the vector, so use the array if possible.   

### 2. Code
```cpp
#include <stdio.h>
#include <algorithm>

using namespace std;

int main(void) {
    int num_of_points, x, y;
    pair<int,int> points[100000];

    scanf("%d", &num_of_points);
    for (int i=0 ; i<num_of_points ; i++) {
        scanf("%d %d", &x, &y);
        points[i] = pair<int,int>(x,y);
    }

    sort(points, points+num_of_points);

    for (int i=0 ; i<num_of_points ; i++) {
        printf("%d %d\n", points[i].first, points[i].second);
    }
    return 0;
}
```

### 3. Result
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Runtime : 60 ms, Memory usage : 1776 KB  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Runtime can be different by a system even if it is a same code.)

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
