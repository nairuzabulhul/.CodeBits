### 1.2 Check Permutations

##### Time Complexity: O(n)

```
import collections

def same_permutation(string1, string2):
    hash_table = collections.defaultdict(int)
 
    for x in string1:
        hash_table[x] += 1
    for x in string2:
        hash_table[x] -= 1
    return not any(hash_table.itervalues())

```

### OUTPUT :
```
print same_permutation("cba","abc")

True

print same_permutation("cbaa","abc")

False

```
