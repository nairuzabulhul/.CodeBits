## Write a method to replace all the space with %20

```
def urlify(str):
    res = ""  

    my_strin = str.strip()
    print my_strin
    
    if my_strin == " ":
        return None

    for n in my_strin:
        if n == " ":
            res += "%20"
        else:
            res += n

    return res
my_strin ="  My Name is    "

print urlify(my_strin)


Time Complexity : O(n)
```

```
Out put :

My%20Name%is

```
