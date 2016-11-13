Given a sorted linked list, delete all duplicates such that each element appear only once.

For example,
Given 1->1->2, return 1->2.
Given 1->1->2->3->3, return 1->2->3.


Time Complexity: O(n)
Space Complexity:O(1)


```
# Definition for singly-linked list.
# class ListNode(object):
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution(object):
    def deleteDuplicates(self, head):
        """
        :type head: ListNode
        :rtype: ListNode
        """
        current = head
        
        if head is None:
            return head
        
        while current.next is not None:
            if current.val == current.next.val:
                temp = current.next
                current.next = current.next.next
                
                del temp
            else:
                current = current.next
        return head
        
```

```
Strategy:
1- set the head as current

2- Traverse the list 

3- if the current(head) is equal to the next node of the current head 
    - save the pointer that points to the next node as temp 
    - move to the next next node
    - delete the duplicate node
    - return the head
4- Else (if the current and current.next are not equal):
      - keep move to next node
```
