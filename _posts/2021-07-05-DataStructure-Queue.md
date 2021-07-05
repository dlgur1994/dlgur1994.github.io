---
title: "Queue"
categories: DataStructure
tags: [DataStructure, Queue]
date: 2021-07-05 22:31:28 -0400
comments: true
---

## 1. Descriptions
### &nbsp;&nbsp;&nbsp;&nbsp;What is Linked List?  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **Selection Sort** "Queue" is a FIFO data structure that follows a particular order.   

## 2. Code
```cpp
#include <iostream>
#include <array>

using namespace std;

struct Node {
    int data;
    Node * next;
};

class Queue {
private:
    Node * head;
    Node * tail;
    Node * node;
    Node * cur;
    int pop_val;

public:
    Queue() {
        head = NULL;
        tail = NULL;
    }

    void push(int val) {
        node = new Node();
        node->data = val;
        node->next = NULL;
        if (head==NULL && tail==NULL) { 
            head = node; 
            tail = node;
        }
        else {
            tail->next = node;
            tail = tail->next;
        }
    }

    int pop() {
        pop_val = head->data;
        cur = head;
        head = head->next;
        delete cur;
        return pop_val;
    }

    void printElement() {
        cur = head;
        while (cur != tail->next) {
            cout << cur->data << ' ';
            cur = cur->next;
        }
        cout << endl;
    }
};

int main(void) {
    array <int,5> values = {1,2,3,4,5};
    Queue queue;

    for (int i=0 ; i<values.size() ; i++) {
        queue.push(values[i]);
    }
    queue.printElement();
    cout << queue.pop() << endl;
    cout << queue.pop() << endl;
    queue.printElement();
    cout << queue.pop() << endl;
    cout << queue.pop() << endl;
    cout << queue.pop() << endl;
    queue.printElement();

    return 0;
}
```

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.

[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms/DataStructure
