============================================
# Topics
- Functions, recursion
- lambda - Map/filter
- OOP & POP
- Class & objects
- user-built Module

---
# Functions
- A function is a block of code that performs a specific task.
- Suppose you need to create a program to create a blue circle.
- You can create two functions to solve this problem:
	- a. A function that create a circle function
	- b. A function that create a color function
- Dividing a complex problem into smaller chunks makes our program easy to understand and reuse.

## Types of function
- there are two types of function in Python programming:
	- Standard library functions - are built-in functions in Python that are available to use.
		- almost all keywords are functions
		- print(), len(), input()...
	- User-defined functions - we can create our own functions based on our requirements.

----

## Creating Functions
Syntax: 
```python
def(means define) fun_name (argt):
	# function body
```

- Functions have to be CALLED to work. Thing function like some skilled person, plmbers can do water pipe problems, their specific task is fixing broken pipes. So, if i need to fix my plumber I have to call the plumber right! => So python functions also have to be called 


## Function Arguments
- are used to take value while calling and insert it inside the function.
- its recommended to give them default value when writing a large code
- argument is a must when calling a function if its input is needed during EXECUTION
```python
def display(value):
	print(f"The value u entered is: {value}")
user_input = input("Enter a number: ")
display(user_input)



```

----

## Return Statement
- A python function may or may not return a value.
- If we want our function to [return some value to a function call], we use the 'return' statement.
-<span style="color:rgb(255, 192, 0)"> Returned to the function</span>
- when u include a return statement you DONT ONLY just call the function
	- but you need to PRINT IT!!!
		- [print(fun(argt))]
- `return f"the value is:{aka}" 
	- NO PARENTHESIS

```python
def add(num1,num2):
	return num1+num2
	
sum= add(2,3)
print(sum)
or
print(add(2,3))
```


- as i told you every things are functions on python
	- so print() is a function also input() is len(), everything
	- when we do `print(hello)` we are calling the function and giving it an argument.

```python
def power(base, exponent):
	result = base ** exponent
	return result

base = int(input("enter a base number: "))
exponent = int(input("Enter its exponent: "))  

print(power(base, exponent))
```


----

# Recursion
- Recursion is process of defining something in terms of itself.
- In python, we know that a function can call other functions. It is even possible for the function to call itself. These types of construct are termed as recursive functions.

```python
def factorial(x):
	if x == 1:
		return 1
	else:
	return (x * factorial(x-1))
print(factorial(4))
```


## Advantages of Recursion
1. Recursive functions make the code look clean and elegant
2. A complex task can be broken down into simpler sub-problems using recursion.
3. Sequence generation is easier with recursion than using some nested iteration.

## Disadvantages of Recursion
1. Sometimes the logic behind recursion is hard to follow through
2. Recursive calls are expensive (insufficient) as they take up a lot of money and time
3. Recursive functions are hard to debug


---

# Anonymous/lambda Function
- if function doesn't have name, it is called lambda function/Anonymous
- If you have 1 line code to return you dont need to def a function,
- a lambda function is a special type of function without the function name.
- Syntax: 
```python
lambda argument(s): expression /can be return value or print/
		**** the return value can be a function applied to that variable
```
- we use lambda keyword instead of def


```python
def greet():
	return "Hello World"	
print (greet())


greet = lambda : print ("Hello World")
greet() # Call the lambda

```

```python
def mx(x,y):
	if x > y:
		return x
	else:
		return y
print (mx(2, 3))

INSTEAD USE

mx = lambda x,y: x if x>y else y
print (mx(2,3))
```

```python
number = lambda a,b: a+b
print (numbers(2,3)) => BECAUSE IT IS RETURNED, PRINT IT
```

-----

# Function takers function
- or functional programming
- Filter, map & reduce takes a<span style="color:rgb(255, 192, 0)"> f</span><span style="color:rgb(255, 192, 0)">unction as an argument.</span>

## 1. Filter()
- used to filter or search some functions from sequences.
	- 
	nums = [3, 2, 6, 8, 2, 91]
	evens = list(filter(lambda n: n%2 == 0, nums))
	
	list() - changes data type to [] list

## 2. Map Function
- apply same function to each element of a sequence
- If you want to do a doubling equations on a list of numbers.
- take some list/iterable object and apply a function to every single value inside of it.
```python
n = [4, 3, 2, 1]
print(list(map(lambda x: x**2, n)))
               ______________  __
                 Function      List - to be iterated through by map
```

## The Append Keyword
- This keyword used to add new element to an existing LIST
- Syntax:
	- mylist.append("new Element.")

```python
# EXCERCISE

lili = []
for i in range (5):
	nums = int(input("Enter a number: "))
	lili.append(nums)

print(lili)
  
