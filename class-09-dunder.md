# Dunder Methods

* Dunder methods, also know as magic methods are predefined methods we can use enhance our classes.
* Dunder methods start and end with double underscore "dunder" `__init__`, `__str__`, `__mul__`, `__sub__` etc
* Dunder methods help us imitate Python's built-in methods.
* Dunder methods can be used to add functions like len(), siz(), mathematical operation etc to our own classes that don't come with this functions.
```
class LenSupport:
    def __len__(self):
        return 42

    obj == LenSupport()
    len(obj)
    42
```
* Knowing how to use dunder methods is important and makes code more Pythonic.
* `__repr__` used for a string representation of an object.
* `__str__` is used for string representation to be displayed for enduser.

```
 def __repr__(self):
        return 'Account({!r}, {!r})'.format(self.owner, self.amount)

    def __str__(self):
        return 'Account of {} with starting amount: {}'.format(
            self.owner, self.amount)

```
* Dunder methods can be used to create iteration, indexing, etc as shown below:
```
class Account:
    def __len__(self):
        return len(self._transactions)

    def __getitem__(self, position):
        return self._transactions[position]
```

## Operator Overload

* Operator overloads are dunder methods to add operations such as addition, subtraction, comparison etc: `__add__`, `__eq__`, `__lt__`
* We can make our objects callable by implementing the `__call__` dunder method.

## Context Manager Support and the With Statement
* Context manager is a protocol that helps our object to be used with the `with statement` by adding `__enter__` and `__exit__` dunder methods to our object.

# Basic Statistics in Python — Probability
* Probabilityy is used to answer the question of "what is the chance of something or an event happening".
* Example: the chance of flipping heads or tails when tossing a coin is 50/50 as there are only two possible outcomes.
* The more data or trials we perform the more we will approach the more our probability improves.
* In some cases there is not an easy way to calculate probability as in the coin tossing example so we have statistics that provides us with tools such as mean, standard deviation etc that we can utilize.
* A normal distribution is a particular distribution of the probability across all of the events on the x-y axis. x-axis takes the values of events while the y-axis is the probability associated with each even from 0 to 1.
* Three Sigma Rule 68-95-99.7 rule, shows the distance from mean.
* Z-score is a way to calculate how many standard deviation from mean is a given data.

## References:

[Enriching Your Python Classes With Dunder (Magic, Special) Methods](https://dbader.org/blog/python-dunder-methods)
[Basic Statistics in Python — Probability](https://www.dataquest.io/blog/basic-statistics-in-python-probability/)



 <br /> <br /> 
## [<-- Back](README.md) 
