---
title: "Selection Sort"
categories: Algorithm Sort
date: 2021-07-01 11:52:28 -0400
comments: true
---

## 1. Descriptions
### &nbsp;&nbsp;&nbsp;&nbsp;What is Selection Sort?  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **Selection Sort** sorts the arrays by continuing to send the smallest number forward in an unaligned array. It takes the smallest number from beginning to end of the array to the front of the array, and repeats to the end of the array, sending the smallest number of arrays to the front except aligned elements.   

## 2. Code
```cpp
#include <stdio.h>

int main(void) {
    int arr[10] = {1, 10, 5, 8, 7, 6, 4, 3, 2, 9};
    int min, id, temp;

    for (int i=0 ; i<9 ; i++) {
        min = 11;
        for (int j=i ; j<10 ; j++) {
            if (arr[j] < min) {
                min = arr[j];
                id = j;
            }
        }
        temp = arr[i];
        arr[i] = arr[id];
        arr[id] = temp;
    }

    for (int i=0 ; i<10 ; i++) {
        printf("%d\n", arr[i]);
    }
    return 0;
}
```

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.

[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms/DataStructure
