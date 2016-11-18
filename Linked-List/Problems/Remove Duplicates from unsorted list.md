#### Write a program to remove duplicates from unsorted linked list 

```
Strategy :

There are two solutions for this problems . 
First solution is without adding temporary buffer or list.It is done by 2 loops.
Second solution is using hash tables

METHOD 1 (Using two loops)

- This is the simple way where two loops are used.
- Outer loop is used to pick the elements one by one.
- Inner loop compares the picked element with rest of the elements.


METHOD 3 (Use Hashing)
We traverse the link list from head to end. 
For every newly encountered element, we check whether it is in the hash table: 
if yes, we remove it; otherwise we put it in the hash table.

source:GeeksforGeeks
```


### Solution 1: Using 2 loops

### Time Complexity is O(n^2)
### Space Complexity is O(1)

```
class Node:

    def __init__(self,data):
        self.data = data
        self.next = None



class Solution :

    def __ini__(self):
        self.head = None


    def remove_duplicates(self,head):

        # store the head in a variable
        current = head

        if head is None:
            return None

        while current != None:
            new_head = current
            while new_head != None
                if new_head.next.data == current.data:
                    new_head.next = new_head.next.next
                else:
                    new_head = new_head.next

            current = current.next

        return head

        
```

### Solution2 : Hash Table

#### Time Complexity is O(n)
#### Space Complexity is O(n)

```
class Node:

    def __init__(self,data):
        self.data = data
        self.next = None



class Solution :

    def __ini__(self):
        self.head = None


    def remove_duplicates(self,head):

        # special case
        if head is None:
            return None

        current = head

        hash = {}

        hash[head.data] = True

        while current.next != None:
            if hash.has_key(current..next.data):
                # remove the node 
                current.next = current.next.next
            else:
                hash[current.next.data]= True
                current = current.next
                
        return head
```
