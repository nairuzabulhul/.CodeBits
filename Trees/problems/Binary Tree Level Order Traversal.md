### Binary Tree Level Order Traversal

![Log](https://s13.postimg.org/jt83r2f2f/test1.png)
#### Source: LeetCode



####Solution

####Strategy:




####Code:

```
# Definition for a binary tree node.
# class TreeNode(object):
#     def __init__(self, x):
#         self.val = x
#         self.left = None
#         self.right = None

class Solution(object):
    
    def levelOrder(self,root):
        #Edge case:
        if root == None:
            return []
        
        res_list = []
        
        node = [root]
        
        while node :
        
            #Access root first and append it to result list
            res_list.append([x.val for x in  node] )
            
            next_node = []
            
            # loop through node, and check left and right of the node
            # append to nextnode
            for n in node:
                if n.left != None:
                    next_node.append(n.left)
                    
                if n.right != None:
                    next_node.append(n.right)

	     
            node = next_node
            
        return res_list    
```

