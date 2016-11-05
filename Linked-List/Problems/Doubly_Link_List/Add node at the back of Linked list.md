### Wrtie a program that adds a node to the end of the linked list
```
class Node:
    
    def __init__(self, data):
        self.data = data
        self.next = None
        self.prev = None

class DoublyLinkedList:
    
    def __init__(self):
        
        self.head = None
        
    #String representation of the list
    def print_list(self, node):

        print "List: "
        
        while(node is not None):
            print " %d" %(node.data)
            node = node.next
        
    def add_node_back(self, new_data):
        
        #Step1: Create a new node
        new_node = Node(new_data)
        
        #Step2: set the new_node.next to NoNE
        new_node.next = None
        
        #Step3: check is the new node is not the first in the list
       
        if self.head is None:
            new_node.prev = None
            self.head = new_node
            return 
        
        #Step4: traverse the list
        last = self.head
        
        while last.next is not None:
            last = last.next
                
        last.next = new_node
        new_node.prev = last
        return

 
    
new_number = DoublyLinkedList()

new_number.add_node_back(7)
new_number.add_node_back(20)
new_number.add_node_back(100)

new_number.print_list(new_number.head)

```

###OUTPUT
```
List:
7
20
100
```
