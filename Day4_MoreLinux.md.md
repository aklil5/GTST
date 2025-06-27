
## Linux File Hierarchy
- Linux/UNIX have a special file system than windows.
- file system is a directory structure that the OS uses.

## File System
- directories/FOLDERS that our system /windows/ use 
- eg. folders in Local disk C

## System Files
- are FILES used by the system software (OS).
- Windows: system files appear under the local Disc C
- Linux
- System files appear under the root directory (/)

!!!! EVERY PATH STARTS WITH /

## File Structure in detail
1. /{root}
	- every single file and directory starts from the root directory (/)
	- ONLY THE ROOT USER has the right to write under this directory
	- /root is the root user's home directory, which is not the same as /

2. bin - Binary executables
	- essential command binaries that need to be available in single-user mode; for all users
	- you can list all the commands in the folder
	eg. cat, ls, cp, pwd

3. /boot - Boot loader files
	- is directory containes the essential files needed to boot the system or kernel.
	- Kernel initrd, vmlinux, grub files are located under /boot 
	- Eg: initrd.img-2.6.32-24 generic, vmlinuz-2.6...., grub

4. /dev - essemtial device files
	- these include terminal devices, usb or any device attached to the system.
	- Eg. /dev/tty1. /dev/usbmon0

5.  /etc - et cetra
	- contains configuration files required by all programs.
	- adadis michanu programs configuration files are stored here
	- also contains startup and shutdown shell scripts used to start/stop individual programs.
	- Eg. /etc/resolv.conf, /etc/hosts (to change give IP address to a name u want), /etc/passwd

6. /home - Home directory
	- home directories for all users to store their personal files.
	- eg. /home/nathan, /home/rexder
	- here, you cant access files of other users
	- eg. if your home is /home/nathan you cant access /home/rexder
	- your home directory /home/nathan will be denoted by ~

7. /lib - Libraries essential for the binaries in /bin & /sbin
	- library filenames are either id* or lib*.so.*
	- eg. id 2.11.1.so, libncurses.so.5.7

8. /media - Mount points for removable media such as CD-ROMS
	- Temporary mount directory for removable devices
	- eg. /media/cdrom for CD-ROM; /mediafloppy for floppy drives

9. /mnt - temporarily mouned files
	- temporary mount directory where sysadmins can mount file systems
	- if you are NOT ROOT USER, you cant access it

10. /opt - optional application sw packages
	- contains add-on applications from individual vendors.
	- add-on-applications should be installed under either /opt or /opt/sub-directory.

11. /sbin - essntial system binaries
	- just like /bin, /sbin also contains binary executables.
	- the linux commands located under the directory are used typically by system administratory, for system maintenance purpose.

12. /tmp
	- directory that contains temporary files created by system and users.
	- files under this directory are "deleted" when system is rebooted
	- you wont find it after shutown
	

13. /usr - user utilities
	- contains binaries, libraries, documentation, and source-code for SECOND LEVEL programs.
	- /usr/bin contains binary files for user programs. If you cant find auser binary under /bin, look under usr/bin. For example: at, awk, cc, less, scp
	- /usr/sbin contains binary files for system administrators. If you cant find a system binary under /sbin, look under /usr/sbin
	- Eg: atd, cron, sshd, useradd, userdel
	- /usr/lib contains libraries for /usr/bin and usr/sbin
	- usr/src holds the Linux kernel sources header-files and documentation


## Text Editors
programs used for text processing(writing and saving).
1. Command line text editors: 
	- VIM
	- Nano 
	- Emacs
	- Neovim
2. Graphical Text editors
	- Sublime
	- Vscode
	- Gedit
	- Pluma

## VIM
- Before vi the primary editor used on Unix was the "line editor"(only one line)
	- user was able to see/edit only one line of the text at a time
- then the vi editor improved and developed VIM (VI iMproved)
- the vim editor is:
	- a very powerful
	- but at the same time is cryptic
	- is hard to learn, specially for windows users
- It have many modes
	- Command mode
	- Input/insert mode
	- Visual mode
	- Normal mode

### Opening Vim
- syntax [vim yourfilename]
- vim is by default on [Normal Mode] when you open it. To get on insert mode, you have to type "i"
- [Insert mode] - you can type and edit ur text
- [Command mode] - press "esc"
	- Save ":w ENTER"
	- Quit  ":q ENTER"
	- Save and Quit ":wq ENTER"
	- Force Quit & save  ":wq! ENTER"
	- Undo ":undo ENTER"
	- Execute bash commands ":%!yourcommand"
	    NO space between them
	     after grep, filtering a word do you have to UNDO?
- [Visual Mode] 
	- allows users to select and manipulate blocks of text
	- Types of Visual Mode
		- Character-wise: selects text character by character
			- Press "v"
		- Line-wise: selects entire lines of text
			- Press "shift + v"
		- Block-wise: selects rectangular blocks of text.
			- Press "ctrl + v" or "ctrl + q"
	- Commands on Visual Mode - after you select
		- d: Delete the selected text
		- y: Yank (copy) the selected text
		- p: Paste the yanked text after the cursor


## NANO
- the GNU nano text editor is a user-friendly, free and open-source text editor that usually comes pre-installed in modern Linux systems.
- [starting nano] 
	- synthax nano [file name]
	- then start typing
- Nano hotkeys
	- Ctrl + S - save
	- Alt + U - undo
	- Alt + E - redo
	- Ctrl + X - exit
	- ^ is equal to Ctrl
- Paste, Copy & paste all over the linux is
	- Alt + 6 - copy
	- Ctrl + Shift + X (F9) - cut 
	- Ctrl + Shift + U (F10) - paste 

Main nano help text
- Ctrl G

To append a file into ur current file:
- Ctrl + R then file name (if not on same directory - write path then FileName)

^ is it keyt????
is vim and nano application to be installed

====P2====

## Linux User Management
- On Computer system, a person who uses the compiler is called "[user]"
- Every users have Group
- Group is a collection of users that share the same permissions to access files, directories and resources
- users have their  own file & applications.
- to know our name on linux -> "whoami"
- those users have power/privilage
- On linux there's 2 kinds of users
	- Root id = 0
	- Normal User id starts with 1-999
	- 1000 given for 1st local user
- the root user have the power to do everything on linux
- but if users want to have a root access they add [sudo] infront of the command.
	- sudo YourCommand
- SUDO = Superuser Do, used to pass permission denied


## Creating Users
you have 2 ways:
- Useradd command -> simple
	- sudo useradd username
	- NOT FOUND in the home directory
	- shell type is "bash"
- adduser command -> detailed
	- sudo adduser username
	- shell type is "sh"
- the user files are stored inside "cd /etc/passwd"
- the user password are stored inside "cd /etc/shadow"
	- only root has access
- when you create a user [it creates a group with that name]
- to know the id of user
	- id username


## [TO ACCESS ROOT USER]
Command
- [sudo su]
if you do "cd root/root"
- yerasu personal file yetekemetebet bota slehone

