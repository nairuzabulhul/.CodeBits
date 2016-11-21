## Binary Tree Pre-Order Travseral (Iterative)

```
# Python program to perform iterative preorder traversal
 
# A binary tree node
class Node:
 
    # Constructor to create a new node
    def __init__(self, data):
        self.data = data
        self.left = None
        self.right = None
 
# An iterative process to print preorder traveral of BT
def iterativePreorder(root):
     
    # Base CAse 
    if root is None:
        return
 
    # create an empty stack and push root to it
    nodeStack = []
    nodeStack.append(root)
 
    #  Pop all items one by one. Do following for every popped item
    #   a) print it
    #   b) push its right child
    #   c) push its left child
    # Note that right child is pushed first so that left
    # is processed first */
    while(len(nodeStack) > 0):
         
        # Pop the top item from stack and print it
        node = nodeStack.pop()
        print node.data,
         
        # Push right and left children of the popped node
        # to stack
        if node.right is not None:
            nodeStack.append(node.right)
        if node.left is not None:
            nodeStack.append(node.left)
```

## TESTING
```
# Driver program to test above function
root = Node(10)
root.left = Node(8)
root.right = Node(2)
root.left.left = Node(3)
root.left.right = Node(5)
root.right.left = Node(2)
iterativePreorder(root)

```
