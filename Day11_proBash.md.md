- Regular expressions
- Else if
- loops
- functions
- bash and linux shell
------
# Regular Expressions! /regex/

How do sites know that our input is not email?
- most filter validation on any platform done by Regular expression /regex/
- They are patterns that helps to filter so texts, space, tabs and symbols.
- Like telegram or other platforms filtering links inside group, filtering some bad words. All are regex.
- Regex is PATTERN!
- Regex are used on linux tools called grep, awk and sed

regex.....
- To demonstrate this we can simply use vscode search tool.
- and dont forget to turn the regex button on
- The pattern is same but the implementation may differ on programming languages.
- On python, 
```python
import re
a = re.search("PATTERN", "SEARCHING FILE").group(0)

print(a)
```

when it filters - It HIGHLIGHTS them

so 'n is a patter, it is called <span style="color:rgb(255, 192, 0)">metacharacter'</span> 
# Metacharacters
- Those are regex pattern symbols for filter
- They are:
	- .
	- ^
	- $
	- *
	- +
	- ?
	- { }
	- []
	- ()
	- |
	- \

# Dot (.)
- used to get all the line except new lines
- Syntax:
	- This means give me <span style="color:rgb(255, 192, 0)">all lines except those without a text</span>

Caret (^) - Assertion
- Used to get line that <span style="color:rgb(255, 192, 0)">start with pattern</span>
- Syntax: \^hello
	- This means lines that start with hello

Dollar sign ($) - Assertion
- used to get line that <span style="color:rgb(255, 192, 0)">ends with some pattern</span>
- Syntax: hello$
	- That ends wit hello

