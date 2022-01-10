# Stacks and Queues

## What is a Stack
* A stack is a data structure that consists of Nodes. Each Node references the next Node in the stack, but does not reference its previous.
* Push - Nodes or items that are put into the stack are pushed
* Pop - Nodes or items that are removed from the stack are popped. When you attempt to pop an empty stack an exception will be raised.
* Top - This is the top of the stack.
* Peek - When you peek you will view the value of the top Node in the stack. When you attempt to peek an empty stack an exception will be raised.
* IsEmpty - returns true when stack is empty otherwise returns false
* FILO: First In Last Out
* LIFO: Last In First Out
* When we remove an item it is always the top item and next item is set to top and so on until the last item is removed.
* The Big O for `push, pop, peek, isEmpty, Dequeue`, etc is O(1)
* We push a node into a stack by setting its next node to the current top.
```
ALOGORITHM push(value)
// INPUT <-- value to add, wrapped in Node internally
// OUTPUT <-- none
   node = new Node(value)
   node.next <-- Top
   top <-- Node
   ```
* `pop()` removes a node from the top and the node below will become the top.
* `isEmpty()` should be used before `pop()`
```
ALGORITHM pop()
// INPUT <-- No input
// OUTPUT <-- value of top Node in stack
// EXCEPTION if stack is empty

   Node temp <-- top
   top <-- top.next
   temp.next <-- null
   return temp.value
   ```
* `peek()` returns the top node. We check the stack/queue is not empty first.

## What is a Queue
* Enqueue - Nodes or items that are added to the queue.
* Dequeue - Nodes or items that are removed from the queue. If called when the queue is empty an exception will be raised.
* Front - This is the front/first Node of the queue.
* Rear - This is the rear/last Node of the queue.
* Peek - When you peek you will view the value of the front Node in the queue. If called when the queue is empty an exception will be raised.
* IsEmpty - returns true when queue is empty otherwise returns false.
* FIFO: First In First Out (first node in is first out)
*  LILO: Last In Last Out (Last node in is last out)
* `enqueue()` is used to add an item to a queue.
* `rear` is a reference to the last node
```
ALGORITHM enqueue(value)
// INPUT <-- value to add to queue (will be wrapped in Node internally)
// OUTPUT <-- none
   node = new Node(value)
   rear.next <-- node
   rear <-- node

   ```
* `Dequeue()` is used to remove the front node of the queue. We should check the queue is not empty at first.
```
ALGORITHM dequeue()
// INPUT <-- none
// OUTPUT <-- value of the removed Node
// EXCEPTION if queue is empty

   Node temp <-- front
   front <-- front.next
   temp.next <-- null

   return temp.value
  
   ```
* `peek()` used to inspect the front node.
```
ALGORITHM peek()
// INPUT <-- none
// OUTPUT <-- value of the front Node in Queue
// EXCEPTION if Queue is empty

   return front.value

```

<br /> 
## References:

[Stacks and Queues](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-10/resources/stacks_and_queues.html)



 <br /> <br /> 
## [<-- Back](README.md) 