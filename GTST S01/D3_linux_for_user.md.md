
=====P1====

## Overview of kali linux
- specifically, we will see "kali linux" with Gnome desktop environment. Debian is recommended.
- previously known as Backtrack
- You can switch between your [desktop environment.
- the default one is XFC and u can add more after u download.
- 
- Menu - Application

1. Information gathering
	- tools for info, gathering in system network, host//
	- maltego, nmap - network map, recon-ng
2. Vulnerability Analysis
	- nikto, nmap
3. Web Application Analysis
	- tools for finding vulnerabilities and on websites
	- (burpsuite, sqlmap, ZAP, wpscan,) webscrab, skipfish, commix, httrack, paros
4. Database Assessment
	- Tools for finding vulnerabilities and exploits on Databases. Eg. log files - are login files
		- you can find the administrators username and file
	- JSQL injection, sqlmap, SQLite data
5. Password Attacks
	- tools for exploiting passwords for login, websites, application, windows...
	- hashcat, john, johnny, wordlists
6. Wireless Attacks
	- tools for exploiting wireless systems like wifi, bluetooth
	- aircrack-ng, wifite, reaver
7. Reverse Engineering
	- tools for exploiting softwares, Mobile Applications and any binary files
	- apktool, NASM shell, ghidra
8. Exploitation Tool
	- tools for exploiting Softwares, Mobile, Computers, websites and anythings
	- sqlmap, metasploit
9. Sniffing and spoofing 
	- tools for Listening or hijacking networks
	- wireshark
10. Post Expoitation/Maintaining Access
	- tools for maintaining our access after exploiting a system
	- backdoor
11. Forensic
	- tools for doing researches and investigate a Cyber Attack
	- hashdeep
12. Reporting tools
	- tools for report preparation. after some forensic you will get data and will write report and these tools will help you.
	- maltego, record my desktop
13. Social Engineering
	- tools for social engineering attacks
	- backdoor, beef xss, maltego
14. System Service
	- buttons used to start some services.
	- beef start, beed stop, dradis start, dradis stop
15. Usual Application
	- softwares for some basic purpose

## Shutdown, lock, restart
	to have hybernate option to ur GNOME
		genome extension - hybernate

## Worskspace manager
- to classify our works on different windows
- 1 2 3 4 - xfc
- gnome top right box with number on it


## Folder Manager 
1. Dolphin
2. Thunar - ubuntu, gnome, xfce
3. Naultilus - ubuntu, gnome
4. 

## Linux Command
- Linux systems use shells (delala). the shell help us to communicate with the kernel and helps to execute codes.
- Shell is also called "Terminal".

- default shell type of kali linux- ZSH

The terminal have 5 parts
1st line
	- Username 
	- @ Hostname
	- Current Directory = PATH in [] 
		- "~" is home directory
		- "." is local directory
		- `*` is all diretories 
-2nd line
	- Privilege = 
		- $ - (local user), 
		- # - (root)
		- PS??
	- Command place = __

Directory = folder

## Linux Command Basics
- on Linux there are over 1000 commands. But we are expected to know the main and useful only.
- also those commands have their own "options" and "arguments".
	- `$ command --option argument`
	- Options: additional settings they take 
	- Arguments: different inputs to have outputs

## What is Command
- "SMALL PROGRAMS THAT DO ONE TASK WELL"


ls/List Directory
- SYNOPSIS
	- ls [OPTION]  [File]
- DESCRIPTION
	- List information about the Files (the current directory by default)
tree
- SYNOPSIS
	- tree [FOLDER]
- DESCRIPTION
	- list info about the files and folders with tree structure (the current directory by default)


- ls -l - more information about the files (creator, date of creation)
- ls -a - all hidden files will be shown - HIDDEN files have '.' infront of them
- ls -al - more information about all hidden and not hidden files
- ls filename - files inside the folder
- ls -R - Recursive - lists ALL folders and their sub folders
- ls - Rla - RECURSIVE, DETAILED, HIDDEN files


====P2=====

pwd/ print working directory
- SYNOPSIS
	- pwd [options]
- DESCRIPTION
	- it prints the path of the working directory, starting from the root.

echo
- SYNOPSIS
	- echo [string]
- DESCRIPTION
	- to display line of text/string that are passed as an argument.

Output Redirecting (>)
- Your can write "Output of any commands into files, This is Called Redirecting.
- To do this we will use the ">" Sign (output redirecting sign)
	- echo text> file.txt "new file"
- You can add texts (append)
	- echo text >> file.txt "append to existing file"

cat/ head/ tail/ less
- SYNOPSIS
	- cat [FILE]
		- cat [FILE] -n - COUNTS NUMBER OF LINES 
	- head [FILE]
	- tail [FILE]
	- less [FILE]
		- opens it separately from the command line
		- use q to go back to terminal
- DESCRIPTION
	- All are used to show the content of a file
	- Head and Tail will display the 10 lines of the file.

touch - CREATE FILE
- SYNOPSIS
	- touch [file1] [file2] [file 3], SPACE BETWEEN NAMES - DIFFERENT FILES
- DESCRIPTION
	- Creates any kind of files with the name you gave it. With EMPTY inside.

mkdir / make directory
- SYNOPSIS
	- mkdir [FOLDER NAME1]
	- [FOLDER-NAME2]
	- [FOLDER NAME 2]
	- mkdir -p folder1/folder2/folder3 SUBFOLDERS
- DESCRIPTION
	- creates folder with the name u gave it.
	- DONT forget to add the "" when you are using folders with space between them.

clear
- SYNOPSIS
	- clear
- DESCRIPTION
	- clears your screen

or use 
- Ctrl + L

Upward Arrow - previous commands

rm/remove
- SYNOPSIS
	- rm [FILE1] [FILE2] [FILE3]
	- CANT REMOVE IF THERE ARE SUBFOLDERS
- DESCRIPTION
	- removes files
- rm -r => recursive (4 folders) - REMOVES WITH ALL SUBFOLDERS
- rm -i => for prompt (ask) FOR FILES, NOT folders
- rm -f => Force - Powerful, for those that refuse to be deleted
- you can use them in combination
	- rm -rf 'filename' => Remove Subfolders with Force

cp/mv Copy and Move
- SYNOPSIS
	- cp[OldFilePlace  New file place]
	- mv [OldFilePlace  New file place]
- DESCRIPTION
	- if you want to copy folder which contains files, you have to use -r option

- cd / - changes to root directory
- cd ..  or cd ../ - go to previous folder
- cd ../../ - go previous twice

- IF YOUR ARE ON ROOT OR ANOTHER FOLDER and you want to copy and paste file from home/user
- cp ~/file ~/folder

	- cp -r => copy all including subfolders

- You can use Notations to Move and Copy file/Folder
	- cp "Cyber sec note.pdf" ../../tmp
		- go backward twice from current folder and paste to the folder mentioned
	- mv adlg.log ~/Downloads/ - ??? why / at end
		- copy and paste from anywhere to anywhere
	- mv * /root

`~ = /home/user`


grep - 
- grep [options] pattern [files]

- The grep filter searches a file for a particular pattern of characters, and displays all lines that contain that pattern. The pattern that is searched in the file is referred to as the regular expression (grep stands for global search for regular expression and print out).

if it is a WORD that you search you can choose NOT to use ""
- grep -i 'search' file
	- case insensitive
- grep -c 'search' file
	- count numbers word
- grep -l 'search' * (no file name, searches from all)
	- displays filename
- grep -r 'search' foldername (all subfolders)
	- search text in folders
- grep -v 'term' filename
	- to display without this term
- grep -n 'term' file
	-  number of line
- grep -o 'pattern' filename
	- display that specific word only

- grep -ran HTB
	- a - binary file - ZIP file and json files
- grep -rno HTB

wc - wrod count
- SYNOPSIS
	- wc [OPTION] .... [FILE].....
- DESCRIPTION
	- to find out number of lines, word count, byte and characters count in the files specified in the file arguments
	- no of line, words, size(byte)
	- includes all 3 below, but if u want specifically only one info, use one of them
		- wc -l - number of line in text file
		- wc -w - number of words
		- wc -c - how many Bytes


## Multiple Command Executions
- you can run/execute multiple commands in 1 line.
- using 3 methods:
	- AND (&&)
	- OR (||)
	- Pipeing (|)

AND (&&)
- all commands you entered will be executed. if both are working without error

OR (||)
- command will be executed. If it have error or not
- if the 1st command works, the 2nd wont be run

Piping (|)
- will help you run commands by using the output of the 1st command as the input for the next one.
- Eg. cat file.txt | wc -l

RENAME FILES
- mv filename newfilename

## Sed/Stream Editor
- A powerful command-line tool for parsing(metenten) and transforming text in Linux.
- processes files line-by-line, making it efficient for large text processing tasks.
- Common Uses:
	- text substitution and replacement
	- deleting or selecting specific lines
	- efficient text manipulation for tasks like network
	- information gathering or penetration testing logs.
- SYNTAX: - sed [options] 'command' filename
	- OR use piping
		   - cat filename | sed 's/old/new/'
	- Substitute (Replace): sed "s/old/new/" file
		- You can use the | sign instead of /too.
		- 's|old|new|'
		- Use 'g' on the end todo replace if it finds the word MORE THAN 1 time in one line. 's/old/new/g'
	- Delete: sed '/pattern/d' file


## awk
- a versatile command-line text-processing tool.
- ideal for pattern scanning and data extraction in STRUCTURED TEXT.
- Named after its creators: Aho, Weinberger, and Kernighan
- features:
	- processing tet line-by-line
	- supports complex pattern matching
	- allows field-based (columns) text manipulation, making it great for column-based data like CSV (comma separated value) files.
- Basic Synthax:
	- [awk 'pattern {action}' file.txt
	- awk '{print $1, $3}' file.txt
		- \# prints columns 1 and 3
	- awk '/pattern/ {print $0}' file.txt
		- \# prints ALL lines matching "pattern"

- Awk by Default Determine columns, if they are separated by space (), Here space is known as [DELIMITER.
	- To change Delimiter add => -F "Sign"  
- Built-int Variables:
	- $0 - Entire line of text
	- $1, $2....: represents each column (field) in a line
	- NR: Line (record) number. - no of record/row
	- NF: Number of fields (row) in the current record. - no of column on each line
	- $NR - 1,1 2,2 3,3 4,4 - lay yaluten
	- $NF - last column
- You can use it with file or Pipped.
	- Awk 'options' file.txt
	- Cat 'file.txt' | awk 'options'



Eg. `cat awk.txt | awk -F "," '/6/ {print $2}'
    print the 2nd column of all lines that have pattern 6 in them
Eg `cat awk.txt | awk -F "," '$4 > 68000 {print $2}'`
	print 2nd column of those with value of 4th column > 68000
Eg `cat awk.txt | awk -F "," '{sum += $4} END {print "Total: ",sum }`
	add all 4th column values and store it in sum var
	Total: 

