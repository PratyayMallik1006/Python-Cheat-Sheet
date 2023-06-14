# Python Cheat Sheet
## VS Code Extensions:
1. Python - Microsoft
2. Pylint - Microsoft
3. autopep8 - Microsoft (formatter)

# Strings
```py
message="Hello World"

#message length
print(len(message))

# e, charater at index
print(message[1])
# l, charater at index from last
print(message[-2])

# He, slice from start index to index n-1
print(message[0,2])

# Hel, slice from start index to index n-1
print(message[,3])
```
## Formatting Strings
```py
name="Lewis"
place="Ferrari"
full_message = f"Hello {name} Welcome to {place}"
print(full_message)
```
## String Methods
```py
message="hello World"

print(message.upper())
#HELLO WORLD

print(message.lower())
#hello world

print(message.title())
#Hello World

print(message.find("llo"))
#2

print(message.find("hlo"))
#-1

print(message.replace("l","*"))
#he**o World

print("hello" not in message)
#False
```
# Type Conversion
```py
age = input("age:" )
print(int(age)+1)
```
# Falsy Values
```py
0
“”
[]
```
# Logical operators
```py
#and or not

if age>=19 and age<60:
	print("adult")
	
if 18<= age <60:
	print("adult")
```
# Loops
```py
for x in "Python"
for x in ['a','b','c','d']

for x in range(1,10,2)
#1,3,5,7,9
```
## For Else
```py
animals = ["Dog","Cat"]

for animal in animals:
	if animal.startswithh("G"):
		print("Found")
		break
else:
	print("Not found")
```
# Function
```py
def add(a,b=1):
	return a+b
print(add(a=1,2))
```
## Tuple as Argument
```py
def add(*list)
	print(list) # (1,2,3,4)

add(1,2,3,4)
```
## Dictionary as Argument
```py
def add(**user):
	print(user) #{'id':33,'name':'Lewis'}
	print(user["name"]) #Lewis

add(id=33, name="Lewis")
```
# Lists
```py
# Creating lists
letters = ["a","b","c"]
matrix = [[0, 1], [1, 2]]

zeros = [0] * 5
combined = zeros + letters #[0,0,0,0,0,a,b.c.d]

numbers = list(range(20)) [1,2,3 ... 18,19]
```
## Accessing items
```py
letters = ["a", "b", "c", "d"]
letters[0] # "a"
letters[-1] # "d"
```

## Slicing lists
```py
letters[0:3] # "a", "b", "c"
letters[:3] # "a", "b", "c"
letters[0:] # "a", "b", "c", "d"
letters[:] # "a", "b", "c", "d"
letters[::2] # "a", "c"
letters[::-1] # "d", "c", "b", "a"
```

## Unpacking
```py
num=[1,2,3]
first,second,third=num

num=[1,2,3,4,5,6,7,8]
first, second, * other = num # 1,2,[3,4,5,6,7,8]
```

## Looping over lists
```py
for letter in letters:

for index, letter in enumerate(letters):
```

## Adding items
```py
letters.append("e") #adding at end of list
letters.insert(0, "-") #adding at index 0
```
## Removing items
```py
letters.pop() # last of list
letters.pop(0) # at an index
letters.remove("b") #of first occurance element
del letters[0:3]
```
## Finding items
```py
if "f" in letters:
	letters.index("f")
```
## Sorting lists
```py
letters.sort()
letters.sort(reverse=True) # sort order-descending

# Custom sorting
items = [
("Product1", 10),
("Product2", 9),
("Product3", 11)
]

#without lambda function
def sort_item(item):
	retuen item[1]
items.sort(key=sort_item)

#with lambda function
items.sort(key=lambda item: item[1]) # sort by value of item[1]
```

## Map and filter
```py
prices = list(map(lambda item: item[1], items)) #map(function, list)
expensive_items = list(filter(lambda item: item[1] >= 10, items)) #filter(function, list)
```
## List comprehensions
```py
prices = [item[1] for item in items] #like map
expensive_items = [item for item in items if item[1] >= 10] #like filter
```
## Zip function
```py
list1 = [1, 2, 3]
list2 = [10, 20, 30]
combined = list(zip(list1, list2)) # [(1, 10), (2, 20), (3, 30)]
```
# Stack
```py
stack_list=[]
stack_list.append(1)
stack_list.append(2)

last= stack_list.pop()
```
# Queue
```py
from collection import deque
q_list=[]
q_list.append(1)
q_list.append(2)
q_list.popleft()
```

# Tuples
```py
point = (1, 2, 3)
pointt(0) # 1
point(0:2) # (1, 2)
x, y, z = point
if 10 in point:
```
## Swapping variables
```py
x = 10
y = 11
x, y = y, x
```
# Arrays
Works better than lists incase of very large data
```py
from array import array
numbers = array("i", [1, 2, 3]) #i-type code: signed int
```

