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


a development process where you write tests for tasks before you even write the code to implement those tasks.

