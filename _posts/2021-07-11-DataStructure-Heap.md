---
layout: post
title: "Heap"
date: 2021-07-11 22:15:28 -0400
categories: [Data Structure]
tags: [DataStructure, C++, Heap]
comments: true
---

## 1. Description
**What is Binary Search Tree?**  
"Heap" is a type of complete binary tree and is a data structure that always has a large-scale relation between parent and child nodes. If the parent node is always larger than the child node, then it is called Max Heap, and vice versa, it is called Min Heap. Only the relationship between parent and child nodes is important, and the relationship with sibling nodes is irrelevant. Because of the large-scale relation between parents and children, the root, which is the top parent, always has the largest or smallest value, which can be used to implement Priority Queue.  
**What I learned?**  
1 Trinomial operator  
result = (A>B)? A : B -> If A is greater than B, A is assigned to result, and vice versa, B is assigned to result  
2 Initializing and using Vector  
vector<int> v(5,2): Declare and initialize vectors v with five 2s as elements  
v.size(): Returns the size of vector v  
v.pop_back(): pop the last element of vector v  

## 2. Code
```cpp
#include <iostream>
#include <vector>
#include <array>

using namespace std;

class Heap {
private:
    vector<int> heap;
    int parent;
    int child;
public:
    Heap() {
        heap.assign(1,0);
    }

    void pushValue(int val) {
        heap.push_back(val);
        child = heap.size()-1;
        parent = child/2;
        while(heap[parent] < heap[child]) {
            heap[0] = heap[child];
            heap[child] = heap[parent];
            heap[parent] = heap[0];
            child = parent;
            parent = child/2;
        }
    }

    void printValues() {
        for (int i=1 ; i<heap.size() ; i++) {
            cout << heap[i] << ' ';
        }
        cout << endl;
    }

    int popValue() {
        int ret_val = heap[1];
        int child2, bigger;
        heap[1] = heap[heap.size()-1];
        heap.pop_back();
        parent = 1;
        while(parent < heap.size()) {
            child = parent*2;
            child2 = parent*2+1;
            cout << child << ' ' << child2 << endl;
            bigger = (heap[child] > heap[child2])? child : child2;
            if (heap[parent] < heap[bigger]) {
                heap[0] = heap[bigger];
                heap[bigger] = heap[parent];
                heap[parent] = heap[0];
            }
            parent = bigger;
        }
        return ret_val;
    }
};

int main(void) {
    array<int,10> values = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
    Heap heap;
    for (int i=0 ; i<values.size() ; i++) {
        heap.pushValue(values[i]);
    }
    heap.printValues();

    cout << heap.popValue() << " Erased" << endl;
    heap.printValues();

    return 0;
}
```

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]:   https://github.com/dlgur1994/Algorithms/tree/master/DataStructure
