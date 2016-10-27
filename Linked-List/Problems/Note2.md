```
"""
Write an Algorithm that reverses a queue using  a stack :
"""


"""
Strategy:

1- Check if the Queue is not Empty 

2- Create an Empty stack to use later for the reverses items

3- Iterate through

"""

Queue = [1,2,3,4,5]
 
stack = []
 
q2 = []


for i in Queue:
    # q2.append(i)
    print i 


n = len(Queue)

x = 0 
while x < n :
    
    res= q2.pop()
    stack.append(res)
    x+=1    

print "Q2",q2
print "Originial Array", Queue
print "Stack",stack

```
