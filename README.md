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

# Python Standard Libraries
## Random Values
```py
import random

print(random.random()*10) #1 t0 10
print(random.randint(1,10))
print(random.choice([1,2,3,4]) #one random value from list

#suffling
num =[1,2,3,4]
random.shuffle(numbers)

#k length list random values from the string
print(random.choices([1,2,3,4],k=2) #[1,2]

#password generator
print("".join(random.choices("ABCDEFGHI",k=4)))
import string
sample_space=strings.ascii_letters + string.digits
print("".join(random.choices(sample_space,k=4)))

#comma seperated
print(",".join(random.choices("ABCDEFGHI",k=4))) #A,B,C
```
## Timestamps
```py
import time

start = time.time()
some_function()
end = time.time()

duration = end - start
print(duration)
```
## Datetime
```py
from datetime import datetime
import time

dt = datetime(2023,1,1)
dt = datetime.now()

#String to datetime
dt = datetime.strptime("2023/01/01", "%Y/%m/%d")

dt = datetime.fromtimestamp(time.time())
print(dt)

#formating
print(f"{dt.year}/{dt.month}")
print(dt.strftime("%Y/%m"))
```

## Time Delta
Duration
```py
from datetime import datetime, timedelta

dt1 = datetime(2023,1,1)
dt2 = datetime.now()

duration = dt2 - dt1
print(duration)
print("days",duration.days)
print("seconds",duration.seconds)
print("totla_seconds",duration.total_seconds())

dt1 = datetime(2023,1,1) + timedelta(days=1, seconds=2)
```


## Path
```py
from pathlib import Path

Path("C:\\Projects\\Python")

#raw string
Path(r"C:\Project\Python")

#Current Folder
Path()

#relative path
Path("animals/__init__.py")
Path()/"animals"/"__init__.py"
```
## Directories
```py
path=Path("animals/__init__.py")
path.mkdir()
path.rmdir()

#list all files and folders
for p in path.iterdir():
	print(p)

folders=[p for p in path.itedir() if p.is_dir()]
txt_files=[p for p in path.rglob("*.txt)]
```

## Files
```py
path=Path("animals/__init__.py")
path.rename("init.txt")
text_str=path.read_text()
path.write_text("abcd")

#moving files
import shutil

source = Path("animals/__init__.py")
target = Path("birdss/__int__.py")
shutil.copy(source,target)
```
## Zip Files
```py
from pathlib import Path
from zipfile import ZipFile

#Creating New zip File
zip = ZipFile("files.zip","w")
for path in Path("animals").rglob("*.*"):
	zip.write(path)
zip.close()

#Reading from Zip File
with ZipFile("files.zip") as zip:
	print(zip.namelist())
	info = zip.getinfo("animals/__init__.py")
	print(info.file_size)
	print(info.compress_size)
	#Extracting
	zip.extractall("New_Folder")
#"with" syntax doesnot requires close()
```

## CSV Files
Comma Separated value
```py
import csv

#creating CSV File
file = open("data.csv","w")
writer = csv.write(file)
writer.writerow(["cust_id","prod_id","price"])
writer.writerow([1,11,100])
writer.writerow([2,12,100])
file.close()

#reading CSV File
file = open("data.csv","r")
reader = CSV.read(file)
#print(list(reader))
for row in reader:
	print(row)
```

## JSON Files
```py
import json
from pathlib import Path
students=[
	{"id":1,"name":"abc"},
	{"id":2,"name":"def"}
]
data = json.dumps(students)
print(data)

#Creating JSON File
Path("students.json").write_text(data)

#Reading JSON File
info = Path("students.json").read_text()
```

## SQLite Databse
```py
import sqlite
import json
from pathlib import Path

students = json.load(("students.json").read_text())

#Writing into a Databse
conn = sqlite3.conncet("db.sqlite3") #Database Name 
command = "INSERT INTO students VALUES(?,?)"
for student in students:
	conn.execute(command, tuple(student.value()))
conn.commit()
conn.close()

#Reading from a Database
with sqlite3.conncet("db.sqlite3") as conn:
	command = "SELECT * FROM students"
	cursor = conn.execute(command)
	#for row in cursor:
	#	print(row)
	students = list(cursor.fetchall())
```

## Browser
```py
import webbrowser
webbrowser.open("google.co.in")
```
## Template
1. template.html
```html
<html>
<body>
Hello $name, How are you?
</body>
</html>
```
2. main.py
```py
from pathlib import Path
from string import Template

template = Template(Path("template.html"),read_text())
body = template.substitute({"name":"Lewis"})
```

