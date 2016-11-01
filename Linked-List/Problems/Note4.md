class LinkedList:
    def __init__(self, data, prev=None, next=None):
        self.data = data
        self.prev = prev
        self.next = next

    # Just a string representation
    def __str__(self):
        if self.next:
            return '%s %s' % (str(self.data), self.next.__str__())
        else:
            return '%s' % str(self.data)

# Insert to middle logic
    def insertToMiddle(self,data, left, right):
        prev = None
        next = None
        # Iterate
        
        while True:
            # Test for intersection
            if left.next is right:
                node = LinkedList(data, left, right)
                left.next = node
                right.prev = node
                return
            elif left is right:
                node = LinkedList(data, left.prev, right.next)
                left.next = node
                right.next.prev = node
                return
    
            # Next iteration
            left = left.next
            right = right.prev
    
            # This doesn't actually execute for a right call
            if not left or not right:
                return

# Sample list creation
node1 = LinkedList(1)
node2 = LinkedList(2,node1)
node3 = LinkedList(3,node2)
node4 = LinkedList(4,node3)
node5 = LinkedList(5,node4)
node1.next = node2
node2.next = node3
node3.next = node4
node4.next = node5

# Test
print node1 
# insertToMiddle(5,node4,node4)
# print node1
node1.insertToMiddle (30, node4, node5)
print node1
# insertToMiddle(7, node1, node4)
# print node1        
