

# Example 

#arr = [2,2,3,6]
arr = [4,4,9,3]
target = 8

def new_sum (arr, target):
    
    for i in range(len(arr) - 1):
        
      if arr[i] == arr[i + 1] :
          if target ==  arr[i] + arr[i + 1]:
            print [arr.index(arr[i]), arr.index(arr[i]) + 1]
            
      else:
        
         if target ==  arr[i] + arr[i + 1]:
           print [arr.index(arr[i]), arr.index(arr[i + 1])]
        
new_sum(arr, target)
