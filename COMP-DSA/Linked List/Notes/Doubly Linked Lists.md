RELATED: [[Linked List]]

The Doubly Linked List has two pointers per node: `prev` to the previous node and `next` to the next node. If `prev` is null, it indicates the start of the list.

The only major difference between singly and doubly linked lists is that the doubly linked list has a `prev` pointer, which requires more operations when inserting and deleting nodes.

The visual shows a linked list with three nodes: `ListNode1`, `ListNode2`, and `ListNode3`. To insert `ListNode4`, update the `next` pointer of `ListNode3` and the `prev` pointer of `ListNode4`:

```cpp
tail.next = ListNode4;
ListNode4->prev = tail;
tail = tail->next;
```

### Insertion

Adding a node to a doubly linked list runs in $𝑂(1)$ time, requiring updates to both the `next` and `prev` pointers.
Here is the shortened text:

We have 3 nodes: `ListNode1`, `ListNode2`, `ListNode3`. We want to insert `ListNode4`. We update `ListNode3`'s `next` and `ListNode4`'s `prev`. The pseudocode and visuals demonstrate this step-by-step.

```cpp
tail.next = ListNode4;
ListNode4->prev = tail;
tail = tail->next;
```

![](https://imagedelivery.net/CLfkmk9Wzy8_9HRyug4EVA/64a757a6-4dd0-4ea0-2f25-e57b2cab0c00/sharpen=1)

![](https://imagedelivery.net/CLfkmk9Wzy8_9HRyug4EVA/dc183286-3867-4dbf-4dee-e6f71854c900/sharpen=1)

### Deletion

Going back to the example with the three nodes, deleting is also a $𝑂(1)$ operation. There is no shifting or traversal required. Instead, in this case adjusting the `prev` pointer is required. The following pseudocode and visual demonstrate this.

```cpp
ListNode2 = tail->prev;
ListNode2->next = nullptr;
tail = ListNode2;
```

| Operation | Big-O Time Complexity | Notes                                                               |
| --------- | --------------------- | ------------------------------------------------------------------- |
| Access    | $𝑂(𝑛)$              |                                                                     |
| Search    | $𝑂(𝑛)$              |                                                                     |
| Insertion | $𝑂(1)*$              | Assuming you have the reference to the node at the desired position |
|  Deletion | $𝑂(1)*$              | Assuming you have the reference to the node at the desired position |
