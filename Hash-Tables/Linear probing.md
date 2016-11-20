### Linear probing of hash tables

```
class HashTable:
    def __init__ (self):
        self.size = 13
        self.hash_keys = [None] * self.size
        self.hash_values = [None] * self.size

    def hash_function(self,key,size):
         """
            This function returns the insert positin of new data 
         """
         return key % size

    def rehash_function(self, old_hash, size):
        """
            This function rehashed the old hash to avoid collision
        """
        return (old_hash + 1) % size

    def add_data(self, key, value):
        """
        This function adds data to the
        hash table using linear probing
        """
        # create a hash value
        hashed = self.hash_function(key,len(self.hash_keys))

        if self.hash_keys[hashed] == None:
            self.hash_keys[hashed] = key
            self.hash_values[hashed] = value
        
        else:
            if self.hash_keys[hashed] == key:
                self.hash_values [hashed] = value
                
            else:
                # create a new hash value to find the next available spot
                new_key = self.rehash_function(hashed, len(self.hash_keys))

                while self.hash_keys[new_key] != None \
                      and self.hash_keys[new_key] != key:

                     # rehahs again
                     new_key = self.rehash_function(new_key,len(self.hash_keys))

                if self.hash_keys[new_key] == None:
                        self.hash_keys [new_key] = key
                        self.hash_values[new_key] = value

                else:
                        #replace the sport of the same hash with new data
                        if self.hash_key[new_key] == key:
                            self.hash_values = value

                    
    def get_data(self,key):
         """
         This function retrieves data from the
         hash table
         """
         search = self.hash_function(key,len(self.hash_keys))
         position = search
         found = False
         stop = False
         value = None
         
         while self.hash_keys[position] != None and \
               not found and not stop:
             
             if self.hash_keys[position] == key:
                 found = True
                 value = self.hash_values[position]
             else:
                 position = self.rehash(position,len(self.hash_keys))
                 if position == start :
                     stop = True
         return value
         


```
