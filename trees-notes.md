# Logarithms

* What is a Logarithm?

    • Exponent Review:
        - An exponent represents how many times a number (the base) is multiplied by itself
        - Example: 2^5 = 2 x 2 x 2 x 2 x 2 = 32

    • Logarithm Definition:
        - A logarithm is the inverse of an exponent
        - The logarithm base-n of a number is the exponent to which the base must be raised to produce that number
        - Example: log2(32) = 5, because 2^5 = 32

    • Logarithm and Exponent Relationship
        - if b^x = y, then logb(y) = x
        - Example: 10^3 = 1000 means log10(1000) = 3


* Binary Logarithm (Base-2 Logarithm)
    • Binary Exponent Table:
        - 2^0 = 1
        - 2^1 = 2
        - 2^2 = 4
        - 2^3 = 8
        - 2^4 = 16
        - 2^5 = 32

    • Binary Logarithm Table:
        - log2(1) = 0
        - log2(2) = 1
        - log2(4) = 2
        - log2(8) = 3
        - log2(16) = 4
        - log2(32) = 5

    • Calculation in Code:
        - in JavaScript:

        ```js
        Math.log2(32) // 5
        ```

* Why Are Logarithms Important?

    • Growth Comparison
        - Logarithmic growth is much slower than linear (O(n)) or quadratic (O(n^2)) growth
        - Example: for large inputs, logarithmic functions grow very slowly, almost appearing constant on a graph

    • Real World Impact:
        - For large input sizes, algorithms with O(log n) complexity vastly outperform those with O(n) complexity
        - Example: to reach a logarithmic value of 100, n would need to be astronomically large (around 1.27 x 10^30)


* Summary
    • Logarithms: the inverse of exponents, telling you the number of times a base must be multiplied to reach a given value
    • Binary Logarithms: logarithms with base-2, crucial for understanding the performance of algorithms, particularly those with O(log n) complexity
    • Importance in Algorithms: logarithmic time complexity is extremely efficient, especially for large inputs, making it a key concept in optimising code performance


# Binary Search

1. Overview:
    • Purpose: efficiently search for a target value in a sorted array
    • Complexity: time complexity is O(log n), which is significantly faster than a linear search (O(n)) for large data sets

2. Divide and Conquer Approach:
    • Concept: binary search uses a divide-and-conquer strategy by repeatedly dividing the search range in half
    • Example: searching for "dictionary" in a dictionary by continuously splitting the range of pages in half until the target word is found

3. Preconditions for Binary Search:
    • Data must be sorted: the array or list needs to be in a sorted order
    • Constant-time access by index: the data structure must allow direct access to elements via indices (e.g. arrays)

4. Binary Search Algorithm:
    • Initial Setup:
        - Define two pointers: `lo` (start of the array) and `hi` (end of the array)
    • Midpoint Calculation:
        - Calculate the midpoint: `mid = (lo + hi) / 2`
    • Comparison:
        - Compare the target with `arr[mid]`
        - if `arr[mid] === target`, return `mid`
        - if `arr[mid] < target`, move the `lo` pointer to `mid + 1`
        - if `arr[mid] > target`, move the `hi` pointer to `mid - 1`
    • Repeat: continue the process until the target is found or `lo` exceeds `hi`
    • Return: if the target is not found, return `-1`

5. Pseudocode:

    ```js
    function binarySearch(arr, target) {
    lo = 0
    hi = arr.length - 1

    while (lo <= hi) {
        mid = Math.floor((lo + hi) / 2)

        if (arr[mid] == target) {
        return mid
        } else if (arr[mid] < target) {
        lo = mid + 1
        } else {
        hi = mid - 1
        }
    }

    return -1
    }
    ```

6. Performance Analysis:
    • Time Complexity: O(log n) due to halving the search space with each comparison
    • Space complexity: O(1) as only a few variables (lo, hi, mid) are used regardless of input size

7. Comparison with Linear Search:
    • Linear Search:
        - Compares each element sequentially until the target is found
        - Time complexity is O(n), making it inefficient for large datasets
    • Binary search:
        - Performs log base 2 comparisons, greatly reducing the number of checks needed

8. Practical Performance Test:
    • Experiment: run a binary search on a large dataset and compare its performance with linear search
    • Results: binary search typically performs significantly faster, especially as the dataset grows

9. Key Takeaways:
    • Binary search is an essential algorithm for efficiently finding elements in assorted arrays
    • Understanding its preconditions (sorted data and index access) and implementation is crucial for optimising search operations for software development


# Intro to Trees

1. What is a Tree?
    • A tree is a type of graph that is structured in a heirarchical manner
    • It consists of nodes (elements) and edges (connections between nodes)
    • A tree is a connected acyclic graph, meaning there are no cycles

2. Characteristics of Trees:
    • Root: the topmost node in a tree. the only node without a parent
    • Children: Nodes that descend from another node
    • Leaf: A node with no children
    • Internal node: a node that has at least one child
    • Path: a sequence of nodes connected by edges
    • Subtree: a tree formed from any node and its descendants

