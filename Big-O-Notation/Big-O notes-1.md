#Big-O Notation

## Definition:

- A way computer algorithm scales with large input





Big-O Notation:

- Time Complexity
- Space Complexity 


Examples: 

# Problem 1 :

### Take an input of n and return the sum of the numbers from 0 to n 

### Bad Answer:
```  
def sum_all_nums(n+1):

  sum_of_nums = 0;
  
  for x in range(0,n):
  
    sum_of_nums += x
  
  return sum_of_nums

```
### Good Answer:

```
def sum_all_nums(n):
  
  return (n*(n+1))/2
```

## Explanation:

For the fist answer the (time comlexity), which means the time it takes to run the function is __O(n)__, while the second answer

time complexity is __O(1)__. 

The reason for the second answer to be efficient is that __O(1)__ constatnt is considered the most efficient functions among __Big-O__ functions,
because it return ONLY one statement(no loops, no ifs)





