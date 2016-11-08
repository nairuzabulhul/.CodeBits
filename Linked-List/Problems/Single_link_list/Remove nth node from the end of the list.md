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
1- Set 2 pointers at the head: first_pointer and second_pointer 

2- Move the first pointer n node , then move the second pointer by keep a gap of n node between the first_pointer and second_pointer

3- when the first_point reaches the last node in the list, the second node will be in the n position 

Example 

You have a list of 

   1 - 2 - 5 - 6 -9 -10 - 100 -20 -14 -17 -30

and n = 4 


1- Set the two pointer on the head which is (1) 

2- Move first_pointer to n node, which is 4 --- first_pointer would be on 6 , and second_pointer still on 1 

the gap between them is 4 nodes, as n = 4 


3- Keep the first_pointer moving (in a speed of 4 nodes), firs_pointer would be at node (100),

and the second_pointer would be at node(6)

4- Keep the first_pointer moving again(in as speed of 4 nodes), the fist_pointer this time at node (17), and the second_pointer at 

node (100)

5- Keep the first_pointer moving (in a speed of 4 nodes), opops the list need by one node jump, so now the first_pointer at node(30),

and second_pointer has to jump the same a mount of first_pointer, so the second_pointer at node(20)


6- Now the nth from the end list would be the position of second_pointer, which at node 20 
""""

```
