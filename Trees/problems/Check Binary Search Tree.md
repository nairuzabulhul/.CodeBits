### Write a program to check if a binary tree is a binary search tree

### Solution:
```
class Tree:

    def __init__(self, data):
        self.data = data
        self.value = value
        self.left = None
        self.right = None



class Solution:

    def __init__(self):
        self.root = None


    def binary_search_tree(self, root, min_value, max_value):

        if root is None:
            return Tree(min_value, max_value)

        if min_value < root.data :
            root.left = binary_search_tree(root.left, min_value, max_value)

        elif max_value > root.data:
            root.right = binary_search_tree(root.right, min_value, max_value)

        else:
            
            root.value = max_value
            
        return root

```
