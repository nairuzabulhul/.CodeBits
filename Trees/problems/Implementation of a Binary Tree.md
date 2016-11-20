### Implementation of a Binary Tree

```
"""
Binary Tree is a trea which each node has ONLY two children at most.
One is indentified as left and the other is right 
"""

class Node:
    def __init__(self, data):
        self.data = data
        self.left = None
        self.right = None


    def __str__(self):
        """
        This function for the string representaiton
        of the tree
        """
        return str(self.data)

class Tree:

    def __init__(self):
        self.root = None


    def create_tree(self, new_data):

        # if the trea has not root, create a root
        if self.root == None:
            self.root = Node(new_data)

        else:
            # if the root exists
             current = self.root

             while current:

                 if new_data < current.data:

                    # if the number is smaller than the root, add the value
                    # to the left side of the tree
                    if current.left :
                        current = current.left
                    else:
                        current.left = Node(new_data)
                        break;
                    
                 elif new_data > current.data:

                    if current.right :
                        current = current.right
                    else:
                        current.right = Node(new_data)
                        break;
                 else:
                    break
```
