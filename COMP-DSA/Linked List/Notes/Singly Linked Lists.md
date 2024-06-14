RELATED: [[Linked List]]

A linked list is a data structure that stores elements in an ordered sequence, similar to an array, but with key differences.

Linked lists are composed of `ListNode` objects, each with two attributes:
1. `value`: Stores the node's value, which can be any data type.
2. `next`: Holds a reference to the next node in the list.

## Creating a Linked List from scratch

Chaining `ListNode` objects creates a linked list. Here's how to define a `ListNode` class in pseudocode:

```cpp
struct Node { 
	int data; 
	Node* next; 
	
	Node(int value) : data(value), next(nullptr) {} 
};
```

## Sample Code

```c++
#include <iostream>

// Node structure
struct Node {
    int data;
    Node* next;

    Node(int data) : data(data), next(NULL) {}
};

// Linked List class
class LinkedList {
private:
    Node* head;

public:
    LinkedList() : head(NULL) {}

    // Function to add a node at the end
    void append(int data) {
        Node* newNode = new Node(data);
        if (head == NULL) {
            head = newNode;
        } else {
            Node* temp = head;
            while (temp->next != NULL) {
                temp = temp->next;
            }
            temp->next = newNode;
        }
    }

    // Function to display the list
    void display() {
        Node* temp = head;
        while (temp != NULL) {
            std::cout << temp->data << " ";
            temp = temp->next;
        }
        std::cout << std::endl;
    }

    // Destructor to free memory
    ~LinkedList() {
        Node* temp = head;
        while (temp != NULL) {
            Node* next = temp->next;
            delete temp;
            temp = next;
        }
    }
};

int main() {
    LinkedList list;
    list.append(10);
    list.append(20);
    list.append(30);

    list.display(); // Output: 10 20 30

    return 0;
}

```

## Big-O

| Operation | Big-O Time Complexity | Note                                                                |
| --------- | --------------------- | ------------------------------------------------------------------- |
| Access    | 𝑂(𝑛)                |                                                                     |
| Search    | 𝑂(𝑛)                |                                                                     |
| Insertion | 𝑂(1)                 | Assuming you have the reference to the node at the desired position |
| Deletion  | 𝑂(1)                 | Assuming you have the reference to the node at the desired position |