### Write a program that inserts a node in the middle of two existing nodes

````
class Node:
    def __init__(self, data, previous=None, next=None):
        self.data = data
        self.previous = previous
        self.next = next

    # Just a string representation
    def __str__(self):
        if self.next:
            return '%s %s' % (str(self.data), self.next.__str__())
        else:
            return '%s' % str(self.data)

    # Insert a node in the middle of a Doubly linked list
    def insert_to_middle(self, new_data, left_node, right_node):
        prev = None
        next = None
        # Iterate

        while True:
            # Test for intersection
            if left_node.next is right_node:
                new_node = Node(new_data, left_node, right_node)
                left_node.next = new_node
                right_node.prev = new_node
                return
            elif left_node is right_node:
                new_node = Node(new_data, left_node.previous, right_node.next)
                left_node.next = new_node
                right_node.next.prev = new_node
                return

            # Next iteration
            left_node = left_node.next
            right_node = right_node.prev

# Sample list creation
node1 = Node(1)
node2 = Node(2,node1)
node3 = Node(3,node2)
node4 = Node(4,node3)
node5 = Node(5,node4)
node1.next = node2
node2.next = node3
node3.next = node4
node4.next = node5

#### Test
node1.insert_to_middle(50,node1,node2)
print node1
node1.insert_to_middle (30, node4, node5)
print node1

node1.insert_to_middle(100, node4, node5)
print node1

```
