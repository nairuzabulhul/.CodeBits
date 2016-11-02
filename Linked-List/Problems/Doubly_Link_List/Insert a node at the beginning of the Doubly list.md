### Wrtie a program that adds a node at the beginning of the Doubly Linked List


```
#Write a program to add a node at the begining of the Doubly Link

class Node:

    def __init__(self, data):
        self.data = data
        self.next = None
        self.prev = None
        

class DoublyLink:

    def __init__(self):
      self.head = None

    #String representation of the list
    def print_list(self, node):
 
        print "List: "
        while(node is not None):
            print " %d" %(node.data),
            #last = node
            node = node.next

    def add_node_front(self, new_data):

        #Step1: Create a new node
        new_node = Node(new_data)
        
        #Step2: Assign a new node .next as the head(NONE)
        new_node.next = self.head

        #Step3: Check if the self.head is not none
        if self.head is not None:
            self.head.prev = new_node
        
        #Step3: Change the pointer of the head. previous to become as new node
        self.head = new_node

        

 
## Testing ## 
double_list = DoublyLink()
double_list.add_node_front(7)
double_list.add_node_front(10)
double_list.add_node_front(100)

#Printing the list :
double_list.print_list(double_list.head)
```

```
#OUTPUT :
100 10 7 

```
