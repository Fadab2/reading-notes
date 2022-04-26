
# Pythonisms

### Dunder Methods
Dunder methods are special methods that lets you emulate the behavior of built-in methods. Dunder methods start and end with a double underscore as in ` __init__` or `__str__`
* Dunder methods can be used inside classes to give or add more features such as getting the length of an object by including the `def __len__(self)` method. Some dunder method examples:
* `__getitem__` to slice lists
* `__len__`  to get length of an object
* `__init__`   to construct objects
* `__repr__` to get string representation of an object
* `__str__` to get a printable string representation of an object.
* `__reversed__` to iterate in reverse order
* `__call__` to make an object callable
* `__eq__` and `__lt__` to compare values are equal or less than

example:
```
from functools import total_ordering

@total_ordering
class Account:
    # ... (see above)

    def __eq__(self, other):
        return self.balance == other.balance

    def __lt__(self, other):
        return self.balance < other.balance
```


### Iterators

* `__iter__` and `__next__` are dunder methods that make a Python object iterable as below in two different classes:
```
class Repeater:
    def __init__(self, value):
        self.value = value

    def __iter__(self):
        return RepeaterIterator(self)

class RepeaterIterator:
    def __init__(self, source):
        self.source = source

    def __next__(self):
        return self.source.value
```
* `iter` sets up and retrieves the iterator object
* `next` repeatedly fetches values.
The above code can be shorter and more concise by adding the `__next__` to the Repeater class as below:
```
class Repeater:
    def __init__(self, value):
        self.value = value

    def __iter__(self):
        return self

    def __next__(self):
        return self.value
 ```
 Both above examples run forever. To fix the infinite loop we re-write our code as below to keep track of the loop and stop when specific cases are met:
 ```
 class BoundedRepeater:
    def __init__(self, value, max_repeats):
        self.value = value
        self.max_repeats = max_repeats
        self.count = 0

    def __iter__(self):
        return self

    def __next__(self):
        if self.count >= self.max_repeats:
            raise StopIteration
        self.count += 1
        return self.value
```
### Generators
Generators are a simpler way to write iterator. Generators make our above long iterator infinite code into:
```
def repeater(value):
    while True:
        yield value
```
Still infinite, but way shorter.
We can re-write our BoundedRepeator iterator class using generators as below:
```
def bounded_repeater(value, max_repeats):
    count = 0
    while True:
        if count >= max_repeats:
            return
        count += 1
        yield value
```
<br />

### References

[What Are Dunder Methods?](https://dbader.org/blog/python-dunder-methods)

[Python Iterators](https://dbader.org/blog/python-iterators)

[What Are Python Generators?](https://dbader.org/blog/python-generators)

<br />

## [<-- Back to home](README.md)
