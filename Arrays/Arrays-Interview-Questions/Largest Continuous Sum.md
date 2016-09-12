## Largest Continuous Sum

[![large.jpg](https://s9.postimg.org/6aior6b8f/large.jpg)](https://postimg.org/image/g7tpk8iu3/)

##Solution:

The question asks for the largest continuous number. if the array numbersa re positive, all you have to do is add them, however if there is negative numbers in the array, the array index has to rest it self
```
#Find te largest continous sum

def largest_sum(arr):
    
    current_num = max_num = arr[0]
    
    
    for x in arr[1:] :
        
        current_num = max(current_num + x , x)
        
        max_num = max(current_num, max_num)
        
    return max_num        
    
    
# arr = [1,2,-1,3,4,10,10,-10,-1]   
arr = [1,2, -3, 4]
print largest_sum(arr)
```
