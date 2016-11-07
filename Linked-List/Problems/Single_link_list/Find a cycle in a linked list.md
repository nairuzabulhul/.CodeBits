### Write a program to determine if a linked list has a cycle in it.

```
class Node:

    def __init__(self):
        self.data = data
        self.next= None


class FindCycle:

    def has_cycle(self, head):

        # set two pointers
        first_pointer = head
        second_pointer - head

        # check id the second pointer is not None
        while second_pointer is not None and second_pointer.next is not None:

            first_pointer = first_pointer.next
            second_point  = second_pointer.next.next


            # check if the second_pointer is equal to first_pointer
            if second_pointer == first_pointer :
                return True

        return False

        


```

