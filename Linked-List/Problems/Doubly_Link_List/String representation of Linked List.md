 
## String representation of Linked list
#### Method 1:
 
```
    def __str__(self):
        if self.next:
            return "%s %s" % (str(self.data), self.next.__str__())
        else:
            return "%s" % str(self.data) 
            
            
            
```
```
#Explanation:
 """
    if the next node exists:
        the string representation would return that
        all the existing nodes
    else:
        return just the entered value or data
    """
```
