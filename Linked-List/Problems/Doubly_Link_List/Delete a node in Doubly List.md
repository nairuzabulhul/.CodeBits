### Write a program to delete a node from a doubly linked list

```
import gc

class Node:

    def __init__(self, data):

        self.data = data
        self.next = None
        self.prev = None



class DoublyLinkList:

    def __init__(self):
        self.head = None


    def print_list(self, node):

        print "List: "

        while node is not None:

            print "%d" % node.data
            node = node.next


    def add_node_back(self, new_data):

        # Step1: create a new node
        new_node = Node(new_data)

        # Step2: Make the next of new node  = None
        new_node.next = None

        # Step3 : Check if the new_node is the head
        if self.head is None:
            
            new_node.prev = None #set prev of the node to None to indicate that is the head
            self.head = new_node
            return 

        # Step4: if the new node is not the head, traverse the list
        last= self.head
        while last.next is not None:
            last = last.next
            
        last.next = new_node
        new_node.prev = last
        return 
            
    def delete_node(self, node):
 
        current_node = self.head
 
        while current_node is not None:
            
            if current_node.data == node:
                # if it's not the first element
                if current_node.prev is not None:
                    current_node.prev.next = current_node.next
                    current_node.next.prev = current_node.prev
                else:
                    # otherwise we have no prev (it's None), head is the next one, and prev becomes None
                    self.head = current_node.next
                    current_node.next.prev = None
 
            current_node = current_node.next
```

###TESTING
```
n_list = DoublyLinkList()
n_list.add_node_back(5)
n_list.add_node_back(7)
n_list.add_node_back(100)
n_list.add_node_back(10)


n_list.delete_node(7)
n_list.delete_node(100)


n_list.print_list(n_list.head)
```

###OUTPUT 
```
5
100
```
