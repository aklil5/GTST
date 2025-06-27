''
- Indexing and slicing {start, stop, step}
- input handling {2 methods}
- Operations
- indentation
- if else
- Errors(Exceptions)
- Error handling
- loops

-----
# Indexing
- on lists, we have seen about index numbers.
	- Positive indexing
	- Negative indexing
- Calling texts by indexed also works for strings and tuples

- calling texts by indexed also works for strings(to extract one character/letter) & tuples(extract one element)
----

# Slicing
- in python it is popssible to access a section of items form the list using the slicing operator [":"], not just a single item.
- Syntax:
	- Mylist [start:stop:step]
- Slicing is indexing syntax that extracts a portion from a list. If a is a list, then a [m:n] returns the portion of a:
	- starrting with m
	- up to but not including n
	- negaative indexing can also be used
- It is more applicable for STRINGS

- Python uses default step as 1, sometimes no need to tell/put it [start:stop] is enough
- also default stopping index is the final, still no need to tell for this kinda purpose

```python
name = ["ethiopia", "banana", "china", "Apple"]
- reverse it
- output [apple, banana]
- output [china, ethiop]
```

There are more writing features
print (name[::])
print (name[-1:0:-2])
- start from -ve    <------
- start from +ve    ----->
print (name[8:-1]) - to include last element use 0 or dont write nothing

----

# User Input handling
- on python there are 2 types of inputs
	- By input function
	- By arguments

1. By input functions,
- syntax: var = input("Text you like to display: ")
- Will accept the input and [stores on variable].

