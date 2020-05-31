# Software Engineering Practices

* Clean and modular code
* Code efficiency
* Documentation
* Version Control

## Clean
Readable , simple, consise

## Modular
* functions
* modules
* reuse
* dry 
* fewer arg,parameter

## Refactoring
Which function to modularize
Restructure code to improve internal structure w/o changing external functionality

* Reduce workload
* Easy to maintain
* Reuse
* Better developer

## Writing clean code
 * DRY - dont repeat yourself
 * 4 indent
 * blank
 * 79 char pep 8
 
 ## Efficient code
 refactor to improve efficiency to make it clean and modular 
 
 objective
 * reduce run time
 * reduce space in memory
 
 **Optimizing Code**
 
 sets faster than lists [sets over lists](https://stackoverflow.com/questions/8929284/what-makes-sets-faster-than-lists/8929445#8929445)
 ```
import time
 
with open('all_books_published.txt') as f:
   recent_books = f.read().split('\n')
   
with open('all_coding_blocks') as f:
   coding_books = f.read().split('\n')
   
start = time.time()
recent_coding_books = []

for book in recent_books:
 if book in coding_books:
   recent_coding_books.append(book)
  
 'Duration: {} seconds'.format(time.time()-start())
 ```
 
## Documentation
Additional text or illustrations that comes with or is embedded in software code

* Clarify complex parts of code
* Navigate code easily
* Describe use and purpose of components

**Types of Documentaions**
* Line level
    * In-line comments
* Function or module level
    * Docstring explain function or module 
* Project level
    * for getting others to understand why and how your code is relevant to them, whether they are potentials users of your project or developers who may contribute to your code. 
    
    * At a minimum, this should explain what it does, list its dependencies, and provide sufficiently detailed instructions on how to use it. You want to make it as simple as possible for others to understand the purpose of your project, and quickly get something working.





