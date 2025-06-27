Date: 15/09/2017

Topics:
- what is Programming language
- History of python
- why python is used in hacking
- how to install python
- what is IDE and code editor
- creating python script file
- outputs and comments
- variables and Datatypes

============================================================

# What is Programming Language
- it is language which helps to communicate with computers (they are not able to understand human language)
- we humans have lots of languages
- computer have many languages too
	- Assembly, C, C++, Java, Javascript, Python, Ruby, Perl, Go
- Prog lang. helps to write <span style="color:rgb(255, 192, 0)">programs</span> using those languages

_________________________________________________

# What is Program
- a program is an <span style="color:rgb(255, 192, 0)">algorithm</span> expressed in a programming language.
- an algorithm is a <span style="color:rgb(146, 208, 80)"><span style="color:rgb(146, 208, 80)"><span style="color:rgb(255, 192, 0)">detailed sequence of actions</span> </span>t</span>o accomplish some task. Named after an Iranian mathematician, Al-Khwarizmi/
- Technically, an algorithm must reach a result after a finite number of steps.
- With those steps Programs Do a Specific task Correctly.

## Algorithm Example
- To ask someone his/her name, you will do the following steps:
	a. You walk to the person
	b. greetings
	c. wait for answer back
	d. "What is your name?"
- There will be a lot of kinds of algorithms to do a specific task.

_______________________________________________

# Pseudo Code
- Pseudo Code is a simplified, structured way of writing down programming logic in plain language, without worrying about the syntax of a specific programming language.
- It uses short, clear statements to outline each step of a program's logic, making it easier for beginners to understand how an algorithm works and for programmers to plan complex solutions before writing actual code.
- You can use any informal languages, the main concern is breaking the process down.
- Eg of Pseudocode for a simple l<span style="color:rgb(255, 192, 0)">ogin process</span>
```
	BEGIN
		PROMPT user for username
		PROMPT user for password
		IF username and password match
			DISPLAY "Login Successful"
		ELSE
			DISPLAY "Login Failed"
	END
```

Example
- Pseudo code for Program that accepts 2 numbers from user display the result (like calculator)
```
BEGIN
	DISPLAY "Enter the first Number: "
	INPUT number1
	
	DIPLAY "Enter the second number: "
	INPUT number2

	result = number1 + number2
	DISPLAY "The result is ", result
END
```

ADVANCED
- Adding more operaions to make it real calculator

```
BEGIN
	DISPLAY "Enter the first number: "
	INPUT num1

	DISPLAY "Enter the second number: "
	INPUT num2

	DISPLAY "Choose an operation (+, -, *, /):"
	INPUT operation

	IF operation is "+":
		result = number1 + number 2
		DISPLAY  "The result is: ", result
	ELSEIF operation is "-":
		result = number1 - number 2
		DISPLAY  "The result is: ", result
	ELSEIF operation is "*":
		result = number1 * number 2
		DISPLAY  "The result is: ", result
	ELSEIF operation is "/":
		IF num 2 is not 0:
			result = number1 / number 2
			DISPLAY  "The result is: ", result
		ELSE:
			DISPLAY"Error: division by zero is not allowed.
	ELSE:
		DISPLAY: "Invalid operation selected"
END
```

____________________________________________
# Evolution of I/O {Input/Output}
- Early in the history of computing, programs were submitted on [punch cards with all the data] they required and executed together with other programs that used the same libraries. Output was to a [line printer].
- Later developments introduced [interactive processing] which allowed the user to provide data while the program was running. This normally takes place in a Question & Answer format.


Generations of Computers
1. **Fist Generation**: Vacuum Tubes => punch cards
2. **Second Generation**: Transistors(looks like Socket  - device that changed the world) => Programming started here with Assembly
3. **Third Generation**: Integrated Circuits(many transistors on a board) => Basic, COBOL, Pascal, Fortran, C, C++, Perl and Ada
4. **Fourth Generation**: Microprocessor(CPU - transistors in a box- 64byte, 32byte) => Python, SQL, Matlab - interactive processing speed is increasing rapidly.
5. **Fifth Generation**(quantum, nano technology): Artificial Intelligence

they could only solve one problem at a time. It would take days or even weeks to set up a new Program on First Generation. 

______________________________________________________
# Types of Programming Languages
- Computers understand binary (0/1), humans don't understand this
- So based on the closeness of the language to humans, we classify it into 2
- The more they become low to the machine they are faster.
- The more they become like human language they are slower.

1. Low level
- are more like machine but with lots of effort ppl can understand them. they are close to the hardware of the computer.
- Eg. Assembly, C-lang

2. High level
- they are close to human languages.
- Eg. Python, C++, Java, JS


_________________________________
# How do high level language work?
- as we saw earlier we have said that computer know only [binarys], and if we code with high level languages, how do computers understand us?
1. Compilers:  are tools which helps to convert the whole code to <span style="color:rgb(255, 192, 0)">bytecode</span> then computer will execute it.
	Eg. C, C++, Java
	
	- `source code(Hello.java) -> byte code(Hello.class) -> output

2. Interpreters: can <span style="color:rgb(255, 192, 0)">directly execute</span> the code by reading the source code line by line
	Eg. Python
	
	- `source code(Hello.py) -> output


