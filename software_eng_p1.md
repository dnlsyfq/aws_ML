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
 
 