3. Trees vs. Non-tree Graphs
    • Trees have no cycles
    • Each node in a tree has exactly one parent (except for the root)
    • A graph that contains a node with multiple parents or cycles is not a tree

4. Binary Trees:
    • A binary tree is a type of tree where each node has at most two children
    • Special cases of binary trees:
        - Full binary tree: every node has 0 or 2 children
        - Complete binary tree: all levels are fully filled except possibly the last, which is filled from left to right
        - Perfect binary tree: all internal nodes have two children, and all leaves are at the same level

5. Coding a Binary Tree (object-oriented approach):
    • Represent each node as an instance of a `TreeNode` class
    • A `TreeNode` typically has:
        - `val`: the value stored in the node
        - `left`: reference to the left child
        - `right`: reference to the right child

    ```js
    class TreeNode {
        constructor(val) {
            this.val = val;
            this.left = null;
            this.right = null;
        }
    }

    // creating nodes
    let a = new TreeNode('a');
    let b = new TreeNode('b');
    let c = new TreeNode('c');
    let d = new TreeNode('d');
    let e = new TreeNode('e');
    let f = new TreeNode('f');

    // building the tree
    a.left = b;
    a.right = c;
    b.left = d;
    b.right = e;
    c.right = f;
    ```

    The tree structure would visually look like this:
```js
    a
   / \
  b   c
 / \   \
d   e   f

```

6. Basic Terminology Review:
    • Tree: A graph with no cycles
    • Binary Tree: a tree where each node has at most two children
    • Root: the topmost node, the starting point of the tree
    • Leaf: a node with no children
    • Internal Node: a node that has one or more children
    • Path: a sequence of nodes connected by edges in the tree

7. Key Takeaways:
    • Trees are an important subclass of graphs, used widely in various algorithms and data structures
    • Understanding binary trees is crucial since they form the basics for more complex structures like binary search trees, heaps, and more
    • The root node is often used to represent the entire tree in algorithms


# Tree Traversal Overview

Tree Traversal: the process of visiting or evaluating every node in a tree. There are various methods of tree traversal, each with its own advantages depending on the specific task.

* Key Terminology
    • Node: contains a value and pointers to other nodes
    • Edge: a pointer from one node to another
    • Root Node: the top node in a tree
    • Parent/Child Node: a parent node points to child nodes
    • Subtree: a tree that is a child of another node
    • Branch Node: a node with at least one child
    • Leaf Node: a node with no children
    • Level: number of edges between a node and the root
    • Height: number of edges from the root to the deepest leaf

* Types of Tree Traversals
    1. Depth-First Traversal (DFT):
        • Pre-order: Visit the root, then the left subtree, then, the right subtree
            • Example: 4, 2, 1, 3, 6, 5, 7
```js
     4
   /   \
  2     6
 / \   / \
1   3 5   7

```

        • In-order: visit the left subtree, then the root, then the right subtree
            • Example: 1, 2, 3, 4, 5, 6, 7

        • Post-order: visit the left subtree, then the right subtree, then the root
            • Example: 1, 3, 2, 5, 7, 6, 4

    2. Breadth-First Traversal (BFT):
        • Traverse each level of the tree from left to right before moving to the next level
        • Example: 4, 2, 6, 1, 3, 5, 7


* Implementation Techniques

    1. Recursive Depth-First Search (DFS):
        • Used to explore as deep as possible along each branch before backtracking
        • Example for binary tree search:

        ```js
        function binaryTreeSearch(root, target) {
            if (root === null) return false;
            if (root.value === target) return true;
            return binaryTreeSearch(root.left, target) || binaryTreeSearch(root.right, target)
        }
        ```

    2. Iterative Depth-First Traversal with a Stack:
        • Use a stack to simulate recursion
        • Example:

        ```js
        function depthFirstTraversal(root) {
            const stack = [];
            stack.push(root);
            while (stack.length > 0) {
                let node = stack.pop();
                console.log(node.value);
                stack.push(node.right);
                stack.push(node.left);
            }
        }
        ```

    3. Iterative Breadth-First Traversal with a Queue
        • Use a queue to explore nodes level by level
        • Example:
        ```js
        function breadthFirstTraversal(root) {
            const queue = [];
            queue.push(root);
            while (queue.length > 0) {
                let node = queue.shift();
                console.log(node.value);
                if (node.left) queue.push(node.left);
                if (node.right) queue.push(node.right);
            }
        }
        ```

* Summary
    • Pre-order, in-order, post-order: these are all depth-first traversals used for binary trees, differing only in the order in which nodes are visited
    • Breadth-first Traversal: visits nodes level by level, making it different from depth-first methods
    • Implementation: depth-first can be implemented both recursively and iteratively (with a stack), while breadth-first typically uses a queue
