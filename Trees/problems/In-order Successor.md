### Write an algorithm to find the next "node" (i.e inorder successor) of a given nodein a binary search tree. 
### You may assume that wach node has a link to its parent


```
        15
     /      \
    /        \
   10         20
  /   \       /  \
 8     12    17  25
/     /     /      \
6    11     16     27
    
   


Strategy:


Step1: Start from the root

Step2:
    Pick a node :
    - if a node has a right subtree, look for the leftmost node that would become the successor of the picked node
    
    Example: if we pick node (10), we can see that it has a right subtree node (12), 
    the leftmost node is node 11, which is the successor of node 10
    
    - if a node does not have a right subtree, traverse back to the parent node.
    if the traversal back to the node from the left side 
    means that the parent has not been visited if the traversal comes from the right side, 
    it means that the parent has been visited so  we have to go to the parent of the parents
    
    Example:
     * if we pick node 12. node12 has not subtree, so too it goes back to parent node (node 10), 
       the traversal back to the parent comes from the right side. which in this case node 10 has been visited, 
       and we need to traverse one more step to find the successor of the node. 
       In this case, the step back from node 10 is node 15.
       Therefore, node 15 is the successor of node 12
       
     * if we pick node 8, node 8 has NO to right subtree, so we traverse back to node 10 the parent.
        Since the traversal comes from the left, node 10 has not been visited before.
        so it becomes the successor of node 8
 
```


### Solution
```
class Tree:
    def __init__(self, data):
        self.data = data
        self.right = None
        self.left = None




def in_order_successor(node):

    # if a node has right subtree
    if node.right is not None:
        return left_most_node(node.right)

    # if a node deos not have subtree, traverse back to the parent
    temp_parent = node.parent

    while temp_parent is not None:
        if node != temp_parent.right :
            break

        node = temp_parent
        temp_parent = temp_parent.right

    return temp_parent

def left_most_node(node):

    current = node

    # if the left node does not exist, break, otherwise, return the leftmostnode
    while current is not None:
        if current.left is None:
            break

        current = current.data

    return current
```
