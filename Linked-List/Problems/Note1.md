#### ADD and Delete from the single linked List


Note: last node cannot be delted



```
class Node:
 
    def __init__(self, data):
        self.data = data
        # self.prev = None
        self.next = None
 
    # Just a string representation
    def __str__(self):
        if self.next:
            return '%s %s' % (str(self.data), self.next.__str__())
        else:
            return '%s' % str(self.data)

def delete_node(del_node):
    
    next_node = del_node.next
    
    if next_node is not None:
        del_node.data = next_node.data
        del_node.next = next_node.next

z  =Node(7)
a = Node(5)
b = Node(3)
c = Node(1)
d =Node(10)

z.next = a
a.next = b
b.next  = c 
c.next = d


delete_node(d)

print z


```
