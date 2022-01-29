# Trees
## Common Terminology;
* Node - A Tree node is a component which may contain its own values, and references to other nodes
* Root - The root is the node at the beginning of the tree
* K - A number that specifies the maximum number of children any node may have in a k-ary tree. In a binary tree, k = 2.
* Left - A reference to one child node, in a binary tree
* Right - A reference to the other child node, in a binary tree
* Edge - The edge in a tree is the link between a parent and child node
* Leaf - A leaf is a node that does not have any children
* Height - The height of a tree is the number of edges from the root to the furthest leaf

### Traversals
* We traverse trees to search for nodes and print the values.

### Depth First travesal
* Going through the height of the tree is prioritize.
* Pre-order: root >> left >> right
 ```
    ALGORITHM preOrder(root)

  OUTPUT <-- root.value

  if root.left is not NULL
      preOrder(root.left)

  if root.right is not NULL
      preOrder(root.right)
      
```

* In-order: left >> root >> right
```
    ALGORITHM inOrder(root)
// INPUT <-- root node
// OUTPUT <-- in-order output of tree node's values

    if root.left is not NULL
        inOrder(root.left)

    OUTPUT <-- root.value

    if root.right is not NULL
        inOrder(root.right)

```

* Post-order: left >> right >> root
```
ALGORITHM postOrder(root)
// INPUT <-- root node
// OUTPUT <-- post-order output of tree node's values

    if root.left is not NULL
        postOrder(root.left)

    if root.right is not NULL
        postOrder(root.right)

    OUTPUT <-- root.value

```

### Breadth First
* Breadth first traversal uses a queque to iterates through the tree by going through each level of the tree node-by-node.
```
ALGORITHM breadthFirst(root)
// INPUT  <-- root node
// OUTPUT <-- front node of queue to console

  Queue breadth <-- new Queue()
  breadth.enqueue(root)

  while ! breadth.is_empty()
    node front = breadth.dequeue()
    OUTPUT <-- front.value

    if front.left is not NULL
      breadth.enqueue(front.left)

    if front.right is not NULL
      breadth.enqueue(front.right)

```
### Binary Tree Vs K-ary Trees
* Binary trees have 2 children max per node.
* K-ary tree, nodes can have more the two children. K refers to the maximum number a node can have.

* Traversing K-ary tree we still use the Breadth First Traversal, but we check a number of k children rather than left and right child.
```
ALGORITHM breadthFirst(root)
// INPUT  <-- root node
// OUTPUT <-- front node of queue to console

  Queue breadth <-- new Queue()
  breadth.enqueue(root)

  while ! breadth.is_empty()
    node front = breadth.dequeue()
    OUTPUT <-- front.value

    for child in front.children
        breadth.enqueue(child)
 ```
### Binary Search Trees
* In BST nodes are organized in a way that nodes that are greater than the root are stored to right and nodes with values less than the root to the left of that root.
* Searching BST is easy because we can search either left or right depending on the value compared to the node we are at.

### Big O
* Insertion/search: O(height)
* Space: O(1) as we are not allocating any new space.

 <br />

## References:

[Trees](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/Trees.html)

<br />

## [<-- Back](README.md)