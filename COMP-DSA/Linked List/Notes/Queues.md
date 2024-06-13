RELATED: [[Linked List]]

Queues are similar to stacks, except they follow what is called a **FIFO** approach (First in First Out).

The most common implementation of a queue is using a Linked List.

Only two operations in Queues:
 - `enqueue`
 - `dequeue`

> A queue is an abstract interface, it can implemented using various data structures, as long as they support enqueue and dequeue operations.

### Enqueue

The enqueue operation adds elements to the `tail` of the queue until the size of the queue is reached. Since adding to the end of the queue requires no shifting of the elements, this operation runs in 𝑂(1).

```c++
void enqueue(int val) {
    ListNode* newNode = new ListNode(val);
    
    // Queue is non-empty
    if (right != nullptr) {
        right->next = newNode;
        right = right->next;
    } 
    // Queue 
    else {
        left = right = newNode;
    }
}
```

![[Pasted image 20240613165935.png]]

### Dequeue

The dequeue operation removes and returns elements from the front of the queue. The pseudocode and visual demonstrate this.

```cpp
int dequeue() {
    // Queue is empty
    if (left == nullptr) {
        return -1; // Better to throw an exception
    }
    // Remove left node and return value
    int val = left->val_;
    left = left->next;
    if (!left) {
        right = nullptr;
    }
    return val;
}
```

![[Pasted image 20240613170434.png]]

> There is also a variation of the queue, a double-ended queue, called **deque** (pronounced "deck"). Deque allows you to add and remove elements from both the head and the tail.

## Big-O

| Operation | Big-O Time Complexity |
| --------- | --------------------- |
| Enqueue   | 𝑂(1)                 |
| Dequeue   | 𝑂(1)                 |