Uses of Programming Language
- Android app dev
- web wed
- machine learning
- AI
- Game dev
- Big data tech
- Desktop sw dev
- hacking tool dev


_______________________________
# What is Python Programming?
- It is a high level & Interpreted programming language. => Very easy to learn
- it is very simplified language anyone can write with it, also can read it.
	- python: print
	- C++: cout
	- Java: SysTEM.oUt.prlnTLn

History of python
- Python was developed by [Guido van Rossum] in the late eighties and early nineties at the National Research Institute for Mathematics and CS in the Netherlands.
- Python is derived from many other languages, including ABC, Modula-3, C, C++, Algol-68, SmallTalk, and Unix shell and other scripting languages.
- Python is now maintained by a core development team at the institute, although Guido van Rossum still holds a vital role in directing its progress. 

Uses of Python
- Data visualization
- Data analysis
- Machine learning
- AI
- Back-end web dev (with frameworks like Django and Flask)
- Game dev
- Hacking Script writing


IDe & Code Edittor
- IDE (Integrated Devt Envt): is a sw that helps write and run a specific programming language Eg. PythonIDE
- Code Editors: softwares that help to write any kind of programming language. and also by adding some compiling/interpreting feature they can run programs/scripts. Example: Sublime, VScode

# to open py file in VSCODE - File -> New Text File -> choose lang

===========================================================

==P2==
# Outputs and Comments
- on python, to display output we use keyword 'print'
- syntax: print(Object=' ', sep=' ', end=' ' )?????
<span style="color:rgb(255, 0, 0)">	- Objects can be string, variable /////////////</span>
	- sep - between different objects
	- end - separator of 2 prints
```python
print("Hello", end = ':')
print("world")

# Output Hello:world
```

- \n - new line (empty new line - if added at the end)
- \t - TAB

- You can use the term <span style="color:rgb(255, 192, 0)">"DISPLAY" </span>for pseudo code

# Comments
- are simple notes written on our codes those can help us to remember the function of the code or to make it simple for peoples to understand our code.
- Comments won't be executed.
- Syntax: `# This is a command line`

# Python Keywords
- Keywords are predefined, reserved words used in Python programming that have special meaning to the compiler.
- Fallse, None, True, and, as, assert, asynx, await, break, class, continue, def, del, elif, else, except, finally, for, from, global, if, import, in, is, lambda, nonlocal, not, or, pass, raise, return, try, while, with, yield
----

# Variables
- are a value holders /containers/
- they store data
- we give some value to some word.
- example: number = 10 => from now on my python program knows the value of number is 10.
- The process of giving value to world is called [Variable Declaration]
- The word that holds the data is called [Identifier]
- We can Print value of variables by giving the identifier
- You can Use the term<span style="color:rgb(255, 192, 0)"> "DECLARED" </span>for pseudo code.

- We can change value of variable in a code.
- You can print the variable with [variableName] on print keyword.
	- [Syntax: print (f"your text {variable})
	- USING ONE OBJECT instead of many
		- Eg ` print("your text", variable, "other text"` - this has 3 objects

- REMEMBER
	- while naming the identifier:
		1. Dont use space between words use _
		2. Dont use numbers as identifier

---

# Data Types
- There are a lot of Data types on python
	- Numeric: int, float, complex
	- String: str
	- Sequence: list, tuple, range
	- Mapping: dict ???
	- Boolean: bool
	- Set: set, frozenset

1. Numeric Data type
	- int(integer) - holds signed integers of non-limited length.
	- float - holds floating decimal points and its accurate up to [15] decimal places.
	- complex: holds complex numbers.
- You can identify The type of a variable with the keyword [type(var)]
	- `# Output <class 'int'>`

2. String Data
	- String is a sequence of characters represented by either single or double quotes. 
	- Eg. var = " " or var = ' '

3. Sequence of Data
	A. Lists
	- List is an ordered collection of similar or different types of items separated by commas and enclosed within brackets [ ]. 
	- to access items from a list, we use the index number (0, 1, 2,,,,)
	- We can add/modify objects to the list using [list.append("item")]

	PSEUDO CODE
		- DECLARE list called language containing Python, y

	B. Tuple
	- is an ordered sequence of items same as a list. the difference is that tuples are [IMMUTABLE]. - cant be modified
	- we can use parenthesis () to store items of a tuple.
	- similar to lists, we use the index number to access tuple items in Python


4. Dictionary Data
- Python dictionary is an [UNORDERED] collection of items. It stores elements in key/value pairs.

	PSEUDO CODE
		- DECLARE a dictionary called "fruits" with the following values:
			"apple" = 10
			"banana" = 15-[]

```python
user = {
'username': 'nathan26',
'password': "p@#$$word"
}
```
- username and password = key
- nathan26 & p@ssword = value\$$ 

- we use keys to retrieve the respective value. But not the other way around. 
	- user[username] 
		- \# Output nathan26