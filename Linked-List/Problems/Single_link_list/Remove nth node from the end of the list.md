### Write a program to remove a nth node from the end of the list

```
class Node:

    def __init__(self, data):
        self.data = data
        self.next = None


class SinglyList:

    def removeNthFromEnd(self, head, n):
        # Set the current node to 0 or -1
        current_node = Node(0)
        
        # Set the head to the next of current_node
        current_node.next = head

        # Set 2 pointers to traversr the list
        first_pointer = current_node
        second_pointer = current_node

        # Move the second pointer 
        for i in range(0, n):
            second_pointer = second_pointer.next
            
        # travserse the list    
        while second_pointer.next:
            first_pointer = first_pointer.next
            second_pointer =  second_pointer.next
            
        # Move the first pointer a head
        first_pointer.next = first_pointer.next.next
        
        return current_node.next


""""
Strategy

1- Set 2 pointers

2- Move the first pointer n+1 steps

3- Second Pointer remains at the begining of the list

4- Now, both pointers are exactly separated by nn nodes apart.

5-We maintain this constant gap by advancing both pointers together until the first pointer arrives past the last node.

6-  The second pointer will be pointing at the nnth node counting from the last. We relink the next pointer of the node referenced by the second pointer to point to the node's next next node

""""

```
