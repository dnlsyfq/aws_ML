# Software Engineering Part 2

* Write clean and modular code
* Improve code efficiency
* Add effective documentation
* Use version control
> Testing
> Logging
> Code Reviews

## Testing
[Data Science Code Test](https://www.predictiveanalyticsworld.com/machinelearningtimes/four-ways-data-science-goes-wrong-and-how-test-driven-data-analysis-can-help/6947/)[Getting Started Testing](https://speakerdeck.com/pycon2014/getting-started-testing-by-ned-batchelder)
[Video for Getting Started Testing](https://www.youtube.com/watch?v=FxSsnHeWQBY)


Before deployment, code testing.
catch errors and faulty conclusions before they make any major impact.

writing test industry standard and setting .

Poor quality and accuracy of analysis + quality of code can result to:
* Bad encoding
* Inappropriate features
* Unexpected data were breaking assumptions that your statistical models are based on 


### Unit Test
 a type of test that covers a “unit” of code, usually a single function, independently from the rest of the program.
 
 
* Write unit tests
* Tools to improve unit tests


```
def nearest_square(num):
    root = 0
    while(root + 1) ** 2 <= num:
        root += 1
    return root ** 2
    
from nearest import nearest_square

nearest_5 = nearest_square(5)
"Nearest square <= 5: returned {}, corrent answer is 4.".format(nearest_5)
assert(nearest_5 == 4)
```

### Unit Test Advantages and Disadvantages
The advantage of unit tests is that they are isolated from the rest of your program, and thus, no dependencies are involved. They don't require access to databases, APIs, or other external sources of information. However, passing unit tests isn’t always enough to prove that our program is working successfully. To show that all the parts of our program work with each other properly, communicating and transferring data between them correctly, we use integration tests. In this lesson, we'll focus on unit tests; however, when you start building larger programs, you will want to use integration tests as well.

### Pytest
pip install -U pytest

```
nearest.py

def nearest_square(num):
    root = 0
    while(root + 1) ** 2 <= num:
        root += 1
    return root ** 2
    
test_nearest.py
# Create a test file starting with test_

from nearest import nearest_square

# Define unit test functions that start with test_ inside the test file
def test_nearest_square_5():
    assert(nearest_square(5) == 4)
    
---

# working directory
# Enter pytest into your terminal in the directory of your test file and it will detect these tests for you!

$ pytest # python3 -m pytest

```

### Test Drive Development
> Writing tests before developing code to implement tasks
[Ref 1](https://www.linkedin.com/pulse/data-science-test-driven-development-sam-savage/)
[Ref 2](http://engineering.pivotal.io/post/test-driven-development-for-data-science/)
[Ref 3](https://medium.com/uk-hydrographic-office/test-driven-development-is-essential-for-good-data-science-heres-why-db7975a03a44)
[Ref 4](https://docs.python-guide.org/writing/tests/)

a development process where you write tests for tasks before you even write the code to implement those tasks.

```
def email_validator(email):
    if email.count('@') != 0 and email.count('.') != 0:
        return True
    else:
        return False
        
def test_email_validator():
    assert email_validator('juno@email.com') == True
    assert email_validator('juno@email.com') == False
```

* Tests can check for all the different scenarios and edge cases you can think of, before even starting to write your function. This way, when you do start implementing your function, you can run this test to get immediate feedback on whether it works or not in all the ways you can think of, as you tweak your function.

* When refactoring or adding to your code, tests help you rest assured that the rest of your code didn't break while you were making those changes. Tests also helps ensure that your function behavior is repeatable, regardless of external parameters, such as hardware and time.

## Logging
Logging is valuable for understanding the events that occur while running your program.

log well in order :
* to check the cause
* the context
* figure out how to address issue 


> DEBUG - level you would use for anything that happens in the program.
> ERROR - level to record any error that occurs
> INFO - level to record all actions that are user-driven or system specific, such as regularly scheduled operations

```
Good: Failed to read location data: store_id 8324971
```

## Code Reviews
[Ref 1](https://github.com/lyst/MakingLyst/tree/master/code-reviews)
[Ref 2](https://www.kevinlondon.com/2015/05/05/code-review-best-practices.html)

Help catch errors, ensure readibility, check standards are met ,
share knowledge among teams

## Questions

> Is the code clean and modular?
* Can I understand the code easily?
* Does it use meaningful names and whitespace?
* Is there duplicated code?
* Can you provide another layer of abstraction?
* Is each function and module necessary?
* Is each function or module too long?

> Is the code efficient?
* Are there loops or other steps we can vectorize?
* Can we use better data structures to optimize any steps?
* Can we shorten the number of calculations needed for any steps?
* Can we use generators or multiprocessing to optimize any steps? 

> Is the code well tested?
* Does the code high test coverage?
* Do tests check for interesting cases?
* Are the tests readable?
* Can the tests be made more efficient?

> Is the logging effective?
* Are log messages clear, concise, and professional?
* Do they include all relevant and useful information?
* Do they use the appropriate logging level?