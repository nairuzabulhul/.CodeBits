```
Reverse a queue using queue propoerties of first in first out 

class Queue:
    def __init__(self):
        self.items = []
    
    #fOR STRING REPRESENTATION
    def __str__(self):
        return str(self.items)
        
    def isEmpty(self):
        return self.items == []

    def enqueue(self, item):
        self.items.insert(0,item)

    def dequeue(self):
        return self.items.pop()

    def size(self):
        return len(self.items)
        
    def append(self,items):
        return self.items.append(items)
    
    

q = Queue()
# q.enqueue(1)
# q.enqueue(2)
# q.enqueue(3)
# q.enqueue(4)
# q.enqueue(5)

# newQueue = Queue()

# n = 1 

# while 5 >= n:
#     q.enqueue(n)
#     newQueue.enqueue(n)
#     n+=1

# print "Original Queue",q
# print "New Queue", newQueue


# stack = Queue()

# z = 1

# while  5 >= z:
#     p = newQueue.dequeue
#     stack.append(z)
#     z+=1
    
# print "Dequeue",newQueue
# print stack




```
