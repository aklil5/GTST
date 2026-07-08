
////////WINDOWS SECURITY FOR CHROME TAB

## Script installation
- some hacking tools are developed by some people and those people make it open-source, that means we can get those scrpts/programs from github.
- so we can download and use it. For this purpose git have a feature called "clone" 
- syntax
     - [git clone `<link of script from github>]

## Script modules
- scripts are made with scripting languages (programming ) like {Python, bash, go, ruby}
- so when we use these programming languages to do tasks there is something called modules /libraries these are needed to run the script as the dependencies
- Eg,
    1. Python: to install python modules we use -> pip install `<modulename`
	    - For requirements file -> pip install -r requirements.txt
    2. Go: to install go modules we use -> go install `<modulename`
    3. Roby: to install ruby modules we use -> gem install `<modulename`


```
to install python
	sudo apt install python
```

Python installation

- to install - [pip install term]
	- if pip is not found there will be an error
		- [sudo apt install python3-pip
- if the package is already installed - [pip install -r requirements.txt]

- To RUN python files
		- [python3 filename.py]


if pip doesnt work at all
- use [pipx]


Go package installation
- Go scripts made with go-land (go programming language).
- there are 2 installation methods
	a. Old Version
	- go get github.com:captej/groupcache-db-experiment.git
	b. New version
	1. downloading the package 
		- go install github.com/lc/gau/v2/cmd/gau@latest
			- if command not found
			- [sudo apt install go]??????
		- default place of installed go package is in - ./go/bin/
		- so if you want to run them ./go/bin/"script|
	2. moving the file to /usr/bin (the default download place is - /home/rexder/go/bin) 
		- sudo mv filename_/usr/bin
		- [sudo mv ~/go/bin/gau(go script) /usr/bin]


search - sublister github
- shows programming language its made with and
- and the command to install it under "installation"
- after installation
	- cd sublester
	- ls
	- it has requirements.txt and sublister.py
	- sudo pip install -r reqiorements.txt


```
to install using ./ - you have to give execute permission for all
```


if you need help on linux about commands
- you can use
	- man (manual)
		- this will give you the whole manual and instruction of a tool or command
		- [man `<yourcommand>`]
		- [man awk]
		- [keys:] arrow keys for navigation | q for quit

Help
- Some commands have help option.
	- `<yourcommand>` -h
	- `<yourcommand>` -help
	- `<yourcommand>` --help


# Linux Processes & Services
- Terms
	- [Processes:] running instances of programs.
		- when you execute a program like opening a text editor, running a command, or starting a web browser, Linux loads that program into memory and starts it as a process.
	- [Services:] background programs that start automatically or manually, often for system takes (also known as [daemons)
		- a service that runs to gather any change on the system of to count time runs on background.
- To get processes running:
	- ps [options] - process
- More commands
	- ps -> for process running on my shell
	- ps -A -> view all running processes
	- ps -u username -> view user process
		- those that are running can be can be shell, nano, ....
	

Service on Windows
- Task manager -> Services
	- includes Name, Description, Status (Running and Stopped - you can change it)

Process on Windows
- running on the Foreground
- Task manager -> Processes

///////////////////////OBS Studio - to record desktop

Managing Processes
- to stop process 
	- [kill [options] [PID]]
	- killall [programname]
- More on kill
	- kill -19 PID -> to stop the process
	- kill -18 PID -> to resume the process we stopped
	- kill -9 PID -> to stop process immediately
- PID: Process ID- number given to the processes
- PPID: Parent Process ID

	- [killall picom

You love it?
- [ps] is a time taking and not realtime.
- for real time we have the tool called "[top]" 
	- installed on linux by default.
- But to make this fun we will use "[htop]", this is colorful and more enhanced!
	- you have to install this
	- [sudo apt install htop]
![[Pasted image 20250523180149.png]]
To kill on htop
1. Search for the process use F3
2. Choose SGNKILL (9) and kill it! /use F9


Foreground/background
- Thus far, we have run commands at the prompt and waited for them to complete. We call this running in the "foreground".
- Use the "&" operator, to run programs in the "background" or press ^Z
	- 
- To get the background process back to foreground
	- 
- To Stop a process going inside your shell just press ^C


===P2===
Managing Services
- Services can be started and stopped
- we will see different hacking services for the future classes.
- To manage services we can use tools called "systemctl"(PREFERRED) or "service"
- Syntax
	- [Sudo systemctl start `<ServiceName>` = Start the service
	- sudo systemctl stop `<ServiceName>` - stop the service
	- sudo systemctl status `<ServiceName>` - to check status of service
	- sudo enable status `<ServiceName>` - to make it start service when the computer boots - PERMANENT
	- sudo disable status `<ServiceName>`- to make it stop the service from running when the computer boots.
- sudo ser\\\ovice `<ServiceName>` start 
- sudo service `<ServiceName>` stop

Eg. [sudo systemctl start apache2


Null device
	is a system file
- [/dev/null] - Redirects output to nowhere
- If you want to ignore output, you can send it to the null device, /dev/null.
- The null device is a special file that throws away whatever is fed to it.
- You may hear people refer to it as the [bit bucket.
- Eg??????
- if you dont want to see errors on your screen an ddont want to save them to a file, you can redirect them to [/dev/null
- On shell output there are 2 things"
	- STDERR = 2
	- STDOUT = 1
- To redirect the errors from a command result we do 
	- command 2> filename
		- here if you check the file you saved on it have errors only.
- to redirect error-FREE output
	- command 1>filename
- So if we redirect our commands output to /dev/null we will get error free result
	- command 2> /dev/null

EG. pip install trem - COMMAND,  BZU ERROR YAMETAL
so 
- pip install trem 2> /dev/null whose cat is empty OR
- pip install trem 2> stderr.txt  WHY ERROR????????
![[Pasted image 20250521210222.png]]
WHY????????


Symbolic linking
- for files and folders
- symbolic linking is same as [Windows shortcut]
- it is a process of creating a linked shortcut form of file to some pre-existing file or folder. - only in home directory
- For Example: you can create program is some file an dto create a shortcut format of that file you will use symbolic linking.
- Also if a file path is too long we can create a symbolic linking.
- Symbolic linked files show 'i' in listing of command. Also there will be a "->" to show the linked file.
- Syntax: [ln -s SOURCE_FILEPATH newfilename]
- then ls -l newfilename
- MOREEEE



Alias
- used to give a name to some bunch of COMMANDS.
- Eg. if i wanted to name ls -la 'rex' so any time i want to get output of ls -la jus type rex
	- alias rex = 'ls -la'
- but this doesnt work after you closed the terminal
- if you want to make it work
	- you will add it to your shell config file
- Eg. for bash and fish, zsh...

PERMANENTLY
- Bash = nano ~/.bashrc
- ZSH = nano ~/.zshrc
- Fish = nano ~/.config/fish/config.fish

- close and reopen ur terminal/linix??? for it to work


then #My Aliases
alias burp = ""


Tmux - Terminal Multiplexer
- tmux is used to CLASSIFY our terminal work.
- you can install it using apt. On kali it is built in. Then to start it just type '[tmux]' , to install [sudo apt install tmux]
- to create config file type
	- nano .tmux.conf
	- Type this

```txt
unbind C-b
unbind I
set -g prefix C-a
unbind %
bind e split-window -h
bind o split-window -v
set -g base-index 1
setw -g pane-base-index 1
```
- Save it | exit tmux and open again


- To split horizontally
	- ^A then O
- To split vertically
	- ^A then e
- To exit
	- ^A then x or 
	- just type 'exit'
- To create tab
	- ^A then c
- To rename the tab
	- ^A then , (comma)
- To switch tabs
	- ^A then `<numbers>`
	- TO switch partitions
		- ^A then `<arrow>`
- ...... for more you can google but be aware of our super key is [`^A`]
	- 


wget
- is a tool used to download files from websites/servers
- Syntax
	- wget [options [link


find 
- On terminal if you want to search for files/folders/musics/videos, we can use find command.
- it is very essential tool
- Syntax:
	- find [search path [options [ search word]]]
- More commands
	- find / -name "linux"
	- find 
	- find 
	- find 

ls -la VS ls -l?????????

Searching
- you can search filtering

Google dork cheatsheet
