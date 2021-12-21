# How to use Random Module
* One of the basics of Random module is to generate random numbers.
* Examples of when we use Random Module is when we want the computer to generate for us some random elements within a given range. 
* These element can be part of numbers, a list, a card from a deck, flip a coin etc.

## Random Functions
* Randint: used to generate random integers provided the lowest and highest number as parameters.
for example to print a random number between zero and 10 we use:
```
import random
print(random.randint(0, 10))
```
* Random: is used for a larger numbers by multiplying it by a given number and it generates a float number as in the example below:
```
import random
random.random() * 1000
```
* Choice: Can be used to generate an element out of a list rather than a range of numbers as below:
```
import random
list = ['a', 'b', 'c', 100, 'apples']
random.choice(list)
```
* Shuffle: is used to shuffle elements in a list to make them in random order:
```
from random import shuffle
list = ['a', 'b', 'c', 100, 'apples']
shuffle(list)
```
* Randrange: is used to generate random elements same as randint, but takes a 3rd parameter as a step,example:
```
import random
for i in range(10):
    print(random.randrange(1, 1000, 10))
```
 <br /> 


# Risk Analysis in Software Testing
* Risk analysis is identifying the risks in your application through tests and assigning a level of risk to calculate the impact of the risk.
* Risk analysis at the beginning of the application helps us discover potential areas of risk which helps us to mitigate these risks.
* Some of the possible risks that our software might encounter are:
    * New hardware use
    * New technology use
    * New automation tool use
    * Sequence of code
    * Availability of test resources for the application
* Some unavoidable risks are:
 * Time allocated for testing
 * Issues due to the complexity/size of the application
 * clients delivery urgency
* The above risks can be reducing by: 
    * Risk assessment review meeting
    * Allocate the required resources 
    * Risk assessment database for reference
    * Classify the as high, medium, low


<br /> 

# Test Coverage

* Test coverage is used to find untested code parts.
* Aim for testing all all parts of rather than getting  specific percentage that can be attained using easy tests.
* Some signs of good test coverage are:
    * Less bugs
    * Confidence in changing parts of code without causing bugs.
* Coverage testing analysis helps you find parts of your code that isn't been tested

## References:

[How to use the Random Module in Python](https://www.pythonforbeginners.com/random/how-to-use-the-random-module-in-python)


[What is Risk Analysis in Software Testing and how to perform it?](https://www.edureka.co/blog/risk-analysis-in-software-testing/) 

[Test Coverage](https://martinfowler.com/bliki/TestCoverage.html)


 <br /> <br /> 
## [<-- Back](README.md) 
