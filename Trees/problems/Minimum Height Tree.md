### Given a sorted (increasing order) array, write an algorithm to create a binary tree with
###minimal height.


```
class Node:

    def __init__(self, item):
        self.right = None
        self.left = None
        self.val = item

    def __str__(self):
        return '('+str(self.left)+':L ' + "V:" + str(self.val) + " R:" + str(self.right)+')'


def create_binary_tree(array):

    if array == []:
        return None

    mid_point = len(array)/ 2
    
    node = Node(array[mid_point])

    node.left = create_binary_tree(array[0:mid_point])

    node.right = create_binary_tree(array[mid_point + 1:])

    return node
```
