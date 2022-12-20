# DSA Introduction
- Day −∞ to 0: Stick to a programming language like C or C++. Make sure that you are comfortable with pointers/objects.  

- Day 1: Understand the concept of [Algorithmic complexity](https://en.wikipedia.org/wiki/Algorithmic_complexity "en.wikipedia.org"). Skip the theory for now, but for every piece of code you write, you should be able to derive both time and space complexity.

- Day 2 - 10: Let’s start with some simple data structures,
1.  Arrays
2.  Linked Lists
3.  Strings
4.  Stacks
5.  Queues

Understand their basic operations (insert, delete, search, traversal) and their complexity - [Big-O Algorithm Complexity Cheat Sheet](http://bigocheatsheet.com/ "bigocheatsheet.com"), and code them all.

- Day 11 - 25: Let’s now learn some simple algorithms,
1.  Sorting - [Insertion sort](https://en.wikipedia.org/wiki/Insertion_sort "en.wikipedia.org"), [Merge sort](https://en.wikipedia.org/wiki/Merge_sort "en.wikipedia.org"), [Quick sort](https://en.wikipedia.org/wiki/Quicksort "en.wikipedia.org"), [Heap sort](https://en.wikipedia.org/wiki/Heapsort "en.wikipedia.org"), [Bucket sort](https://en.wikipedia.org/wiki/Bucket_sort "en.wikipedia.org"), [Counting sort](https://en.wikipedia.org/wiki/Counting_sort "en.wikipedia.org"), [Radix sort](https://en.wikipedia.org/wiki/Radix_sort "en.wikipedia.org"), [External sorting](https://en.wikipedia.org/wiki/External_sorting "en.wikipedia.org")
2. Search - [Linear search](https://en.wikipedia.org/wiki/Linear_search "en.wikipedia.org"), [Binary Search](https://www.topcoder.com/community/data-science/data-science-tutorials/binary-search/ "www.topcoder.com")-   (along with its variants). 
3. Prime Numbers - [Sieve of Eratosthenes](https://en.wikipedia.org/wiki/Sieve_of_Eratosthenes "en.wikipedia.org"), [Primality test](https://en.wikipedia.org/wiki/Primality_test "en.wikipedia.org")Strings - [String searching](https://en.wikipedia.org/wiki/String_searching_algorithm "en.wikipedia.org"), [LCS](https://en.wikipedia.org/wiki/Longest_common_subsequence_problem "en.wikipedia.org"), [Palindrome detection](https://www.rosettacode.org/wiki/Palindrome_detection "www.rosettacode.org")
4. Miscellaneous - [Euclidean algorithm](https://en.wikipedia.org/wiki/Euclidean_algorithm "en.wikipedia.org"), [Matrix multiplication](https://en.wikipedia.org/wiki/Matrix_multiplication "en.wikipedia.org"), [Fibonacci Numbers](https://en.wikibooks.org/wiki/Algorithm_Implementation/Mathematics/Fibonacci_Number_Program "en.wikibooks.org", [Pascal's Triangle](http://www.geeksforgeeks.org/pascal-triangle/ "www.geeksforgeeks.org"), [Max Subarray problem](https://en.wikipedia.org/wiki/Maximum_subarray_problem "en.wikipedia.org")

- Day 26 - 50: Once you are comfortable with everything above, start doing problems from,
1.  [Cracking the Coding Interview](https://www.amazon.com/Cracking-Coding-Interview-Programming-Questions/dp/0984782850 "www.amazon.com")
2. [Elements of Programming Interviews](https://www.amazon.com/Elements-Programming-Interviews-Insiders-Guide/dp/1479274836 "www.amazon.com")
3.  [Programming Interviews Exposed: Secrets to Landing Your Next Job](https://www.amazon.com/Programming-Interviews-Exposed-Secrets-Landing/dp/1118261364 "www.amazon.com")
4. [GeeksforGeeks](http://www.practice.geeksforgeeks.org/ "www.practice.geeksforgeeks.org")
5. [HackerRank](https://www.hackerrank.com/ "www.hackerrank.com")
6. [InterviewBit](https://www.interviewbit.com/invite/afaf "www.interviewbit.com")

Stick to chapters of arrays, linked lists, strings, stacks, queues and complexity.

- Day 51 - 60: Let’s learn some non-linear data structures,

1. Tree
	a. Binary Tree, Binary Search Tree - [Tree traversals](https://en.wikipedia.org/wiki/Tree_traversal "en.wikipedia.org"), [Lowest common ancestor](https://en.wikipedia.org/wiki/Lowest_common_ancestor "en.wikipedia.org"), [Depth, Height & Diameter](http://stackoverflow.com/questions/2603692/what-is-the-difference-between-tree-depth-and-height "stackoverflow.com"), [Finding k-th smallest element](http://www.geeksforgeeks.org/find-k-th-smallest-element-in-bst-order-statistics-in-bst/ "www.geeksforgeeks.org")
	b. Heaps

2. Hash table - [4 sum problem](http://www.sigmainfy.com/blog/4sum-problem-analysis-different-time-complexity.html "www.sigmainfy.com"), [Checking if sudoku solution is valid](http://stackoverflow.com/questions/5484629/check-if-sudoku-solution-is-valid "stackoverflow.com")
3. Graph - [Breadth-first search](https://en.wikipedia.org/wiki/Breadth-first_search "en.wikipedia.org"), [Depth-first search](https://en.wikipedia.org/wiki/Depth-first_search "en.wikipedia.org"), [Topological sorting](https://en.wikipedia.org/wiki/Topological_sorting "en.wikipedia.org"), [Minimum spanning tree](https://en.wikipedia.org/wiki/Minimum_spanning_tree "en.wikipedia.org"), [Shortest path problem](https://en.wikipedia.org/wiki/Shortest_path_problem "en.wikipedia.org")

- Day 61- 90: Refer to the previous resources and start doing problems from trees, hash tables, heaps and graphs.

- Day 91 - 100: Understand [Computational complexity theory](https://en.wikipedia.org/wiki/Computational_complexity_theory "en.wikipedia.org") and [NP-completeness](https://en.wikipedia.org/wiki/NP-completeness "en.wikipedia.org"), [Knapsack problem](https://en.wikipedia.org/wiki/Knapsack_problem "en.wikipedia.org"), [Travelling salesman problem](https://en.wikipedia.org/wiki/Travelling_salesman_problem "en.wikipedia.org"), [SAT problem](https://en.wikipedia.org/wiki/Boolean_satisfiability_problem "en.wikipedia.org") and so on.

Day 101 - ∞ You are now better than most of the CS undergrads. Keep revising the above topics and start competitive programming! Good luck!

## Time and Space Complexity
There are many ways to solve a problem, it is highly required to use a method to compare the solution in order to judge which is  more optimal. The method must be:

- Independent of the machine and its configuration, one which the algorithm is running on. 
- Shows a direct correlation with the number of inputs
- Can distinguish two algorithms clearly without ambiguity.
  
  There are two methods used, **time complexity** and **space complexity**

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
3. **Queue** => This works with FIFO principle, unlike the stack which is LIFO, the first element stored in the queue will be removed first. In programming terms, putting items in the queue is called **enqueue**, and removing items from the queue is called **dequeue**.
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

