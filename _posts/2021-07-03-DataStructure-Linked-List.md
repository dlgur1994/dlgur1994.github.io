---
layout: post
title: "Linked List"
date: 2021-07-03 12:00:28 -0400
categories: DataStructure
tags: [DataStructure, C++, LinkedList]
comments: true
---

## 1. Descriptions
### &nbsp;&nbsp;&nbsp;&nbsp;What is Linked List?  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **Selection Sort** "Linked List" is a data structure that stores data and a pointer in a node and uses the pointer from each node to connect to another node, ultimately a long connected data structure. At this point, nodes are dynamically allocated to memory.   

## 2. Code
```cpp
#include <stdio.h>

struct Node {
    int val;
    Node * next;
};

class LinkedList {
private:
    Node * head = NULL;
    Node * tail = NULL;
    Node * cur = NULL;
    Node * ptr = NULL;
    Node * del_node = NULL;
public:
    void addNode(int val) {
        ptr = new Node(); // 'new' keyword provides dynamic allocation like 'malloc' function in C language. And dynamically assigned objects must be pointed out using a pointer.
        ptr->val = val; // '->' is a symbol used by a pointer to access an element.
        ptr->next = NULL;
        if (head == NULL) {
            head = ptr;
        }
        else {
            tail->next = ptr;
        }
        tail = ptr;
    }

    void searchNode(int target) {
        int id = 0;
        bool flag = false;
        cur = head;
        while (cur != tail->next) {
            if (cur->val == target) {
                printf("target index: %d\n", id);
                flag = true;
                break;
            }
            cur = cur->next;
            id++;
        }
        if (flag == false) {
            printf("can't find value\n");
        }
    }

    void deleteNode(int val) {
        cur = head;
        while (cur != tail->next) {
            if (cur->val == val) {
                del_node = cur;
                head = cur->next;
                delete del_node;
                break;
            }
            else if (cur->next->val == val) {
                del_node = cur->next;
                cur->next = cur->next->next;
                delete del_node;
                break;
            }
            cur = cur->next;
        }
    }

    void printNode() {
        cur = head;
        while (cur != tail->next) {
            printf("%d ", cur->val);
            cur = cur->next;
        }
        printf("\n");
    }

};

int main(void) {
    int values[5] = {1, 2, 3, 4, 5};
    LinkedList linked_list;
    
    for (int i=0 ; i<5 ; i++){
        linked_list.addNode(values[i]);
    }

    linked_list.printNode();

    linked_list.searchNode(5);
    linked_list.searchNode(6);
    
    linked_list.deleteNode(1);
    linked_list.printNode();
    linked_list.deleteNode(3);
    linked_list.printNode();
    linked_list.deleteNode(5);
    linked_list.printNode();
    
    return 0;
}
```

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]:   https://github.com/dlgur1994/Algorithms/tree/master/DataStructure
