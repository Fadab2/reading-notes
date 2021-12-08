# Testing and Modules

## Unit tests
* are a code we write to test that our program produces the right/expected output given an some input.
* in test driven development you write your test before you write your code.
* we should use descriptive names when developing our test unit.
* test file name should be same as module name preceded by `test_`
* test should have its own folder.
* we can use lib pytest to execute tests.
* Example of Python code to test a given name return a female:
```

def test_should_return_female_when_the_name_is_from_female_gender():
    detector = GenderDetector()
    expected_gender = detector.run(‘Ana’)
    assert expected_gender == ‘female’
```

* you can write a better code just by having your test passing in mind.


## if __name__ == “__main__”:
* used when the file is run directly.
* when the file is imported the `__name__ `is set to imported file name eg `__name__ == "__foo__"`


## Recursion
* a function calls itself directly/indirectly to solve some problems.
* recursive  can solve some problems easier.
* base condition is an exit point for the program.
* direct recursion is a function calling itself while indirect recursion is a function calling other function.
* tailed recursive is when the recursive call is executed last.
* memory is allocated to each function call, when base case is reached values are returned to the calling function one by one and memory is freed.
* recursive operations have greater memory/time requirement and it will remain in stack until program finishes and too many function calls.


#### References:

[In Tests We Trust — TDD with Python](https://code.likeagirl.io/in-tests-we-trust-tdd-with-python-af69f47e6932)


[What does the if __name__ == “__main__”: do?](https://www.geeksforgeeks.org/what-does-the-if-__name__-__main__-do/)
[Recursion](https://www.geeksforgeeks.org/recursion/)


[go to home](README.md)