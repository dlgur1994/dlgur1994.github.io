---
title: "Merge Sort"
categories: DataStructures Python MergeSort
date: 2021-03-03 23:47:28 -0400
comments: true
---

### 1. What I learned
#### &nbsp;&nbsp;&nbsp;&nbsp;Merge Sort
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Merge Sort is cut until all elements of the array are one, and then compared one by one to create an array. This uses the concept of recursion.   

### 2. Code
```python
def mergeSort(vals):
    l = len(vals)
    # Continue to separate the list until there's only one element.
    if l == 1:
        return vals
    vals1 = vals[:l//2]
    vals2 = vals[l//2:]
    vals1 = mergeSort(vals1)
    vals2 = mergeSort(vals2)

    id1, id2 = 0, 0
    for i in range(l): # Compare the elements of vals1 with the elements of vals2 and make a list in small order
        if id1 == len(vals1):
            vals[i] = vals2[id2]
            id2 += 1
        elif id2 == len(vals2):
            vals[i] = vals1[id1]
            id1 += 1
        elif vals1[id1] > vals2[id2]:
            vals[i] = vals2[id2]
            id2 += 1
        else:
            vals[i] = vals1[id1]
            id1 += 1
    return vals
```

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.
[hyuk-gh]: https://github.com/dlgur1994/StudyAlgorithms
