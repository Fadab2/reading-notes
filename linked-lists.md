# Linked Lists


# Big O: Analysis of Algorithm Efficiency
* Big O is a method used to describe how efficient an algorithm is using running time and memory space consumed by that algorithm.
* Big O describes the worse scenario assuming the element we searching is the last element etc.
* Input size, units of measurement, orders of growth and (best case, worse case, average case) are used to analyze the Big O.
    * Input Size: is the size of parameters values read by the function.
    * Unit of Measurement: The time in milliseconds, number of operations and number of basic operations are used to measure the Big O.
    * for space complexity measurement, space needed to hold the code for the algorithm, the space needed to hold the input, the space needed to hold the output and the working space are used.
     
## Orders of Growth

* Orders of growth is describes the increase in running time and memory space.
* Using the input size we can measure the space and time required and how does it grow when the input grows.
![Orders of grows](/orders-of-grows.png)

* `Constant Complexity` means the algorithm will always have the same time and space of `O(1)` regardless of the size of input.
`Logarithmic Complexity` as the input increases the complexity growth doesn't grow as fast as the input. Example, binary search.
* `Linear Complexity` complexity directly affected by the input size.

# What is a Linked List
* Linked list is a data structure containing a series of nodes that are connected to each other.
* Each node links to the next node.
* There are `Singly Linked` list (referencing next node) and `Doubly Linked` list (referencing both next and previous node)
* Each node has a `data` and a `next` property pointing to the next node or to a `null`
* `Head` is a Node type referencing to the first node.
* `Current` is a Node type referencing the current node.
* We use a `while` loop to traverse a linked list. We are cannot use `foreach` or a `for` loop to traverse linked list.
* The `next` property allows us to move from one node to the next.
Example of checking for a specific value in a linked list:
```
ALGORITHM Includes (value)
// INPUT <-- integer value
// OUTPUT <-- boolean

  Current <-- Head

  WHILE Current is not NULL
    IF Current.Value is equal to value
      return TRUE

    Current <-- Current.Next

  return FALSE
  ```
* while traversing a linking list we always move our current to current.next until we either find what we looking for or reach the end of the linked list.
* Because we might visit every node, the time Big O is O(n) and space is O(1)
* When adding or removing nodes, the order of operations is important because we can lose connection to nodes. Eg assign a new node to point to the next node before making the previous node point to the new node.
* In order to insert a node somewhere in the middle we have to traverse the nodes and check for the value that we want to insert after/before it.



## References:

[Big O: Analysis of Algorithm Efficiency](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-05/resources/big_oh.html)


[Linked Lists What is a Linked List](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-05/resources/singly_linked_list.html) 

 <br /> <br /> 
## [<-- Back](README.md) 