Plus(+) - Quantity
- Used to get line that have <span style="color:rgb(255, 192, 0)">pattern that occurs 1 or more times. (gets increasing patterns</span>
- Syntax: hellos+
	- A text hello that have s at least 1 times and more.
![[Pasted image 20250616202638.png]]![[Pasted image 20250616202708.png]]

Asteriks (\*) - Quantity
- Used to get line that have pattern that occurs 0 and more times.
- Syntax: hellos*
	- A text///////

Question mark (?) - Quantity
- used to get line that have pattern that occurs 0 and 1 times.
- Syntax: hellos?
	- A text hello that have s at least 0 or 1 time.

- starts with n and
- ends with com

```regex
^n.*com$
```
in between means: 
	.* -> 0 or more between them
	.+ -> 1 or more between them

Curley Bracket ({ min, max}) - Quantity
- Used to get line that have pattern that occurs min and max times. It is custom
- Syntax: hellos{1, 3}
	- A text hello that have s at least 0 times and more.

- {1,} = plus sign
- {0} = astrik
- {0,1} = question mark

What if
- starts with n and ends with com including the texts that have 7-13 character between those 2
	- ^n.{7,13}com$

\w 
- used to get <span style="color:rgb(255, 192, 0)">Alphanumeric</span>
- Syntax: \w
	- All texts except newlines and symbols

\W
- used to get ALL except Alphanumeric
- Syntax: \W
Includes:
- TABS, space, symbols, numbers, new lines

\s
- used to get white space.
- Syntax: \s

\S
- Used to get all except white space
- Syntax: \S

\d
- used to get Digit/numbers/
- Syntax" \d

\D
- used to get all except Digis/numbers/
- Syntax: \D

Pipe(|) - OR
- used to search 2 different things.
- syntax: a|b

^t.* - those that start with t - <span style="color:rgb(255, 192, 0)">THE WHOLE LINE</span> 

.* - FULL LINE

[a-z\dA-Z] == \w

Escape (\\)
- used to search symbols that are meta characters.
- Syntax: \sign 
	- Example: \\.

Square Brackets ([]) - Custom pattern
- Used to create your own patterns
- Syntax: `[pattern]`
	- Example: `[a-z]`

```
write a regex to filter a link and gmail


.*@.*\.(com|net|org)$


```


Bash regex
- You can use it on awk, sed, but for today i will show you using grep.
- On bash treminal these meta characters have meaning. so we have to escape them by adding "\\" infront of the metacharacters.


`cat testingREGEX.txt | grep "^.*@.*[a-z]\$"`

BASH FOR REGEX
- we use<span style="color:rgb(255, 192, 0)"> =~ </span>operator for regex check with if condition statements
- Here we use double Brackets for our conditional Statements.
- Syntax:
```
pattern = "YourRegex"
if [[ $input =~ ${pattern} ]]
```
![[Pasted image 20250616215121.png]]

accept emails from username and check if its valid email or not

Bash else if
- To do more than 1 comparing
- it is same with python it is "elif"
- Syntax:
	```bash
	if condition
	then
		body
	elif condition
	then 
		body
	else
		body
	fi
```
![[Pasted image 20250618202036.png]]
# Loops
- on Bash, there are 4 types of loops:
	a. For loop
	b. While loop
	c. Until loop
	d. Select loop

For loops
- the iteration may be different here. we can use arrays like list on python but we don't have range in bash but we can do {a..b} this iterates from a to b
- iterate over sequence data style or var with with sequence data type
- Syntax
```bash
for condition
do
	body
done
```

```bash
for num in {1..10}
do 
echo $num
done

//output: 
1 
2 
3 
4 
...
10
```
![[Pasted image 20250618202845.png]]

---

# For loop without sequence data
```bash
for ((i=1; i<=10; i++))
      # START # END E INCREMENT
do
echo $i
done
```

On bash
i++ = i += 1
i-- = i -= 1

---

# For loop with increment/decrement
- same syntax with index slicing but here it is for looping - {start..stop..step}
```bash
for num in {1..10..1}
do 
echo $num
done
```

```bash
for num in {10..0..-1}
do
echo $num
done
```

---

# While loop
```bash
while [ expression ]
do
	body
done
```

- ![[Pasted image 20250618204415.png]]

Infinite loop
```bash
while :
do
echo "Welcome to GeezTech."
done
```

Break Statement
```bash
#! /bin/bash

echo "Countdown for Website Launching..."
i = 10
while [ $i -ge 1 ]
do
if [ $1 == 2 ]
then
	echo "Mission Aborted, Some Technical Error Found."
	break
fi
echo "$i"
(( i-- ))
done
```

Continue Statement
- is A function that helps on break the loop there and start if from the up again. - its python equivalent is called 'pass'
- jumps a loop and continues to other
![[Pasted image 20250618205614.png]]

---

Until loop
- it is same but this on exits the loop when the expression is true.
- The name until means "eske"
```bash
until [Expression]
do
body
done
```

```bash
i = 1
until [$i -gt 10]
do
echo $i
((i++))
done

//Output: 1 2 3 4 5 6 7 8 9 10
```

```bash
i=0
while [ $i -lt 10]
do
echo $i
((i++))
done
```

---

Select Loop
- The select loop in bash is a control flow statement used for creating a simple menu from which the user can choose options. It provides an easy way to handle user input in a loop.
- Syntax
```bash
select variable in list
do 
	commands 
done
```
![[Pasted image 20250618212619.png]]
![[Pasted image 20250618213534.png]]

# Function
```bash
function_name(){
body
}
function_name
```

```bash
print_it() {
	sum=$(($1+$2))
	echo "The sum: $sum"
}
print_it 5 6
```

- when you have function and the arguments will be $1, $2...
- if we use $? it will call the return value
![[Pasted image 20250618214525.png]]
# Bash and Linux
- We can run linux commands inside our bash
```bash
#! /bin/bash
echo "I can run apt commands in my bash"
apt update
```

- You can run bash codes in 1 line.
```bash
for i in {1..5}
do
echo "Hello $i"
done
```

```bash
for i in {1..5} do echo "Hello $i" done
```

- You can access files in current directory using * sign
```bash
#! /bin/bash

echo *
//lists all files in currect directory
```


# Interaction with linux
- you can interact with linux terminal using bash.
- For this our codes are bash so your terminal have to be on bash
- To check your shell - echo $SHELL - if not bash change it using
	- Command: <span style="color:rgb(255, 192, 0)">/bin/bash</span>
- then you can write BASH SCRIPTS with out creating a file - on the Command line

# For loop on terminal 

syntax: `for command; do body; done
on the command line
```bash
for i in *; do echo $1; done
```

```bash
ls

for i in *; do mv $i old_$i; done

* -> holds the file names as a sequence data type
```
`
