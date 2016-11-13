```

Write a program to find the node at which the intersection of two singly linked lists begins.


For example, the following two linked lists:

A:          a1 → a2
                   ↘
                     c1 → c2 → c3
                   ↗            
B:     b1 → b2 → b3
begin to intersect at node c1.


```

```
# Definition for singly-linked list.
# class ListNode(object):
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution(object):
    
    
     def getIntersectionNode(self, headA, headB):
       
       list_a = self.getSize(headA)
       list_b = self.getSize(headB)
       
       
       if list_a < list_b :
           return self.getIntersectionNode(headB, headA)
           
       
       for n in range(list_a - list_b):
           headA = headA.next
    
       while headA and headB:
          
          if id(headA) == id(headB):
              return headA
        
          headA= headA.next
          headB = headB.next
          
       return None
          
     def getSize(self, head):
        len = 0 
        
        while head:
            len +=1
            head = head.next 
        return len
              
        
        

```
