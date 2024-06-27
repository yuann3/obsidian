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

```cpp
/* Binary tree node */
struct TreeNode {
    int val;          // Node value
    TreeNode *left;   // Pointer to left child node
    TreeNode *right;  // Pointer to right child node
    TreeNode(int x) : val(x), left(nullptr), right(nullptr) {}
};
```

If a node does not have any children, it is classified as a **leaf** node. If a node has even a single child, either left or right, it would be classified as a **non-leaf** node.

Unlike linked lists, binary tree node pointers can only point in one direction. As such, cycles are not allowed in binary trees. Mathematically speaking, a binary tree is an undirected graph with no cycles. This means that a leaf node is always guaranteed to exist.

> The same applies to the decision trees in recursion.

### Initializing a binary tree

Similar to a linked list, begin by initialize nodes, then construct references (pointers

```cpp
/* Initializing a binary tree */
// Initializing nodes
TreeNode* n1 = new TreeNode(1);
TreeNode* n2 = new TreeNode(2);
TreeNode* n3 = new TreeNode(3);
TreeNode* n4 = new TreeNode(4);
TreeNode* n5 = new TreeNode(5);
// Linking references (pointers) between nodes
n1->left = n2;
n1->right = n3;
n2->left = n4;
n2->right = n5;
```

## Visualization

### Root Node / Leaf Nodes

**Root node** is the highest node in the tree and has no parent node. All of the nodes in the tree can be reached by the root node.

**Leaf nodes** are nodes with no children. The nodes at the last level of the tree are guarenteed to be leaf nodes but they can also be found on other levels.

![[Pasted image 20240625162006.png]]

### Children

The children of a node are its **left** child and **right** child.

![[Pasted image 20240625162959.png]]
### Height

The height of a binary tree is measured from the root to the lowest leaf, like the height of anything in real life. The height of a single-node tree is 1 if the node is counted, or 0 if not.

The height of a tree is determined by the number of edges between nodes, not the nodes themselves. Using this approach, the height is `n-1`, where `n` is the number of nodes in the path from the root to the lowest leaf.

The maximum height of the above binary tree is 3. Alternatively, counting by edges, it would be 2.

> The number of edges in a tree are $𝑛−1$, where 𝑛 is the number of nodes.

### Depth / Height

The depth of a binary tree node is measured from the node to the root. The depth at the root is 1, increasing as we descend. To measure depth at a node, count the number of nodes above it, including the node itself.

![[Pasted image 20240625171804.png]]

### Ancestor / Descendent

**Ancestors** are nodes positioned above and connected to the nodes below them.

**Descendants** of a node are either the node's children or the children of some other descendants of the node.

![[Pasted image 20240625172642.png]]
