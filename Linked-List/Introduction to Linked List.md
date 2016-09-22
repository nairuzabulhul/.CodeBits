##Linked List Notes:

 1- First, before we start learning Linked list, we start review how array works. Arrays saves items in memeory by reserving 4 bytes in memory

for every item

[![mem1.jpg](http://s15.postimg.org/5ezt0xyqj/mem1.jpg)](http://postimg.org/image/adnbfh2jb/)

2- An array for items are usually reserves on memory as a block . In the below example, we have an array of 4 intergers, these
intergers are as continous block

[![mem2.jpg](http://s12.postimg.org/sjx93s4ct/mem2.jpg)](http://postimg.org/image/izdmgwf0p/)


3- Time Complexity of an array is __O(1)__

###Adding to an array:

1- To add to an array, we have to reserve fixed size length to fillup. 

2-Adding items to an existing array, reserve new size for the array, copy old items and add new ones to the the new array

[![mem3.jpg](http://s18.postimg.org/oqqjh6pnt/mem3.jpg)](http://postimg.org/image/9597x8dph/)


### Disadvantage of arrays:
- fixed sizes
- Every time you need to add new items to an existing array. we have to copy old items and add new ones
- if the array is large, and  contains only few items, we will have memory waste.

####The solution to replacing arrays is using Linked Lists:

[![link1.jpg](http://s17.postimg.org/e3bn89u1b/link1.jpg)](http://postimg.org/image/4vjerkmyz/)

1- Unlike array that saves items as block. Linked List saves items separately on memory.for the example below, you need to reserve  bytes of

memory and then add the item (6). Then, reserve another 4 bytes separately for number 5 . 

__NOTES__: all requests of reserving space in memory are separately. the items are not saved continously as arrays


2- Every new item __node__added to the linked list has three part info, address and link 

[![link4.jpg](http://s21.postimg.org/bxrd325sn/link4.jpg)](http://postimg.org/image/e2bq457f7/)


3- the info is the item (number)you are going to add to the list. The address is the location of the item in the meory.

4- The address the node is the next item address not the existing one.(That is why it is a linked list)

[![link5.jpg](http://s10.postimg.org/cn9bhiy3d/link5.jpg)](http://postimg.org/image/w53yxgv11/)

5- The address of the last item in the link is 0 or null indicates the end of the linked list

6- The first node is called __header__ that gives us the access to the whole list


### Insertion to the linked list:

1- create a node (item,address), separately and  then linked it through to the rest of the list through adjusting the address

of the next available address

[![link7.jpg](http://s10.postimg.org/n8ajjop89/link7.jpg)](http://postimg.org/image/mvj5di6yd/)


__Time Complexity___: O(n)







####Source:
[MyCodeSchool ""Youtube""] (https://www.youtube.com/watch?v=NobHlGUjV3g&feature=player_embedded)
