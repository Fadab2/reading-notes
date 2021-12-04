## Big O

- Big O notation is used to measure the performance of an algorithm.
- It the time and resources needed in worse case scenario.
### examples of some Big O and their efficiency/meaning

- O(1) means algorithm will same time of execution regardless of the size of input:
```
bool IsFirstElementNull(IList<String> elements)
{
    return elements[0] == null;
}
```
- O(N) performance grows linearly depending on size of input

```
bool ContainsValue(IEnumerable<string> elements, string value)
{
    foreach (var element in elements)
    {
        if (element == value) return true; 
    }     
    return false; 
}
```
- O(N²) performance is directly proportional to the square of the size of the input.

```
bool ContainsDuplicates(IList<string> elements)
{
    for (var outer = 0; outer < elements.Count; outer++) 
    {
        for (var inner = 0; inner < elements.Count; inner++) 
        { 
            // Don't compare with self 
            if (outer == inner) continue;             
            
            if (elements[outer] == elements[inner]) return true; 
        }
    }    
    return false;
}
````
- O(2^N) growth is exponential and is doubled with the addition to the input.
```
int Fibonacci(int number)
{
    if (number <= 1) return number;
       
    return Fibonacci(number - 2) + Fibonacci(number - 1); 
}
```
### Logarithms

- Binary search is an efficient  algorithm that works in sorted data sets. It takes the middle number of the set and keeps moving left or right depending on the number value until it finds the target value or it doesn't find it. Its Big O is described as O(log N) in which double the size of input has little effect on performance as the algorithm works by splitting the data in half every time.

## Names and Values in Python
- Python underlying mechanisms are simple, but can be surprising.
- You can get around Python without fully understanding the actual mechanism.
- We assign values to names so the names refer to values.
- many names can refer to the same value
- if two names pointing to the same value we can reassign a new value to a name and won't affect the other name's value. but if we change the value then both name will have the updated value.
- values are deleted when no name is point to them.
- assignment don't copy values, but point to the existent value.
- immutable values are values that can't be changed.
- many things like lists/dictionaries are references.
- better to not mutate values, but write functions and that mutate and return a new value.
- Python is dynamically typed and any name can refer to any value (type) at anytime.
- names have no type, but values do have type.



#### References:

[A beginner's guide to Big O Notation](https://rob-bell.net/2009/06/a-beginners-guide-to-big-o-notation)

[Ned Batchelder - Facts and Myths about Python names and values](https://www.youtube.com/watch?v=_AEJHKGk9ns)



[Back to Home](README.md)