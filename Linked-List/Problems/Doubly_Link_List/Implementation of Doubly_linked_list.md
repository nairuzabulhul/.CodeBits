### Write a program to implement a doubly linked list 

```
#Every Node in a Doubly Link list consists of three MAIN elements
# Data    : is content of the node
# Next    : is the link to the next Node address
#Previous : is the link to the previous Node address

class Node:
    def __init__(self, data):
        self.data = data
        self.next = None    
        self.previous = None 
        
        
    #String representation of the linked list
    """
    if the next node exists:
        the string representation would return that
        all the existing nodes
    
    else:
        return just the entered value or data
    
    """
    def __str__(self):
        if self.next:
            return "%s %s" % (str(self.data), self.next.__str__())
        else:
            return "%s" % str(self.data)
            
            
###Testing ######
node1 = Node(7)
node2 = Node(5)
node3 = Node(10)

node1.next = node2
node2.prev = node1
node2.next = node3
node3.prev = node2

print "Doubly Linked List", node1

##OUTPUT##
 7 5 10 

```

