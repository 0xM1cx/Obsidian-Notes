# DSA Introduction

## What is an Algorithm?
In computer programming, an **algorithm** is a set of well-defined instructions to solve a particular problem. It takes a set of input and produces a desired output. For example,

An algorithm to add two numbers:
1. Take two number inputs
2. Add numbers using the + operator
3. Display result

### Qualities of a Good Algorithm
- Input and output should be defined precisely.
- Each step in the algorithm should be clear and unambiguous.
- Algorithms should be most effective among many different ways to solve a problem.
- An algorithm shouldn't include computer code. Instead, the algorithm should be written in such a way that it can be used in different programming languages.  

## Data Structures and Types
### What are Data Structures?
**Data Structure** is a storage that is used to store and organize data. It is a way of arranging data on a computer so that it can be accessed and updated efficiently.

Depending on your requirement and project, it is important to choose the right data structure for your project. For example, if you want to store data sequentially in the memory, then you can go for the Array data structure.

![[Pasted image 20220524093406.png]]
### Types of data Structures
Data structures are divided into two categories:
1. Linear Data Structure
2. Non-Linear Data Structure

#### Linear Data Structure
In this structure, elements are arranged in sequence one after the other. Since elements are arranged in particular order, the are easy to implement.

However, when complexity of the program increases, the linear data structures might not be the best choice because of operational complexities.

##### Popular Data Structures are:
1. **Arrays** => is a container, which can hold a fix number of items and these items should be of the same type. The elements in this array are arranged in continuous memory. And, the type of elements that can be stored in the form of arrays is determined by the programming language.![[Pasted image 20220524094229.png]]
2. **Stack** => In this structure, elements are stored in the LIFO principle. The last element stored in the stack will be the first one removed or the first element stored will be the last removed.
![[Pasted image 20220524094218.png]]
3. **Queue** => This works with FIFO principle, unlike the stack which is LIFO, the first element stored in the queue will be removed first.
![[Pasted image 20220524112000.png]]
 4. **Linked List** => In linked list data structures, data elements are connected through a series of nodes. And, each node contains the data items and address to the next node.
 ![[Pasted image 20220524112705.png]]
 
#### Non Linear Data Structures
Unlike linear data structures, elements in non-linear data structures are not in any sequence. Instead they are arranged in a hierarchical manner where one element will be connected to one or more elements.

Non-linear data structures are further divided into graph and tree based data structures.

1. **Graph Data Structure** => In this graph each node is called ***vertex*** and each vertex is connected to other vertices through edges.
![[Pasted image 20220524113724.png]]
**Popular Graph Based Data structures**
-   [Spanning Tree and Minimum Spanning Tree](https://www.programiz.com/dsa/spanning-tree-and-minimum-spanning-tree)
-   [Strongly Connected Components](https://www.programiz.com/dsa/strongly-connected-components)
-   [Adjacency Matrix](https://www.programiz.com/dsa/graph-adjacency-matrix)
-   [Adjacency List](https://www.programiz.com/dsa/graph-adjacency-list)

2. **Trees Data Structure** => Similar to graph, a tree is a collection of vertices and edges. However, in tree data structure, there can only be one edge between two vertices. ![[Pasted image 20220524114435.png]]
**Popular Tree based Data Structure**
-   [Binary Tree](https://www.programiz.com/dsa/binary-tree)
-   [Binary Search Tree](https://www.programiz.com/dsa/binary-search-tree)
-   [AVL Tree](https://www.programiz.com/dsa/avl-tree)
-   [B-Tree](https://www.programiz.com/dsa/b-tree)
-   [B+ Tree](https://www.programiz.com/dsa/b-plus-tree)
-   [Red-Black Tree](https://www.programiz.com/dsa/red-black-tree)
---

### Linear Vs Non-linear Data Structures
Now that we know about linear and non-linear data structures, let's see the major differences between them.
| **Linear Data Structures** | **Non Linear Data Structures** |
| --- | --- |
| The data items are arranged in sequential order, one after the other | The data items are arranged in non-sequential order(hierarchical manner). |
| All the items are present on the single layer | The data items are present at different layers |
| It can be traversed on a single run. That is, if we started from the first element, we can traverse all the elements sequentially in a single pass. | It requires multiple runs. That is, if we start from the first element it might not be possible to traverse all the elements in a single pass. |
| The memory utilization is not efficient | Different structures utilize memory in different efficient ways depending on the need. |
| The time complexity increase with the data size | Time complexity remains the same. |
| **Example**: Arrays, Stack, Queue | **Example**: Tree, Graph, Map |
> Knowledge about data structures help you understand the working of each data structure. And, based on that you can select the right data structures for you project.
> 
> This helps you write memory and time efficient code.

