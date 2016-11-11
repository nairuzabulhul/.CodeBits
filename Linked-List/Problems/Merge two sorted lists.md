####### Merge two sorted linked lists and return it as a new list. The new list should be made by splicing together the nodes of the first two list

######Time: O(n) 
######Space:O(1)




```
Strategy:


List1 =  1 > 5 > 9 

List2 =   7 > 8> 10


List3 = 1 >5 > 7 > 8 > 9 > 10

1- Create a temporary Node and its pointer points to the next node from either list1 or list2

List3 = result_node --- > List1 or List2

2- After, creating the temp node, compare the first elements from list1 and list2 

 The first element of List1 is 1 
 The first element of List2 is 7 

3- if list1 is smaller than list2, append List1 to the list and and move the pointer to the next node from list1, otherwise append from List2

Let's see how this works

result_node > 1> 5 > 7 > 8 > 10

- compare 1 from List 1 with 7 from List2 . 1 is smaller than 7. Therefore, 1 is added to List3 and the pointer moves to next node    which is 5 

- Now compare 5 from list1 with 7 from list2. 5 is less than 7. Therefore, 5 is added to List3 and pointer moved to next_node, which is 9 

- Compare 9 from List1 with 7 from List2. 7 is less than 9. 7 is added to List3, and List2 pointer moves to next_node which is 8 

- Since List1 reached the end, append the remaining of list2 to List3:

      result_node > 1> 5 > 7 > 8 > 10

```
