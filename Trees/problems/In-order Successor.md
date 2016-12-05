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

Step1:
    
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
       and we need to traverse one more step to find the successor of the node. In this case, the step back from node 10 is node 15.
       Therefore, node 15 is the successor of node 12
       
     * if we pick node 8, node 8 has NO to right subtree, so we traverse back to node 10 the parent.
        Since the traversal comes from the left, node 10 has not been visited before, so it becomes the successor of node 8
 
```


### Solution
```

```
