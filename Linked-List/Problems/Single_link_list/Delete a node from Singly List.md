### Wrtie a program that deletes a node from a Singly Link List
```
# Definition for singly-linked list.
class Node:
     def __init__(self, data):
         self.data = data
         self.next = None

class SinglyLinkList:
    
    def delete_node(self, node):
 
        # set the new_node to the next of node
        new_node = node.next
        
        # Check if the new node is not the head 
        if new_node is not None:
        
            # set the value of node to the new node
            node.data = new_node.data
            node.next = new_node.next
            
        else:
            raise "cannot delete the last node"

```
