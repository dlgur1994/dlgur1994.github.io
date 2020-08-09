---
title: "Data Structure Recursion Hanoi.py"
date: 2020-08-09 22:27:28 -0400
categories: DataStructure
---

## 1. Descriptions
### &nbsp;&nbsp;&nbsp;&nbsp;a. Hanoi Tower?  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The Tower of Hanoi (also called the Tower of Brahma or Lucas' Tower and sometimes pluralized as Towers) is a mathematical game or puzzle. It consists of three rods and a number of disks of different sizes, which can slide onto any rod. The puzzle starts with the disks in a neat stack in ascending order of size on one rod, the smallest at the top, thus making a conical shape. The objective of the puzzle is to move the entire stack to another rod, obeying the following simple rules.

### &nbsp;&nbsp;&nbsp;&nbsp;b. Rules?  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1. Only one disk can be moved at a time.  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;2. No disk can be placed on top of the smaller disk.  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;3. Each move consists of taking the upper disk from one of the stacks and placing it on top of another stack or on an empty rod.

## 2. How I sloved
&nbsp;&nbsp;&nbsp;&nbsp; Whatever happens, eventually I have to move the blocks from the left bar to the right bar. Therefore, the blocks (total blocks-1) are moved to the middle bar, the bottom block is moved to the right bar, and the blocks from the middle bar are moved to the right bar. I used a recursive to divide the number of blocks into one and more.

## 3. Code
```python
def hanoitower(numOfBlock,a,b,c):
    if (numOfBlock==1):
        return blockList.append([a,c])
    else:
        hanoitower(numOfBlock-1,a,c,b)
        blockList.append([a,c])
        hanoitower(numOfBlock-1,b,a,c)
    return blockList

input = int(input())
blockList = []
result = hanoitower(input,1,2,3)
print(len(result))
print(result)
```

#### Check out the [my GitHub repo][hyuk-gh] for more info on the code. If you have questions, you can leave a reply on this post.

[hyuk-gh]:   https://github.com/dlgur1994/StudyAlgorithms/DataStructure
