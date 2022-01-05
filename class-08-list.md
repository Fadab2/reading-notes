# List Comprehensions in Python
* Python provides better way than for loops to handle lists and list comprehension.
* Python's comprehension featueres keeps our code more elegant.
* List comprehension is more powerful and concise for creating lists and has the syntas:
`my_new_list = [ expression for item in list ]`
* List comprehension enables us to perform expressions, conditions in an entrire list in a single like.
* List comprehension is more flexible than for loops and faster.
Example of creating basic list:
```
    numbers = [x for x in range(10)]
    print(numbers)

    prints: numbers 0-9
```
 Above code generate a list of numbers in range and stores in numbers.

Example of creating a list using for loops vs list comprehension:
```
for x in range(10):
    # raise x to the power of 2
    squares.append(x**2)

print(squares)
[0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
```
using list comprehension:
```
# create a list using list comprehension
squares = [x**2 for x in range(10)]

print(squares)
```
* We can use filters to work with certain parts of the list such as just getting the even numbers.
```
even_numbers = [ x for x in range(1,20) if x % 2 == 0]
```
* List comprehension can make working with strings easier as well:
```
# a list of the names of popular authors
authors = ["Ernest Hemingway","Langston Hughes","Frank Herbert","Toni Morrison",
    "Emily Dickson","Stephen King"]

# create an acronym from the first letter of the author's names
letters = [ name[0] for name in authors ]
print(letters)
['E', 'L', 'F', 'T', 'E', 'S']
```
* We can use Python's built in methods like lower, upper, isdigit inside our list comprehensions to perform different tasks on the data.
* We can parse files using list comprehension;



## References:

[List Comprehensions in Python](https://www.pythonforbeginners.com/basics/list-comprehensions-in-python)

 <br /> <br /> 
## [<-- Back](README.md) 