- data accept Starts in the function - AFTER you run the code
- all data he accept is stored as string
- You can change the input type to int() float() eval() str() 
- type(input)
	-  `<class 'str'> -> Default
	- number = int(input("Enter number: "))
	- number = eval(input())
	- number = float(input())


2. Arguments
- This help us to get the input from the command lines
- the CODE is NOT RUN, you write on the terminal
- Shell: [python gtst.py arg1 arg2 arg3
	- on the terminal
	- python (file location )
	- python test.py Nathan Hailu
- Syntax: 

```python
import sys
name = sys.argv[1]
print(f"Hello {name}!")
```

```python
# You can do more inputs
import sys
firstname = sys.argv[1]
lastname = sys.argv[2]
print(f"Hello {firstname}!, Your Father name is: {lastname}.)
```
 - u can create variable until n times
 - var = sys.argv[100]




=======================================================

==P2==

# Operators
- are special symbols that perform operations on variables and values. 
	- Example: print (5 + 6) # 11
- There are lots of operators type on python:
	1. Arithmetic Operators
	2. Assignment
	3. Comparison
	4. Logical
	5. Bitwise
	6. Special 


---

## 1. Arithmetic Operators
- are a simple maths operators
- INPUTS have to be in [int, eval, float] only.
- +, -, *, /, %(modulo), ** (power) 
```python
a = 7
b = 2
print ("Sum: ", a + b)
```

## 2. Assignment
- used to assign values to variables
- You do the arithmetic operators 1st, then the equal sign
	- = -> assignment operator
	- += -> addition assignment
	- %= -> remainder assignment 
```python
print (5%12) # output 5 - Always the first No of a < b
```

## 3. Comparison Operators
- used to compare VARIABLE and return BOOLEAN RESULT
- Boolean means either TRUE or FALSE
	- == (is equal to), !=, >, <, >=, <=

## 4. Logical
- are used to check if an expression is TRUE or FALSE
	- and -> a and b
	- or -> a or b
	- not -> not a

## 5. Bitwise Operators
- Computers work with Binarys
- On our computer everything have a binary value. (also called bit)
- On python there is a keyword called [bin(YourDecimal) eg, bin(10)] this helps to Show you the binary value of Your Decimal
	- the BINARY VALUE is the number after 0b
- True - have value of 1
- False have value of 0
- [Bitwise Operators Used to do maths (Logical operations) on The binary value of The expression].
- There are
	- Compliment (Not) (~)
	- And (&)
	- Or ( | )
	- Xor (^)
	- Left Shift (<<)
	- Right Shift (>>)
- If you work on Cryptography on hacking this is must!

## Complement(NOT) (~)
- it will convert the first value to binary and will reverse each bit then converts to decimal.
- in simple maths, it will add  1 to the number and makes it negative

## AND (&)
- you can add 0 before the binary of any number if it is not 4 digit binary
- bin(7) -> 111, but we can do 0111 too

## OR (|)
- same as AND but the logic operator will be changed.

## XOR (^)
- it is like and, or but the difference of logic here is
	- if they are same = 0, eg 0^ 0 = 0
	- if they are different = 1, eg 0^1 = 1
## Left Shift (<<)
- Every number have 0 at the end => 1.0, 32.0... 
	- 1010.0000
- a<< b => you shift b bits to the left

## Right Shift (>>)
- a>>b => shifting b bits to the right

## Indentations
- Are just a White Space which python uses for some of its function. If there is no proper Indentation error then you are doomed.
## 6. Special
- 

---
# Indentations
- are just white space which python uses for some of its function. If there is no proper indentation error, then you are doomed.

====================================================

==P3==

# If-else Conditions
- In computer programming, we use the if statement to run a block code only when a certain condition is True.
- For example, assigning (A, B, C) based on marks obtained by a student.
	- If the percentage is above 90, assign grade A
	- If the percentage is above 75, assign grade B

- In python, there are three forms of if---else statement.
	1. if statement
	2. if....else statement
	3. if.....elif......else statement

```python
if success() == True:
	celebrate()
while success() == False:
	try_again()
	be_awesome()
```

-----

1. If Statement
- The if statement evaluates condition
	- if condition is evaluated to <span style="color:rgb(255, 192, 0)">True,</span> the code inside the body of if is executed.
	- i=f condition is evaluated to <span style="color:rgb(255, 0, 0)">False, </span>the code inside the body of if is skipped.
- Synt:
```python
if condition:
	# body of if statement
```

- <span style="color:rgb(255, 192, 0)">.isdigit() </span>checks if the value is number.

2. If...else statement
- An if statement can have an optional else clause.
- The syntax of if....else statement is: 
```python
if condition:
	print()
else:
	print()
```

3. if.....elif......else statement
- Here
	1. if **condition1** evaluates to True, **code block 1** is executed.
	2. if **condition1** evaluates to False, **condition2** is evaluated.
	3. if **condition2** evaluates to True, **code block 2** is executed.
	4. if **condition2** evaluates to False, **code block 3** is executed.

## Nested if statements
- We can use an if statement inside of an if statement. This is known as a nested if statement.
- Here two requirements have to be true to 

```python
# Question: software that accepts a number and checks if a number, if the number is even it displays "even", if the number is odd "odd", if the input is not integer display "Please enter a number only" else dispplay "nothing inserted"

num = input("Enter a number: ")

if num.isdigit():
num = int(num)
	if num % 2 == 0:
		print("even")
	else:
		print("Odd")
elif num == " ":
	print ("Nothing inserted!")
else:
	print("Please enter a number only")
```
---


# Logical Errors (Exceptions)
- Errors that occur at runtime (after passing the syntax test) are called <span style="color:rgb(255, 192, 0)">exceptions or logical errors.</span>
- For instance, they occur when we
	- try to call an index that is greater than the list have causes (Index Error)
	- try to divide a number by zero (ZeroDivisionError)
	- When you have an error and your syntax (NameError) or so on.
- So specially when errors occur on runtime this causes a huge damage on our program so we have to handle it.

Error handling
- For handling errors we use try..... except blocks.
- 2 key word:
	- try:
		- code that may cause exception
	- except:
		- code to run when exception occurs
		- print ("Error: Denominator cannot be 0.")

if we are not sure which error we might get
- try:
	- code
- except ZeroDivisionError:
	- print ("Denominator cant be 0")
- except IndexError:
	- print("Index out of Bound")

- this time it will identify the type of error and print of accordingly
- ---

# Python Loops
- In computer programming, loops are used to repeat a block of code.
- Eg. if we want to show a message 100 times, then we can use a loop. And print (100) It's just a simple example; you can achieve much more with loops.
- There are 2 types of loops in Python:
	- For Loop
	- While Loop

## For Loop
- is used to run a block of code for a certain number of times. It is used to [iterate over any sequences] such as list, tuple, string...
- Syntax
```python
for val in sequence:
	Statement(s)
```

- sequence is a list, tuple, string or range
- Val is a variable which will hold the iteration from the sequence.
```python
languages = ["Swift", "Python", "Go"]
for language in languages:
	print (language)
```

### Range keyword
- A range is series of values between two numeric intervals. range(size)
```python
number = range(5)
	print (number)
# range(0, 5)

for i in range (5):
print (i)
# Output 0
# 1
# 2
# 3
# 4
```
### len key wrod
- a len is used to show the length of a sequence may be list, tuple or staffing. len(list)

## While Loop
- python while loop is used to run a specific code until a certain condition is met.
- syntax
```python
while condition:
	# body of while loop
```

1. You can do infinite loops
```python
while True:
	#body of the loop
```
### Difference between for and while
- The for loop is usually used when the number of iterations is known.
- and while loop is usually used when the number of iterations are unknown. When we have condition.
- Example:
	- If you have a case that wanted to check level of a user and displays "you have passed {n}th level" n is sequence. Until the user level and class level is equal. What do u do?

```python
current_level = 0
final_level = 5
while current_level <= final_level:
print("You have passed level", current_level)
current_level += 1

print("Level Ends")
```
- For loop: ends when the iterable is finished.
- While loop: end when the condition is false.

## Break
- Break is used to exit from an infinite loop.
```python
while True:
	print("aklil")
	break
```

```python
# Question
# 1. Create a simple number guessing game where the user has to guess a randomly generated number until they get it right

# Question
# Accept a number and calculate the sum of its digits using a while loop

import random
random_number = random.randint(1,5)
  

while True:
	user_input = int(input("Guess the number"))
	if user_input != random_number:
		print("incorrect")
	else:
		print("Correct")
		break;
```



```python
code = [2131, 2314, 24325, 6546]
errors = 0

while True:
	if errors <= 5:
		user = int(input(f"Enter The captcha correctly {code[0]}:\n>>"))
		if user != int(code[0]):
			print (int(code[0]))
			print(f"trail {errors}: incorrect!, try again")
			errors += 1
		elif user == int(code[0]):
			print ("welcome!")
			break	
	else:
		print("try again, next time.")
		break
```