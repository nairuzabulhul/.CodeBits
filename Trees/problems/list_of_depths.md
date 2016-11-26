### Given a binary search tree, design an algorithm which creates a linked list of all the
### nodes at each depth (eg, if you have a tree with depth D, you’ll have D linked lists).


```
class TreeNode:
     
         
    def __init__(self, data):
        self.data = data
        self.left = None
        self.right = None
             
    #in-order: left, current, right
    def traverse(self,func, level=0):

        # left side
        if self.left:
            self.left.traverse(func, level +1)
        # root
        func(self, level)

        # right side
        if self.right:
            self.right.traverse(func, level +1)
            

# Create linked list from binary tree
def binary_to_linked_list(tree_node):
    tree_dict = {}

    def fill_the_tree(node, level):
        # starts with empty level, then appends a node to the list
        tree_dict.setdefault(level, []).append(node)
        tree_node.traverse(fill_the_tree)

        return tree_node

```
