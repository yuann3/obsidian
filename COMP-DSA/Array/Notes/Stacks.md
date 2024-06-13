A data structure that contains a collection of elements where you can add and delete elements from just one end (called the top of the stack). 

Stacks are a dynamic data structure that operate on a **LIFO** (Last In First Out) manner. The last element placed inside is the first element that comes out. 

The stack supports three operations - `push`, `pop`, `peek`.

## Push

Push operation **adds an element to the top of the stack**, which in dynamic array terms would be appending an element to the end. This is an efficient 𝑂(1) operation as discussed in the previous chapters. It helps to visualise a stack as an array that is vertical. The pseudocode demonstrates the concept, along with the visual where we add numbers from 11 to 44 to the top. The top pointer updates to point at the last item added. The following pseudocode and visual demonstrates this.

```cpp
void push(int n) {
    stack_.push_back(n);
}
```

![[Pasted image 20240613111440.png]]

## Pop

Pop operation removes the last element from top of the stack, which in dynamic array terms would be retrieving the last element. This is also an efficient 𝑂(1) operation as discussed in the previous chapters.

```cpp
int pop() {
    int res = stack_[stack_.size() - 1];
    stack_.pop_back();
    return res;
}
```

![[Pasted image 20240613111611.png]]


## Peek

Peek is the simplest of three. It just returns, without removing, the top most element.

```cpp
int peek(const std::vector<int>& stack) {
    if (stack.empty()) {
        throw std::out_of_range("Stack is empty");
    }
    return stack.back();
}
```

## Big O

| Operation | Big-O Time Complexity | Notes                             |
| --------- | --------------------- | --------------------------------- |
| Push      | 𝑂(1)                 |                                   |
| Pop       | 𝑂(1)                 | Check if the stack is empty first |
| Peek/Top  | 𝑂(1)                 | Retrieves without removing        |
