## Write a program that finds a nthh node from the last in a singly linked list 


```
Strategy :

1- Using two pointers



```

## Solution

```
class LinkedListNode:

    def __init__(self, value, nextNode=None, prevNode=None):
        self.value = value
        self.next = nextNode
        self.prev = prevNode

    def __str__(self):
        return str(self.value)


class LinkedList:

    def __init__(self, values=None):
        self.head = None
        
    def kth_to_last(ll, k):
    runner = current = ll.head
    for i in range(k):
        if runner is None:
            return None
        runner = runner.next

    while runner:
        current = current.next
        runner = runner.next

    return current

```
## OUTPUT
```
ll = LinkedList()
ll.generate(10, 0, 99)
print(ll)
print(kth_to_last(ll, 3))  
        
```

###Time complexity is O(n)
