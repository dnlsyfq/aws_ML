Object-oriented programming has a few benefits over procedural programming
object-oriented programming allows 
* to create large, modular programs that can easily expand over time;
* hide the implementation from the end-user.




* class : a blueprint consisting of methods and attributes

* objects : object - an instance of a class

* attribute - a **descriptor** or characteristic. Examples would be color, length, size, etc. These attributes can take on specific values like blue, 3 inches, large, etc.

* method - an **action** that a class or object could take


* encapsulation - one of the fundamental ideas behind object-oriented programming is called encapsulation: you can combine functions and data all into a single entity. In object-oriented programming, this single entity is called a class. Encapsulation allows you to hide implementation details much like how the scikit-learn package hides the implementation of machine learning algorithms.


### Set and Get methods

```
class Shirt:

    def __init__(self, shirt_color, shirt_size, shirt_style, shirt_price):
        self._price = shirt_price

    def get_price(self):
      return self._price

    def set_price(self, new_price):
      self._price = new_price

    def change_price(self, new_price):
      self.price = new_price * 0.81 # convert dollars to Euros

shirt_one.change_price(10)
```


---

### Class

class is a template for a data type. 

* describes the kinds of information that class will hold and how a programmer will interact with that data. 
* define a class using the class keyword. 
* PEP 8 Style Guide for Python Code recommends capitalizing the names of classes to make them easier to identify

```
class CoolClass:
  pass
```

---

### Instantiation

class must be instantiated. In other words, we must create an instance of the class.
Instantiating a class looks a lot like calling a function.

```
cool_instance = CoolClass()
```

---

### Object-Oriented Programming

A class instance is also called an object. The pattern of defining classes and creating objects to represent the responsibilities of a program is known as Object Oriented Programming or OOP.

Instantiation takes a class and turns it into an object, 

*To check which class object is
```
type(cool_instance)
```

### Class Variables

When we want the same data to be available to every instance of a class we use a class variable. A class variable is a variable that’s the same for every instance of the class.

```
class Musician:
  title = "Rockstar"

drummer = Musician()
print(drummer.title)
```
### Methods

Methods are functions that are defined as part of a class. The first argument in a method is always the object that is calling the method. Convention recommends that we name this first argument self. Methods always have at least this one argument.

```
class Dog:
  dog_time_dilation = 7

  def time_explanation(self):
    print("Dogs experience {} years for every 1 human year.".format(self.dog_time_dilation))

pipi_pitbull = Dog()
pipi_pitbull.time_explanation()
```

### Methods with Arguments

Methods can also take more arguments than just self
```
class DistanceConverter:
  kms_in_a_mile = 1.609
  def how_many_kms(self, miles):
    return miles * self.kms_in_a_mile

converter = DistanceConverter()
kms_in_5_miles = converter.how_many_kms(5)
print(kms_in_5_miles)
```

### Constructor 
Methods that are used to prepare an object being instantiated are called constructors.

* __init__ method 

```
class Shouter:
  def __init__(self):
    print("HELLO?!")

shout1 = Shouter()
# prints "HELLO?!"
```
```
class Shouter:
  def __init__(self, phrase):
    # make sure phrase is a string
    if type(phrase) == str:

      # then shout it out
      print(phrase.upper())

shout1 = Shouter("shout")
# prints "SHOUT"

```

### Instance Variables

each instance of a class can hold different kinds of data.

The data held by an object is referred to as an instance variable. Instance variables aren’t shared by all instances of a class — they are variables that are specific to the object they are attached to

```
class FakeDict:
  pass
  
fake_dict1 = FakeDict()
fake_dict2 = FakeDict()

fake_dict1.fake_key = "This works!"
fake_dict2.fake_key = "This too!"


working_string = "{} {}".format(fake_dict1.fake_key, fake_dict2.fake_key)
print(working_string)
prints "This works! This too!"
```
### Attribute Functions

Instance variables and class variables are both accessed similarly in Python. This is no mistake, they are both considered attributes of an object. If we attempt to access an attribute that is neither a class variable nor an instance variable of the object Python will throw an AttributeError.

```
class NoCustomAttributes:
  pass

attributeless = NoCustomAttributes()

try:
  attributeless.fake_attribute
except AttributeError:
  print("This text gets printed!")
  

hasattr(attributeless, "fake_attribute")
# returns False

getattr(attributeless, "other_fake_attribute", 800)
# returns 800, the default value

```

### Self

```
class SearchEngineEntry:
  def __init__(self, url):
    self.url = url

codecademy = SearchEngineEntry("www.codecademy.com")
wikipedia = SearchEngineEntry("www.wikipedia.org")

print(codecademy.url)
# prints "www.codecademy.com"

print(wikipedia.url)
# prints "www.wikipedia.org"
```
```
class SearchEngineEntry:
  secure_prefix = "https://"
  def __init__(self, url):
    self.url = url

  def secure(self):
    return "{prefix}{site}".format(prefix=self.secure_prefix, site=self.url)

codecademy = SearchEngineEntry("www.codecademy.com")

print(codecademy.secure())
# prints "https://www.codecademy.com"

print(wikipedia.secure())
# prints "https://www.wikipedia.org"
```

```
class Circle:
  pi = 3.14
  def __init__(self, diameter):
    print("Creating circle with diameter {d}".format(d=diameter))
    # Add assignment for self.radius here:
    self.radius = diameter/2

  def circumference(self):
    return 2 * self.pi  * self.radius


medium_pizza = Circle(12)
teaching_table = Circle(36)
round_room = Circle(11460)

print(medium_pizza.circumference())
print(teaching_table.circumference())
print(round_room.circumference())
```

### __repr__

dunder method called __repr__. This is a method we can use to tell Python what we want the string representation of the class to be. __repr__ can only have one parameter, self, and must return a string.


```
class Employee():
  def __init__(self, name):
    self.name = name

  def __repr__(self):
    return self.name

argus = Employee("Argus Filch")
print(argus)
# prints "Argus Filch"
```

### Inheritance

base class is called a parent class. In these terms, the class inheriting from it, the subclass, is also referred to as a child class.

```
class User:
  is_admin = False
  def __init__(self, username)
    self.username = username

class Admin(User):
  is_admin = True
```
override a method definition is to offer a new definition for the method in our subclass.
An overridden method is one that has a different definition from its parent class

```
```
