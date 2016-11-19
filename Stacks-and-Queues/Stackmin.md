## Implement stack and add stackMin to get the minimum element in the stack 

```
Strategy :

Push(int x) // inserts an element x to Special Stack 
1) push x to the first stack (the stack with actual elements)
2) compare x with the top element of the second stack (the auxiliary stack). Let the top element be y.
…..a) If x is smaller than y then push x to the auxiliary stack.
…..b) If x is greater than y then push y to the auxiliary stack.

int Pop() // removes an element from Special Stack and return the removed element 
1) pop the top element from the auxiliary stack.
2) pop the top element from the actual stack and return it.

The step 1 is necessary to make sure that the auxiliary stack is also updated for future operations.

int getMin() // returns the minimum element from Special Stack 
1) Return the top element of auxiliary stack.

We can see that all above operations are O(1).


source : GeeksforGeeks
```

##Solution 

```
class Stack :

    class Stack:

    def __init__(self):
        self.stack = []
        self.min_stack = []


    def push (self, item):

       self.stack.append(item)

       # if min stack is empty or
       # item is smaller than self.stack, add to minstack
       if len(min_stack) == 0 or item <= self.min_stack[-1]:
           self.min_stack.append(item)

    def pop(self):

        # check if the stack empty before popping 
        if len(self.stack) == 0:
                return None
        else:
            if self.stack[-1] == self.min_stack[-1]:
                self.min_stack.pop()
                return  self.stack.pop()

    def min_get(self):
        if len(self.min_stack) == 0
            return None
        else:
            # return the lasst element in the stack
            return self.min_stack[-1]
       

```
