---
layout: post
title: "Stack"
date: 2021-07-03 14:56:28 -0400
categories: DataStructure
tags: [DataStructure, C++, Stack]
comments: true
---

## 1. Descriptions
### &nbsp;&nbsp;&nbsp;&nbsp;What is Linked List?  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **Selection Sort** "Stack" is a LIFO data structure that builds data step by step from the bottom.   

## 2. Code
```cpp
#include <iostream>
#include <array>

using namespace std;

class Stack {
private:
    // because a variable is declared private, it should be initialized through the constructor.
    int top, maxsize;
    int * stack;
public:
    // the size of the array is dynamically allocated when it is executed using a constructor.
    Stack(int size) {
        top = -1;
        maxsize = size;
        stack = new int[maxsize]; // dynamic allocation with the pointer
    }

    bool isEmpty() {
        if (top == -1){ return true; }
        else { return false; }
    }

    bool isFull() {
        if (top == maxsize-1) { return true; }
        else { return false; }
    }

    void push(int val) {
        if (isFull()) {
            cout << "Full" << endl;
            return;
        }
        else { stack[++top] = val; }
    }

    int pop() {
        return stack[top--];
    }
    
    void searchVal(int val) {
        for (int i=0 ; i<top ; i++) {
            if (stack[i] == val) {
                cout << "index: " << i << endl;
                return;
            }
        }
        cout << "Not found" << endl;
    }

    void printVal() {
        for (int i=0 ; i<top+1 ; i++) {
            cout << stack[i] << ' ';
        }
        cout << endl;
    }
};

int main(void) {
    array <int,5> values = {1,2,3,4,5}; // use the array container provided by c++
    Stack stack(values.size());

    for (int i=0 ; i<values.size() ; i++) {
        stack.push(values[i]);
    }

    cout << stack.isEmpty() << endl;
    cout << stack.isFull() << endl;
    stack.printVal();
    cout << stack.pop() << endl;
    stack.searchVal(2);
    stack.searchVal(6);
    cout << stack.isEmpty() << endl;
    cout << stack.isFull() << endl;

    return 0;
}
```

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.

[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms/DataStructure
