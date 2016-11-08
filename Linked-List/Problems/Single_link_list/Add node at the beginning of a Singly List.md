### Add node at the beginning of a Singly List

```
class Node:
      def __init__(self, data):
      
            self.data = data
            self.next= None
            
class SinglyList:

      def __init__(self):
          self.head = None
          
      
      def add_not_fron (self, new_data):
      
        # Create a new node
        new_node = Node(new_data)
        
        # Make the next of new node == self.head
        new_node.next = self.head
        
        # Move the pointer from old head to the new head(new_node)
        self.head = new_node

```