even = filter(lambda num: num % 2 == 0, lili)
nums = list(map(lambda num: num + 15, even))
print(nums)
```


==P2==

# Object-Oriented Programming/OOP
- Python is an object oriented programming. This means more things in python are objects.
- Objects<span style="color:rgb(255, 192, 0)"> are anything which can have action and name.</span>
- Objects have attributes (properties) and methods (action or functions)
- Eg. My Computer is an object because, it have....
	- Attribute: name, size, cpu, ram...
	- Behavior: Running games, playing music, displaying texts...

# Python Class
- Class is simply <span style="color:rgb(255, 192, 0)">a place where we create our Object's </span>
		- ATTRIBUTE - can be properties, AND 
		- BEHAVIOR 

- it is like a<span style="color:rgb(255, 192, 0)"> template</span>
- A CLASS IS A BLUEPRINT FOR THAT OBJECT.
- Syntax:
```python
class Computer:
	# Creating Attributes
	name = ""
	cpu = ""
```
- After you create the Blueprint, now you can create the objects based on your class
- On the above example we created Class computer and gave it an attributes of name, cpu
- Conventionally, <span style="color:rgb(255, 192, 0)">class Names start with capital letter</span>

- Creating a Class called Flower, with attributes of the flower like petals, stem, leaf
	- Based on our flower CLASS, we can create different types of flowers in this case that is called different OBJECTS

---

# Creating Objects
- You can create many Objects based on 1 class.
- Here we created 2 Objects called
	- Nathan_Computer
	- Alemayehu_Computer
- Syntax:
	- Var = classname()
	- Var.attribute = "value"

```python
# Creating an Object based on the blue print
Nathan_Computer = Computer()
Nathan_Computer.name = "Hp laptop"
Nathan_Computer.cpu = "Intel Core i5"

# Creating another object
Alemayehu_Computer = Computer()  .name    .cpu

print(f"Nathan's Computer Name is called {Nathan_Computer.name}. \n It is {Nathan_Computer.cpu}")
```

## Lets check the type() of our object

```python
# Number 1
Nathan_Computer = Computer()
print(type(Nathan_Computer))

# Output: <<lass '__main__.computer'>

# Number 2
a=4
print(type(a))

# Output: <class 'int'>
```


- When we check Our type it is similar with type of int, both are classes,
- 'a' and 'Nathan_Computer' are objects
- computer and int are classes
---

# Giving Behaviors == Creating Methods
- Functions are called methods of OOP
- Syntax on calling
	- classname.method(object) OR
	- objectname.method()

- Creating a behavior run, which is 1 behavior of my computer. and have parameter of "self"
- Self is the object name on OOP you have to declare it.
```python
class computer:
# Creating Attributes
	name = ""
	cpu = ""

# Creating Behavior
	def run(self):
		return "BIOS" is G00d!"

#Creating an Object based on the blue print
Nathan_Computer = computer()
Nathan_Computer.name = "Hp laptop"

print(f"Running: {computer.run(Nathan_Computer)})
```

```python
# EXCERSIE
class human:
	name = ""
	age = ""
	grade = ""

	def running(self):
		return "I can run!"
	def dancing(self):
		return "I can dance"
	def eating(self):
		return "I can eat!"

human1 = human()  # Creating Object
human1.name = "Nathan"
human1.age = "22"
human1.grade = "3"
  
print(f"My name is {human1.name}\n I am {human1.age} years old. \n I am Grade {human1.grade} student \n My skills are: {human1.running()}, {human1.dancing()}, {human1.eating()}")

# Output: My name is Nathan
#         I am 22 years old. 
#         I am Grade 3 student 
#         My skills are: I can run!, I can dance, I can eat!
```

---

# Python Constructors
- Earlier we assigned a default value to a class attribute.
```python
class Computer:
	name = ""
	cpu = ""
```

- However, we can also initialize values using the constructors.
```python
class Bike:
	# Constructor function
	def __init__(self, name = "", age = ""):
		self.name = name
		self.age = age
```
- Here, `__init__()` is the constructor method that is called whenever a new object of that class is instantiated.
- The constructor above initializes the value of the [name] attribute. We have used the [self.name] to refer to the [name] attribute of the [bike1] object. -> it is like 2 variables 1 is from outside([name]) the class and the other is from inside ([self.name]) class
- If we use a constructor to initialize values inside a class, we need to pass corresponding value during the object creation of the class.
```python
Nathan_Computer = Computer()
Nathan_Computer.name = "Hp laptop"

VS

bike1 = Bike("Mountain Bike")
```

---

# Python Inheritance
- is a way of creating new class with some properties of existing class.
- there is 
	- base class
	- derived class
- Syntax
	- class newclass(oldclass):
		- ....

```python

```
# Python Encapsulation
- Encapsulation is Feature of OOP, That refers to bundling of attributes and methods inside a single class.
- Encapsulation allows for better control and protection of the data, ensuring that it is accessed and modified only through specified methods.

# Package installing
- we use pip to install tools so, on terminal
	- [pip install packagename]


# Package using
- On python, there are a lot of packages to use them, we simply
	- [import packagename]
- Each packages have their own classes and methods so we have to do more studies about those packages.
```python
import sys

a = sys.argv[2]
```
- Here we imported sys package and from that package we added the methods argv, and creating an object 'a'
- From now on when you want to learn website dev with python it is just learning the package. -Django, flask, panda, numpy