# General Rules :

These are general rules to follow when solving Big-O problems:

### Purpose of Analyzing Time Complexity:

When we analyze time complexity, we should keep in mind that we looking for analyzing:

1- Very large input size
2- Worst case scenario 


### Rule 1: Calculating Big-O from Polynomial expression 

a) Look for the highest power in the expression

b) Drop the multiplier 

#### Examples 1 :

  17n<sup>4</sup> + 3n<sup>2</sup> + 4n + 8

- Look for the highest polynomial, which is n<sup>4</sup>
- Drop the multiplier (constant number that comes with n<sup>4</sup>. In this problem is __17__)
- The answer: __O(n<sup>4</sup>)__

#### Example 2:

T(n) = 16n + log<sub>n</sub>

- In this example we have Log<sub>n</sub>.The larger the __n__ ,the more insignifcant it becomes, as it gets smaller and smaller in value. so it cannot be the highest polynomial in the problem
- __16n__ is the highest polynomial.
- The answer: __O(n)__


### Rule 2: Calculating the run-time of all the fragments

Looking at the code, you should be able to calculate 2 things:

1- the run time of all of the code fragments

2- the overall run-time of the code

__For simple expression  as :__

- b = 7  (variable)
- print statements
- return statements
-  a++
 
 The run time for all of the above is __O constatnt__ , __O(1)__
 
 __For Single loops__

We calculate the run-time of single loops with simple function calls or expression, by counting the number of times the loop runs times

the simple statement
```
number of loops  *  simple statement

```

#### Example 1:

```
for num in n :
        print num
    
        
```
- the run-time of the loop is __O(n)__
- the run-time of the print statement is __O(1)__

To calculate the over run-time:

```
O(n) * O(1) = O(n)
```
The answer is __O(n)__

 __For nested loops__

if you come accross nested loops, count the nested loops and multiply it by simple statement or calls

#### Example 1:

```
    for num in n :       O(n)
        for x in n :     O(n)
            print x      O(1)
    
        
```
- In this exmple, we have __2 for loop__ means O(n) x O(n)
- One single print statement means __O(1)__
 ```
 O(n) * O(n) * O(1) 
 
 ```

The answer: __O(n<sup>2</sup>)__



 
 