# Sets
No duplicate items
```py
first = {1, 2, 3, 4}
second = {1, 5}
first | second # union {1, 2, 3, 4, 5}
first & second # intersection {1}
first - second # difference {2, 3, 4}
first ^ second # either in a set but not in both {2, 3, 4, 5}
if 1 in first:
```

# Dictionaries
- Key-Value pairs
```py
point = {"x": 1, "y": 2}
point = dict(x=1, y=2)
point["x"] = 10 # updating at the key
point["z"] = 3 # new key-value
if "a" in point:

point.get("a", 0) # 0 if key "a" not existent
del point["x"]
for key, value in point.items():
```

## Dictionary comprehensions
```py
values = {x: x * 2 for x in range(5)} #{0:0,1:2,2:4,3:6,4:8}
```
# Generator Expressions
More memory efficient than lists, but can't get size
```py
values = (x * 2 for x in range(10000))#Generator object
len(values) # Error
for x in values:
```

# Unpacking Operator

```py
first = [1, 2, 3]
second = [4, 5, 6]
combined = [*first, "a", *second] #[1,2,3,a,4,5,6]
first = {"x": 1}
second = {"y": 2}
combined = {**first, **second} #{x:1,y:2}
```


# Exceptions
```py
# Handling Exceptions
try:
	num=int(input("num: "))
	res=10/num
except (ValueError as err, ZeroDivisionError):
	print("Enter Valid Number")
	print(err)
else:
	# no exceptions raised
finally:
	# cleanup code
	# Raising exceptions
	
if x < 1:
	raise ValueError("Err: Num Can Not Be Less Than Zero”)
# The with statement
with open(“file.txt”) as file:
```
# Classes

## Creating classes
```py
class Point:
		#Constructor
        def __init__(self, x, y):
			self.x = x
			self.y = y
			
		def draw(self): #"self" reference to current object

pnt=Point(1,2) #instance
print(isinstance(pnt,Point)) #True
print(pnt.x) #x=1
```
## Instance vs class attributes
```py
class Point:
        default_color = “red” #Class Level Attributes-static for all instances
		def __init__(self, x, y):
			self.x = x
			
Point.default_color	="blue"
```

## Instance vs class methods
```py
class Point:
        def draw(self):
        
		@classmethod
		def zero(cls): #cls refers to the class
			return cls(0,0)

```
## Magic methods
Called Automatically By Python Interpreter
```py
#Converts Object to String
__str__()

#Comparing two objects
__eq__()
__cmp__()

class Point:
	def __init__(self,x,y):
		self.x=x
		self.y=y
	def __add__(self,other):
		return Point(self.x+othrt.x,self.y+othrt.y)
pnt1=Point(1,2)
pnt2=Point(3,4)
Print(pnt1+pnt2) 
```
## Private members
```py
class Point:
        def __init__(self, x):
	        self.__x = x #x is private member
```
## Properties
```py
class Point:
        def __init__(self, x):
	        self.__x = x
		@property
		def x.getter(self):
			return self.__x
		@property.setter:
        def x.setter(self, value):
        self.__x = value
        
pnt=Point(10)
pnt.x=20 #setter

```
## Inheritance
```py
class ChildClass(BaseClass):

class FileStream(Stream):
        def open(self):
```
## Method Overriding
```py
class BaseClass:
	def __init__(self):
		self.a=1
class ChildClass(BaseClass):
	def __init__(self):
		super().__init__()
		self.b=2
```
## Multiple inheritance
```py
class FlyingFish(Flyer, Swimmer):
```
## Abstract base classes
```py
from abc import ABC, abstractmethod #abc= Abstract Base Class

class Stream(ABC):
        @abstractmethod
		def read(self):
	        pass
class ChildStream(Stream):
	def read(self):
		print("read method")
```
## Inheriting Built-in Types
```py
class MyList(list):
	def pop(self,object)
		print("The removed eleement is:")
		print(super().pop(object))
```
## Named tuples
Instead of using magic method to compare objects
```py
from collections import namedtuple
Point = namedtuple(“Point”, [“x”, “y”])
point = Point(x=1, y=2)
other = Point(x=1,y=2)
print(point == other) #True
```
# Modules (Packages)
Python file of highly related code, that can be imported
1. mamals.py
```py
def eat():
	pass
def walk():
	pass
```
2. Main.py
```py
from mamals import eat, walk
import birds

eat()
walk()

birds.fly()
```
## Compiled Python Files
Upon importing module, python saves compiled file in folder "\_\_pycache__" to speed up module loading

## Importing from other directories
1. animal(folder):
- mamals.py
- \_\_init__.py (no code required)
2. Main(folder)
- main.py
```py
import animals.mamals
from animals.mamals import walk
from animals import mamals
```
## dir Function
To list all attributes and methods of a module
```py
from animals import mamals
print(dir(mamals))
 
```
