# {{New Title}} 🔥
Created on: 

Topics:
- What is bash
- use of bash for hackers
- output
- variables & data type
- input
- comment and indentations
- arithmetic operation
- if-else

----

What is Bash Script
- Bash = Bourne Again Shell
- it is a shell, that is used to interact with your kernel
- What is Script?
	- is a file that contains shell commands in a simple and clear algorithm
- the original is sh = Bourne shell

Uses of bash
- Script development - commands
- Automating tasks
- Simplifying your linux ability
- Developing hacking scripts

Starting with Bash
- Bash files can have ".sh" extension but you cna have it without '.sh' too 
- The file have to have executable Permissions.
- You can use any text editors u need: VIM, nano, VScode, gedit, cherrytree

You can use
- VS code -> opening text file and selecting language bash/scripting lang OR
- Tmux

Displaying Output
- To start Every bash scripts use <span style="color:rgb(255, 192, 0)">shebang (tells the shell which interpreter is used to execute the script).</span>
	- `#! /bin/bash
	- `#! /bin/sh
- To display outputs on bash you just do 
	- `echo "YOUR TEXT HERE"
- To run your project you can do:
	- `/bin/bash hello.sh` - no need for x permission
	- `./hello.sh -> need x
	- `hello -> need x
		- hello.py is FILENAME

Examples
- If you need to add new lines to your code just add 
	- `echo

Variables
- Each variable are same with python variables, with some exceptions.
- Syntax:
	- VARIABLE_NAME  = value
- Exceptions:
	- <span style="color:rgb(255, 192, 0)">NO SPACE </span>between the equal sign (=)
		- NAME = "Nathan" => ERROR
		- NAME="Nathan" => Correct
		- Never Start with Numbers
		- USE double quotes only.
- To use the variable we will used dollar sign ($) before the Variablename
- If you want to display the variable sticked with other text use $[VARIABLE_NAME]
- Bash Variables are string by default.

----



- The set command can be used to assign values to positional parameters.
- Syntax
	- `set value1 value2 valu3 value4 value5`

```bash
#! /bin/bash
set nathan abebe sami miki jerry
echo $3 $2

# Output: sami, abebe
```

```bash
var="menta"
echo "$var"


var = "foot"
echo "${var}ball" # Output football
```

- The set command can be used to assign values to positional parameters.
- Syntax:
	- set value1 value2 valu3 value4 value5

----

System Variables
- are variables those are declared by the system.
```
#! /bin/bash

echo $BASAH
echo $BASH_VERSION
echo $PWD
echo $HOME
echo $PATH
```


i here so many: LANG, TERM, MAIL, EDITOR, USER, SHELL....
- USER displays Computer owner (host)

Variables & Data types
- as we saw, the previous method they create strings only
- so to create other data types we use declare.
- Arrays
	a. Arrays are lists or tuples on python
	b. Syntax:
		i) tar = ("list1" "list2" "list3" "list4") - no commas 
		ii) TO display echo
			1. ${var[0]}
		iii) To get all the elements
			2. ${var[@]}

1. To get the indexes
	1. ${!var[@]}
2. To get the length
	1. ${#var[@]}
3. To add element to the array
	1. var[4] = "list5"
4. To remove from the array
	1. unset var[3]

- On bash we have 2 methods to accept input
	1. Read function
	2. Arguments

1. Bash Read
- read used to accept inputs while the script is running.
- Syntax:
	- read -p "Text to Display" var
	- read -sp "Password: " var => used to accept HIDDEN TEXT like password.
	- read -a var => for accepting arrays (lists)


```bash





```
2. Arguments
- These helps to get input before the script starts
- Syntax:
	- just use $0-$9 while you want to work with the input

---

COMMENTS



# Bash sleep
- sleep used to make a good waiting on our script.
- Syntax:
	- `sleep <number>5`




# Operation
- To do mathematical operations you have to do <span style="color:rgb(255, 192, 0)">$((expression))</span>
- we will use [let] keyword for assigning variable
A. Arithmetic Operations
1. Addition $((a+b))
2. Subtraction $((a-b))
3. Multiplication $((a * b))
4. Division $((a/b))
5. Exponential $((a ** b))
6. Modulo $((a % b))
```bash
x=10
y=6
z=0
echo "Addition"
let "z=$((x+y))"
echo z= $z
```



B. Assignment Operations
1. Increment "let a+=3"
2. Decrement "let a-=3"
3. Multiply "let a*=3"
4. Divide "let a/=3"

C. Comparison operation
- alphabetic Comparison
	- Greater Than => -gt
	- Less Than => -lt
	- Greater than and equals to => -ge
	- Less than and equals to => -le
	- Equal => -eq
	- Not equal => -ne
- Sign Comparison
	- >, <, >=, <=, =, !=

# if else conditions
syntax
```bash
#! /bin/bash

if [condition]
then
body
else
body
fi
```

For Alphabetic Comparison, strings []
```bash
#! /bin/bash

if [2 -gt 1]
then
echo "he"
else
echo "bye"
fi
```

- If you used [condition] => you will use alphabetic comparison
- But for strings you can use sign too

- On bash, we dont have indentation but if you finished writing the body you type ["fi"]

For symbolic Comparison (())
```bash
#! /bin/bash

if ((2 > 1))
then 
echo "he"
else
echo "bye"
fi
```

- If you used ((condition)) => you will use numeric comparison

![[Pasted image 20250614205254.png]]

![[Pasted image 20250614205745.png]]

Nested if 
```bash
#! /bin/bash

if [ $1 -gt 50 ]
then
echo "number is greater thean 50"
//////
if (( "$(($1%2))" == 0 ))
then
echo "and it is an efen number."
fi
//// nested one
fi
```

if you use logical operator - use double [[]]
```bash
if [[ 10 -eq 10 && 5 -gt 4 || 3 -eq 4 || 3 -lt 6 ]]
then
echo "condition is true"
fi
// Output: true
```