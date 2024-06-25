The Binary Tree is a data structure with **nodes** and **pointers**. Each nodes have at most two pointers, called left and right child. The first node is the root. The pointers are drawn downward instead of in a straight line.

The value of a node can be any data type. A `TreeNode` class would look like the following.

```cpp
class TreeNode {
    public:
        int value;
        TreeNode* left = nullptr;
        TreeNode* right = nullptr;

        TreeNode(int val) {
            value = val;
        }
};
```

If a node does not have any children, it is classified as a **leaf** node. If a node has even a single child, either left or right, it would be classified as a **non-leaf** node.

Unlike linked lists, binary tree node pointers can only point in one direction. As such, cycles are not allowed in binary trees. Mathematically speaking, a binary tree is an undirected graph with no cycles. This means that a leaf node is always guaranteed to exist.

> The same applies to the decision trees in recursion.

## Visualization

### Root Node / Leaf Nodes

**Root node** is the highest node in the tree and has no parent node. All of the nodes in the tree can be reached by the root node.

**Leaf nodes** are nodes with no children. The nodes at the last level of the tree are guarenteed to be leaf nodes but they can also be found on other levels.

![[Pasted image 20240625162006.png]]
### Children

The children of a node are its **left** child and **right** child.

![[Pasted image 20240625162959.png]]
