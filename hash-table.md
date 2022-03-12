# Hash Table
Hashtables are a data structure that utilize key value pairs. Where every node has both key and a value.
* Hashtable, is used to determine the index of the array.
* Buckets - A bucket is what is contained in each index of the array of the hashtable. Each index is a bucket. An index could potentially contain multiple key/value pairs if a collision occurs.
* Collisions - A collision is what happens when more than one key gets hashed to the same location of the hashtable.
Hashtable is used to:
* Hold unique values
* Dictionary
* Library

The storing of key data structure helps to retrieve the value quickly with time complexity of O(1). By taking advantage of arrays O(1) read access. It uses a hash function to place items at a specific locaton with an index based off its key.
### Creating a Hash

1. Add or multiply all the ASCII values together.
2. Multiply it by a prime number such as 599.
3. Use modulo to get the remainder of the result, when divided by the total size of the array.
4. Insert into the array at that index.

```
Key = "Cat"
Value = "Josie"

67 + 97 + 116 = 280

280 * 599 = 69648

69648 % 1024 = 16

Key gets placed in index of 16. 
```
Cat is placed in index 16 with corresponding value "Josie".
* Each index holds a data bucket that stores key/value pairs.
* All buckets are `null` until filled a hashcode that matches the index.

### Collisions
* If two or more keys produce the same index in an array collision occurs.
* We can avoid collision by changing the initial state of the buckets from null as a LinkedList so that their values can be stored as a node in case of collision.
And example of a collision is produced by hasshing `hashMap.Add("Pioneer Square", 98104);`
`hashMap.Add("Alki Beach", 98116);` as both will be stored in bucket 92 and when we try to get a value using `.get("Pioneer Square")` We search will produce two different zip code and won't know which one to return.

### Calculating hashes and indexes by summing the ascii values of each character
```
SUM HASHED: Pioneer Square = 1379
SUM HASHED: Alki Beach = 884
SUM HASHED: U District = 955

BUCKET SIZE=99
SUM INDEX: 1379 % 99 = 92
SUM INDEX:  884 % 99 = 92
SUM INDEX:  995 % 99 = 64
```

### Calculating hashes and indexes by multiplying the ascii values of each character
```
MULT HASHED: Pioneer Square = 599126016
MULT HASHED: Alki Beach = 1062823936
MULT HASHED: U District = 578867200

BUCKET SIZE=99
MULT INDEX:  599126016 % 99 = 93
MULT INDEX: 1062823936 % 99 = 31
MULT INDEX:  578867200 % 99 = 43
```

### Bucket Sizes
The size of the buckets matters as:
* Few buckets will produce dense and full with possilbe collisions as below:
```
Bucket 0: [{Renton: 98055} --> {Capital Hill: 98102} --> {Greenwood: 98103} --> {Greenlake: 98103} --> {Pioneer Square: 98104} --> {University District: 98105} --> {Columbia City: 98118}]
Bucket 1: [{Bellevue: 98005} --> {Seattle: 98101}]
Bucket 2: [{Mercer Island: 98040} --> {Alki Beach: 98116} --> {Northgate: 98125}]
Bucket 3: [{Downtown: 98101} --> {Laurelhurst: 98105} --> {Bainbridge Island: 98110} --> {Magnolia: 98199}]
Bucket 4: [{Kirkland: 98033} --> {Lynnwood: 98037} --> {Ballard: 98107} --> {Queen Anne: 98109} --> {West Seattle: 98116}]
Bucket 5: [{International District: 98104} --> {Mount Baker:98144}]
Bucket 6: [{Redmond: 98052} --> {Freemont: 98103} --> {South Lake Union: 98109} --> {Madrona: 98110} --> {Belltown: 98121}]
```
* Too many buckets will very sparse with extra empty space as below:
```
Bucket 0: []
.
.
Bucket 10: []
Bucket 11: []
Bucket 12: [{South Lake Union: 98109}]
Bucket 13: [{Madrona: 98110}]
Bucket 14: []
Bucket 15: []
Bucket 16: [{Magnolia:98199}]
Bucket 17: []
Bucket 18: []
Bucket 19: [{Greenlake:98103}]
Bucket 20: [{Redmond:98052}]
Bucket 21: []
Bucket 22: []
Bucket 23: []
Bucket 24: [{Kirkland:98033}]
Bucket 25: []
Bucket 26: []
Bucket 27: []
Bucket 28: [{Bellevue:98005}]
Bucket 29: [{Seattle:98101}]
Bucket 30: []
Bucket 31: []
Bucket 32: []
Bucket 33: []
Bucket 34: []
Bucket 35: []
Bucket 36: [{Renton:98055}]
Bucket 37: [{Queen Anne:98109}]
Bucket 38: [{Capital Hill:98102}]
Bucket 39: []
Bucket 40: [{Freemont:98103}]
.
.
Bucket 47: [{Greenwood:98103}  --> {Belltown:98121}]
Bucket 48: []
Bucket 49: [{Northgate:98125}]
Bucket 50: [{Bainbridge Island:98110}]
Bucket 51: []
Bucket 52: []
Bucket 53: [{Mercer Island:98040}]
Bucket 54: []
Bucket 55: []
Bucket 56: []
Bucket 57: []
Bucket 58: [{Mount Baker:98144}]
Bucket 59: []
Bucket 60: [{International District:98104}]
Bucket 61: []
Bucket 62: []
Bucket 63: []
Bucket 64: []
Bucket 65: [{Columbia City:98118}]
Bucket 66: [{Lynnwood:98037}]
Bucket 67: []
Bucket 68: []
Bucket 69: []
Bucket 70: []
Bucket 71: []
Bucket 72: [{Downtown:98101}]
.
.
Bucket 78: []
Bucket 79: [{University District:98105}]
Bucket 80: []
Bucket 81: []
Bucket 82: []
Bucket 83: []
Bucket 84: [{West Seattle:98116}]
.
.
Bucket 90: [{Laurelhurst:98105}]
Bucket 91: []
Bucket 92: [{Pioneer Square: 98104} --> {Alki Beach:98116}]
Bucket 93: []
Bucket 94: []
Bucket 95: []
Bucket 96: [{Ballard:98107}]
Bucket 97: []
Bucket 98: []
```
* Buckets can start few and automatically increase the size as the load grows.

# Methods:
`Add()`, `Find(key)`, `Contains(key)`, `GetHash('key')`


<br />

## References

[Hash Table](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-30/resources/Hashtables.html)

<br />

## [<-- Back](README.md)
