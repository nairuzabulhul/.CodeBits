####### Merge two sorted linked lists and return it as a new list. The new list should be made by splicing together the nodes of the first two list

######Time: O(n) 
######Space:O(1)



#### Solution:

```

class Solution:
    
    def mergeTwoLists(self, list1, list2):

        # Create a temp node
        temp_node = ListNode(0)
        pointer = temp_node

        # While the list1 and lis2 true
        while list1 and list2 :
            #if the number in list1 smaller than list2, add number to temp_node list
            if list1.data < list2.data:
                pointer.next = list1
                list1 = list1.next
            else:
                pointer.next = list2
                list2 = list2.next
            
            # Move the pointer to next node    
            pointer = pointer.next

        # if the l1 or l2 reached the end , add the reamining number to list3  
        if list1 == None:
            pointer.next = list2
        else:
            pointer.next= list1

        return temp_node.next

```



```
Strategy:

List1 =  1 > 5 > 9 
List2 =   7 > 8> 10


List3 = 1 >5 > 7 > 8 > 9 > 10

1- Create a temporary Node and its pointer points to the next node from either List1 or List2.

Like this :

     List3 = temp_node --- > List1 or List2

2- After, creating the temp node, compare the first elements from List1 and List2 

    The first element of List1 is 1 
    The first element of List2 is 7 

3- if List1 is smaller than List2, add List1 to the List3 and and move the pointer to
the next node from List1, otherwise append from List2, and mode the poiner from List2


Let's see how this works

 List3 =  temp_node > 

- compare 1 from List 1 with 7 from List2 . 1 is smaller than 7. Therefore, 1 is added to List3 and the
  pointer moves to next node  from List1, which is 5.

- Now compare 5 from List1 with 7 from List2. 5 is less than 7. 
   Therefore, 5 is added to List3 and pointer moved to next_node, which is 9 

- Since List1 reached the end, append the remaining of list2 to List3:

      temp_node > 1> 5 > 7 > 8 > 10 

```
