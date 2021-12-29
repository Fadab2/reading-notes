# Python Scope:
* The scope of a name or a variable is where in the program you can access the it.
* Every name has a scope in where it will be visible.
* Understanding scope helps us avoid name collisions.
* Python scope LEGB rule stands for Local, Enclosing, Global and Built-in and used to resolve names.
* Global scope: names available to all your code.
* Local scope: names only available to code within the scope, a block of code eg.
* Where you define your name determines its scope/visibility.
* Python stores names’ and their scope using dictionaries.

Functions Local Scope
* Function scope is created every time a function is called.
* Function’s arguments and variables that are assigned inside a function exist within that function.
``` 
def func(num):
	x = num * 10
```
if we try to access x or num outside the function we will get an error of “not defined.
* Functions help us avoid collision as the variables have local scope so we can use same name in different functions.
* When functions are nested we can only access them through the outer function as the inner functions have scope within that inner function.

Modules: Global Scope
* Variables/names that are defined on the top of the python file have global scope.
* We can access, reference the values of global variable/names from anywhere in the program.
```
	x = 10
	def func():
		return x
```
Even though x is defined outside the function the function can access it.
* To make a variable global without declared it on the top of the file, we need to use the global statement.
* We cannot change the value of global variable from inside a function.
* Modifies global variables after an assignment is not a good practice

The Built-in Scope
* Python built-in are automatically loaded in the global scope and can be used without importing any module.
* Python 3 has 152 names that can be used without importing, these include exceptions, types, max, sum, sorted etc.
* Built-ins can be redefined/overridden, but will affect all your code.

## The global Statement
* We can declare a name global inside a function using the `global` keyword. This will update sum in the global scope from inside the function.
```
sum = 0
def update_sum(num):
    global sum
    sum = sum + num
```
## Non local statement
* Nonlocal are accessed from inner functions, but cannot be updated or assigned.
* `non local` key word can be used to declare a name this allows to modify the variable inside the nested function.

## References:

[Python Scope & the LEGB Rule: Resolving Names in Your Code](https://realpython.com/python-scope-legb-rule/)



 <br /> <br /> 
## [<-- Back](README.md) 
