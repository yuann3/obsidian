RELATED: [[Linked List]]

Queues are similar to stacks, except they follow what is called a **<mark style="background: #FFF3A3A6;">FIFO</mark>** (First in First Out) approach.

The most common implementation of a queue is using a Linked List.

Only two operations in Queues:
 - `enqueue`
 - `dequeue`

> A queue is an abstract interface, it can implemented using various data structures, as long as they support enqueue and dequeue operations.

### Enqueue

The enqueue operation adds elements to the `tail` of the queue until the size of the queue is reached. Since adding to the end of the queue requires no shifting of the elements, this operation runs in $𝑂(1)$.

```c++
class Queue {
public:
	Queue() : head(nullptr), tail(nullptr) {}
	
	void enqueue(int value) {
	    // Create a new node with the given value
	    Node* new_node = new Node(value);
	    
	    // Check if the queue is empty (tail is nullptr)
	    if (tail == nullptr)
	        // If the queue is empty, 
	        // both head and tail should point to the new node
	        head = tail = new_node;
	    else {
	        // If the queue is not empty,
	        // link the new node to the end of the queue
	        tail->next = new_node;
	        // Update the tail to point to the new node
	        tail = new_node;
	    }
    }
};
```

![[Pasted image 20240613165935.png]]

### Dequeue

The dequeue operation removes and returns elements from the front of the queue. The pseudocode and visual demonstrate this.

```cpp
class Queue {
public:
	Queue() : head(nullptr), tail(nullptr) {}
	
	int dequeue() {
		// check if the queue is empty
	    if (head == nullptr) 
		    return -1; // return this if queue is empty
		
		// Store the current head node in a temporary pointer
		Node *temp = head;
		// Store the value of the current head node
		int value = temp->data;
		// Update the head to point to the next node
		head = head->next;
		
		// If the queue becomes empty, update the tail as well
		if (head == nullptr)
			tail = nullptr;
		
		// Delete the old head node to free memeory
		delete temp;
		
		// Return the value of the dequeued node
		return value;
	}
};
```

![[Pasted image 20240613170434.png]]

> There is also a variation of the queue, a double-ended queue, called **deque** (pronounced "deck"). Deque allows you to add and remove elements from both the head and the tail.

## Big-O

| Operation | Big-O Time Complexity |
| --------- | --------------------- |
| Enqueue   | $𝑂(1)$               |
| Dequeue   | $𝑂(1)$               |
