# Hash tables
Hash tables, also known as hash maps, are data structures that store key-value pairs. They provide an efficient way to store and retrieve data by using a technique called hashing. In a hash table, keys are mapped to array indices using a hash function. This allows for fast access and retrieval of values associated with a given key.

Here's a step-by-step overview of how hash tables work:

1. Hashing: When a key-value pair is inserted into a hash table, a hash function is applied to the key. The hash function computes a numeric value, called the hash code or hash value, based on the key's contents. The hash code is typically an integer.

2. Array index mapping: The hash code is then mapped to an index in the underlying array structure. This is usually done by taking the hash code modulo the size of the array. The resulting index is where the key-value pair will be stored.

3. Collision handling: Since the hash function can produce the same hash code for different keys (known as a collision), hash tables need a mechanism to handle collisions. There are different collision resolution techniques, including separate chaining and open addressing.

- Separate chaining: In separate chaining, each index of the array contains a linked list or another data structure. When a collision occurs, the new key-value pair is added to the list at the corresponding index. This allows multiple key-value pairs to be stored at the same index.

* Open addressing: In open addressing, when a collision occurs, the hash table looks for the next available slot in the array by following a predetermined sequence of indices. This process continues until an empty slot is found. There are variations of open addressing, such as linear probing, quadratic probing, and double hashing.

4. Retrieval: To retrieve a value from a hash table, the key is hashed using the same hash function. The resulting hash code is used to locate the corresponding index in the array. If there are multiple key-value pairs at that index (due to collisions), the search continues within the data structure associated with that index until the matching key is found or until the end of the data structure is reached.

The main advantage of hash tables is their efficiency in terms of average-case time complexity for insertion, retrieval, and deletion operations. When the hash function distributes the keys evenly across the array, the expected time complexity is O(1) (constant time) for these operations. However, in the worst case, when collisions are frequent and the hash table becomes highly populated, the time complexity can degrade to O(n) (linear time), where n is the number of key-value pairs in the hash table.

Hash tables are commonly used in various applications, such as databases, caches, symbol tables, and many programming languages provide built-in implementations of hash tables or similar data structures to facilitate efficient data management and retrieval.