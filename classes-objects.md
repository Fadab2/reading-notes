# Classes and Objects
* Classes are templates to create objects
* Objects are encapsulation of variables and functions into a single entity.
* Objects receive variables and functions from classes.
* In order to create a class we use the `class` keyword followed by the class name starting with a capital letter.
```
class Car:
```
* to assign a class to an object to the Car class we do `myobeject = Car()`
* When we assign a class to an object, that object contains all the variables and functions that are in the class.
* We use the `dot` notation to access variables/functions of a class (`objecname.variable`) (`objectname.function()`)
* We can create as many objects of a class as we need.
* We can modify the class default variables/function values for an object using the by assigning it a new value.
* The (`__init__(self)`) is a special function that is called with class initiation and used to assign values in a class.


# Recursive Functions
* A recursive function is a function that calls itself until some specified base condition is reached.
 * As in below code example, when the base case is reached `n == 1` it exit the recursion.
```
def factorial_recursive(n):
    # Base case: 1! = 1
    if n == 1:
        return 1

    # Recursive case: n! = n * (n-1)!
    else:
        return n * factorial_recursive(n-1)
```
* Most data structures are recursive and can be defined in terms of smaller version of itself.
  


# Pytest Fixtures and Coverage

* Pytest is a library for testing Python code.
* Fixtures are is data to share across test or involve network filesystem.
* We define fixtures using `pytest.fixture` decorator along with a function definition.
* Fixtures are used differently from global variables.



## References:

[Classes and Objects](https://www.learnpython.org/en/Classes_and_Objects)

[Thinking Recursively in Python](https://realpython.com/python-thinking-recursively/)

[Python Testing with pytest: Fixtures and Coverage](https://www.linuxjournal.com/content/python-testing-pytest-fixtures-and-coverage)



[go to home](README.md)