## Emails
- MIME - Multipurpose Internet Mail Extensions
- TLS - Transport Layer Security
```py
from email.mime.multipart import MIMEMultipart
from email.mime.text import MIMEText
from email.mime.image import MIMEImage
import smtplib
from pathlib import Path
from string import Template

template = Template(Path("template.html"),read_text())
body = template.substitute({"name":"Lewis"})

message = MIMEMultipart()
message["from"] = "Lewis Hamilton"
message["to"] = "f1@ferrari.com"
message["subject"] = "Yes"
#message.attach(MIMEText("Body","plain"))
message.attach(MIMEText(body,"html"))
#Image Attachment
message.attach(MIMEImage(Path("Photo.jpg").read_bytes()))

smtp = smtp.SMTP(host="smtp.gmail.com", port=587)
smtp.ehlo()
smtp.starttls()
smtp.login("lewis44@mercedes.com","MyPassword")
smtp.send_messages(message)
print("Sent...")
smtp.close()
```
# Python Package Index (Pypi)
Know more: https://pypi.org/
## pip
To install packages from pypi
```
pip install numpy
pip install --upgrade
pip list
```
## Virtual Environment
- An Environment with custom packages, without interfering with global packages
- Creating environment(folder) with the name "env"
```
python -m venv env
env\bin\activate.bat
deactivate
```
Or
### pipenv
```
pip install pipenv
pipenv install numpy
pipenv --venv
exit
```
## Pydoc
- Checking Package Documentations 
```
pydoc pathlib
```
- Converting Documentation into html file
```
pydoc pathlib.Path
```
- Web View of all documentation in "localhost:8000"
```
pydoc -p 8000
```
# Python Packages

## API
1. CMD
```
pip install requests
```
2. config.py
```py
api_key="api_key_123"
```
3. main.py
```py
import requests
import config

url = "http://api.com/search"
api_key="api_key_123"
headers = {
	"Authorization":"Bearer "+ config.api_key
}
params={
	city="Ooty"
}
response = requests.get(url, headers=headers, params)
print(response)
print(response.json()["temp"])

conditions = response.json()["temp"]
storms =[conditions["weather"] for condition in conditions if condition["weather"]=="storm"]
```
## Twilio to Send Message
Has wrapper above API, as package
1. CMD
```
pip install twilio
```
2. main.py
```py
from twilio.rest import Client

account_sid="abcd"
auth_token="acb"

client = Client(account_sid,auth_token)
client.message.create(
	to"9876543210",
	from="1234567890" #Available in twilio account
	body="hello!"
)
#client.call()
#client.chat()
```
## Web Scraping
1. CMD
```
pip install beautifulsoup4
```
2. Main.py
```py
import  requests
from  bs4  import  BeautifulSoup

response = requests.get("https://stackoverflow.com/questions?sort=MostVotes&edited=true")
soup = BeautifulSoup(response.text, "html.parser")

# class name selected
questions = soup.select(".s-post-summary")

for  question  in  questions:
	print(question.select_one(".s-link").get_text())
	print("Votes:")
	print(question.select_one(".s-post-summary--stats-item-number").get_text())
	print("------")

# print(questions[0].attrs)
# {'class': ['s-post-summary--content-excerpt']}
```
## Browser Automation
### Selenium (testing)
1. CMD
```
pip install selenium
```
2. Install Webdrive
goto: https://pypi.org/project/selenium/

3. Main.py
```py
from selenium inport webdriver

browser = webdriver.Chrome()
browser.get("https://github.com")

#clicking on signin link
signin_link = browser.find_element_by_link_text("Sign in")
signin_link.click()

#inputting username and password
username_box = browser.find_element_by_id("login_field")
username_box.send_keys("lewis44")
password_box = browser.find_element_by_id("password")
password_box.send_keys("myPassword")
password_box.submit()

#confirming if loged into right account
assert "lewis44" in browser.page_source

profile_link = browser.find_element_by_class("user-profile_link")
link_label = profile_link.get_attribute("innerHTML")
assert "lewis44" in link_label

browser.quit()
```
## Working with PDFs
Know more: https://pypi.org/project/PyPDF2/
```py
import  PyPDF2

# read binary
with  open("resume.pdf", "rb") as  file:
	reader = PyPDF2.PdfReader(file)
	print(len(reader.pages))
	page = reader.pages[0]
	page.rotate(90)
	writer = PyPDF2.PdfWriter()
	writer.add_page(page)
	# write binary
	with  open("rotated.pdf", "wb") as  output:
		writer.write(output)
```
## Working with Excel
```py
import  openpyxl

# workbook
wb = openpyxl.load_workbook("data.xlsx")
print(wb.sheetnames)

# wb.create_sheet("Sheet2",0) #index will put before Sheet1
# wb.remove_sheet(sheet)

sheet = wb["Sheet1"]
print(sheet.cell(row=1, column=1).value)
cell = sheet["a1"]
column=sheet["a"]
columns=sheet["a:c"]
matrix=sheet["a1:c3"]
row=sheet[1]
rows=sheet[1:3]

for  row  in  range(1, sheet.max_row+1):
	for  column  in  range(1, sheet.max_column+1):
		cell = sheet.cell(row, column)
		print(cell.value)

#adding row at end
sheet.append([1,2,3])
wb.save("new_data.xlxs")
```
