# Data Structures and Algorithms 2
 
# Authors: 
**Matthias Bartolo - 0436103L**

## Preview:
<p align='center'>
  <img src="https://github.com/mbar0075/Data-Structures-and-Algorithms2/assets/103250564/9f65b3e6-c62c-4a72-bf47-fb7ee01e7553" style="display: block; margin: 0 auto; width: 70%; height: auto;"></br>
</p>

## Description of Task:
The task involved the insertion of all elements from a set into an **AVL tree**, a **Red-Black tree**, and an **unbalanced binary search tree (BST)**. Each of the three tree implementations was created from scratch. After inserting the values into each tree, the total number of rotations performed (in the AVL and Red-Black trees), the height of the tree, the number of nodes in the tree, and the total number of comparison operations (left/right decisions) were recorded.

Next, all elements from the set were deleted from each of the three trees. The total number of rotations performed (in the AVL and Red-Black trees), the height of the tree, the number of nodes in the tree, and the total number of comparison operations were again measured and recorded.

Subsequently, a search operation was conducted for every element in the set within each of the three trees. The search could be successful or unsuccessful, and the results were documented accordingly.

### What is an unbalanced Binary Search Tree?
An unbalanced Binary Search Tree (BST) is a binary tree, whereby every node in the tree can have a
maximum of up to two children. Furthermore, every node in the tree, abides by the rule that all the
nodes in the left Subtree have a smaller value than the current node value, similarly, all the nodes in
the right Subtree have a larger value than the current node value. Moreover, a BST does not have any
balance condition, and thus degenerate.
```python

class BSTNode:
    totalNoOfComparisons=0
    totalNoOfNodes=0
    
    def __init__(self, value):
        self.value = value
        self.leftChild = None
        self.rightChild = None
```

### What is an AVL Tree?
An AVL Tree is a BST, whereby every node in the tree, also abides by a balance condition. The
balance condition states that the height of the left Subtree and the height of the right Subtree does not
differ by no more than one. Upon Insertion or Deletion of nodes in the AVL Tree, if the balance
condition is violated, the AVL Tree will perform a relevant rotation, to rebalance the tree. Moreover,
since the AVL Tree has this balance condition in place, the tree will not degenerate, when compared
to BST.
```python
class AVLNode:
    totalNoOfComparisons=0
    totalNoOfNodes=0
    totalNoOfRotations=0
    
    def __init__(self,value):
        self.value = value
        self.leftChild = None
        self.rightChild = None
        self.height= 0
```

### What is a Red-Black Tree?
A Red-Black Tree (RBT) is a binary tree, whereby every node in the tree, also contains an extra
property, which denotes the node’s colour. Properties of an RBT include that:

**1. Nodes in the RBT would either have a red or black colour.** <br>
**2. The root node of the RBT would have a black colour.** <br>
**3. Children of red nodes would have a black colour.** <br>
**4. Null Leaves would have a black colour.** <br>
**5. Paths from any node to Null Leaves, would have the same number of black nodes.** <br>

Additionally, upon Insertion or Deletion of nodes in the RBT, if one of the previously mentioned
properties is violated, the RBT would either perform a recolouring or a relevant rotation, to maintain
the RBT’s integrity.
```python
class RedBlackTreeNode:
    totalNoOfComparisons=0
    totalNoOfNodes=0
    totalNoOfRotations=0
    
    def __init__(self,value):
        self.value = value
        self.leftChild = None
        self.rightChild = None
        self.parent=None
        self.color=0
```

### Evaluation:
During the comparison of the insertion operation for the trees, it was observed that the AVL tree exhibited lower total comparisons and height compared to the unbalanced BST and Red-Black tree (RBT). Interestingly, the RBT showed similar total comparisons and height to the AVL tree but had fewer rotations. Moving on to the deletion operation, it was generally noted that the RBT had fewer total comparisons and rotations compared to the BST and AVL tree. The RBT's height was also similar to the AVL tree, which typically had the least height among the trees. However, in some cases, the AVL tree had fewer rotations than the RBT, albeit with a marginal difference. This trend was particularly evident in Test Cases 4 and 8. Regarding the search operation, the AVL tree exhibited fewer total comparisons compared to the BST and RBT, while the RBT showed similar total comparisons to the AVL tree.

<p align='center'>
  <img src="https://github.com/mbar0075/Data-Structures-and-Algorithms2/assets/103250564/0aa86e35-f23c-40d1-9778-a7786600a65e" style="display: block; margin: 0 auto; width: 70%; height: auto;"></br>
</p>

In conclusion, the comparisons indicate that for prioritizing insertion and deletion, the RBT is preferable due to its similar height to the AVL tree and fewer rotations. On the other hand, if efficient searching is the priority, the AVL tree is recommended due to its superior balance compared to the RBT, resulting in faster tree traversal. The unbalanced BST demonstrated inefficiency and is primarily useful for educational purposes rather than practical applications. Real-world applications for each tree structure can be summarized as follows: the unbalanced BST can be used in educational settings to teach basic tree concepts, the AVL tree is well-suited for databases due to its optimal search efficiency, and the RBT is beneficial for sets or hash maps, especially when frequent additions or removals are expected.

## Deliverables:  
1. Code/ - subdirectory which holds all Source Code for the Assignment
2. report.pdf - documentation of the Assignment
