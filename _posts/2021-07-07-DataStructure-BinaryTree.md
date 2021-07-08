---
layout: post
title: "Binary Tree"
date: 2021-07-07 14:50:28 -0400
categories: [Data Structure]
tags: [DataStructure, C++, BinaryTree]
comments: true
---

## 1. Descriptions
### &nbsp;&nbsp;&nbsp;&nbsp;What is Binary Tree?  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; "Binary Tree" is a tree data structure in which each node has up to two child nodes, each of which is referred to as a left child node and a right child node.   

## 2. Code
```cpp
#include <iostream>
#include <array>

using namespace std;

struct Node {
    int data;
    Node * left;
    Node * right;
};

class BinaryTree {
private:
    Node * root;

public:
    BinaryTree() {
        root = NULL;    
    }

    Node * getRoot() {
        return root;
    }

    void addNode(Node * cen_node, Node * left_node, Node * right_node) {
        if (root == NULL) { root = cen_node; }
        cen_node->left = left_node;
        cen_node->right = right_node;
    }

    // center -> left -> right
    void preorder(Node * cur) {
        cout << cur->data << ' ';
        if (cur->left != NULL) { preorder(cur->left); }
        if (cur->right != NULL) { preorder(cur->right); }
    }

    // left -> center -> right
    void inorder(Node * cur) {
        if (cur->left != NULL) { inorder(cur->left); }
        cout << cur->data << ' ';
        if (cur->right != NULL) { inorder(cur->right); }
    }

    // left -> right -> center
    void postorder(Node * cur) {
        if (cur->left != NULL) { postorder(cur->left); }
        if (cur->right != NULL) { postorder(cur->right); }
        cout << cur->data << ' ';
    }
};

int main(void) {
    array<int,9> values = {0, 1, 2, 3, 4, 5, 6, 7, 8};
    array<Node *,9> nodes = {};
    for (int i=0 ; i<values.size() ; i++) {
        Node * new_node = new Node();
        new_node->data = values[i];
        new_node->left = NULL;
        new_node->right = NULL;
        nodes[i] = new_node;
    }

    BinaryTree binarytree;
    for (int i=0 ; i<nodes.size()/2 ; i++) {
        binarytree.addNode(nodes[i], nodes[2*i+1], nodes[2*i+2]);
    }

    binarytree.preorder(binarytree.getRoot());
    cout << endl;
    binarytree.inorder(binarytree.getRoot());
    cout << endl;
    binarytree.postorder(binarytree.getRoot());
    cout << endl;

    return 0;
}
```

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]:   https://github.com/dlgur1994/Algorithms/tree/master/DataStructure
