__Examples here are gathered from different resources:__

1- Youtube (mycodeschool)

2- Python Algorithm and Data Structure on Udemy by 

3- valeriecodes (GitHub)

### Example 1:
```
def func_constant(values):

    print values[0]
```

#### The answer is : O(1)

### Example 2:

```
def print_3(lst):
    '''
    Prints all items three times
    '''
    for val in lst:
        print val
        
    for val in lst:
        print val
        
    for val in lst:
        print val
```

#### The answer is O(n)

### Example 3:

```
def comp(lst):

    print lst[0]
    
    midpoint = len(lst)/2
    
    for val in lst[:midpoint]:
        print val
        
    for x in range(10):
        print 'number'
```

#### The answer is O(n)

### Example 4 (not python):

```
def insertion_sort(arr):
 # sorts arr in ascending order
 for i in range(len(arr)):
  j = i
  while j > 0 and arr[j - 1] > arr[j]:
    # swap arr[j] and arr[j - 1]
    temp = arr[j]
    arr[j] = arr[j - 1]
    arr[j - 1 ] = temp
    j = j - 1
  return arr
```
#### The answer is O(n<sup>2</sup>)

### Example 5 (not python):

```
def build_matrix(n):
  matrix = []
  for i in range(n):
    matrix[i] = []
    for j in range(n):
      matrix[i][j] = []
      for k in range(n):
        matrix[i][j][k] = i + j + k
```

#### The answer is O(n<sup>3</sup>)

### Example 6 (not python):

```
def binary_search(arr, target):
  # returns True if target is in arr, False otherwise
  if len(arr) == 0:
    return False                 
  else:
    midpoint = len(arr) / 2
    if arr[midpoint] < target:
      binary_search(arr[(midpoint + 1):], target)
    elif arr[midpoint] > target
      binary_search(arr[0:midpoint], target)
    else:
      # arr[midpoint] == target
      return True
```
#### The answer is ???????

### Example 7 :

```
def print_checkerboard(n):
  for i in range(n):
    for j in range(n):
      if i % 2 == 0:
        if j % 2 == 0:
          print 'X',
        else:
          print ' ',
      else:
        if j % 2 == 0:
          print ' ',
        else:
          print 'X',
    print
```
#### The answer is ????????????
