
## FURTHER ON USER MANAGEMENT

Some advanced user commands
- To change password of user
	- sudo passwd username
- To change user ID
	- sudo usermod -u new_id username
- To delete user
	- sudo userdel -r username (recursive)
![[Pasted image 20250515071316.png]]
- To change users on terminal
	- su - username ??? is the - necessary
- To go back to local user
	- exit

- [sudo mkhomedir_helper YourUserName
	- is used to CREATE A HOME DIRECTORY for a specified user in Linux, typically when the user is being added to the system without an existing home directory

- [sudo usermod YourUsername -s /bin/ NewShell
	- changes the DEFAULT LOGIN SHELL  for the specified user to the specified shell (eg.,/bin/bash???)
	- to check shell type of current user [echo $SHELL]
	- the ckeck shell type of all and more info [cat /etc/passwd]
	- for those created with SUDO USERADD
		- if created with useradd shell type is "sh"
		- To open the shell -> [sudo su - username 
		- shortcuts may not work 
		- to get out - write exit


SOME ADVANCED GROUP COMMANDS
- Create a New group (if not already created):
	- [sudo groupadd GroupName
- Add Users to the Group:
	- s[udo usermod -aG GroupName UserName
- Verify the user's Group Membership:
	- [groups UserName
- Remove User from the Group:
	- [sudo gpasswd -d UserName GroupName
	- Verify the User's Group Membership:
		- groups UerName

- [sudo mkhomedir_helper YourUserName
	- to create new home directory for a specified user in Linux, typically when the user is being added ot the systme without an existing home directory.
- [sudo usermod YourUsername -s/bin/shell
	- changes the default login shell for the specified user to the specified shell (eg. /bin/bash/zsh)



SUDOERS FILE
- [sudo su] - if not the 1st user others cant use SUDO commands
- the sudoers file is a file Linux and Unix administrators use to allocate system rights to system users
- the user you created doesn't have power to use "sudo" as the original one.
- this is because it is not Added in the sudoers file  
- to access this file:
	- [sudo visudo
- scroll down to "# user privilage specification"


- you can add the User you need to have access to the sudoers file, so he can use the sudo command
- then after the user can use sudo commands


LINUX FILE OWNERSHIP + PERMISSION
## Linux File Permission
- Every file on linux have their own 
		-  [ls -l]
	- owner
	- permissions
- There is 5 main parts on the listing
	- permission
		- starts with - or d
	- owners
	- date
	- size
	- filename

OWNERSHIP
- Ownership is the owner of the file
- This have 2 kinds
	- User
	- Group
- To change the owner of the file you can use the command
	- [sudo chown usr:group filename]
- Then you can access the admin.txt
	- [cat /home/qmrxe/admin.txt] qmrxe = new owner

PERMISSION
- there are 3 types of permissions
	- Read (r)
	- Write (w)
	- Execute (x)
- the folders and files differ with the 
	- "d" - (means directory) or
	- "-" - (meang txt or other file) on the beginning of the permission.


PERMISSIONS HAVE 3 PARTS

	- User - group - other
- User (u) - power of user defined on the ownership
- Group (g) - power of group defined on the ownership
- Other (o) - power of other users.
- All (a) - power of all which can be found in the 3 above owners
- Command to change permission of file
	- [ sudo chmod Option(+x or a+x) filename ] - execute for all (a=all)


CHMOD commad
- this command helps to change file permission
- those file permissions are read, write & execute
- each of the permission have a number representations
	- Read -> 4 - r [cat filename]
	- Write -> 2 - w [nano filename]
	- Execute -> 1 -x [???]
- Syntax
	- [chmod Parameter filename] parameter = r/w/e/4/2/1



			+ is giving the permission
			- is taking/removing
- The parameter can be in numbers and symbols

A. PARAMETERS IN SYMBOL
- chmod a+x filename -> adding execute permission for all (chmod +x filename)
- chmod u+x filename ->adding  execute permission for user
- chmod g+x filename -> adding execute permission for group
- chmod o+x filename -> adding  execute permission for other
- chmod -x filename -> removing execute permission for all
- chmod a+rwx, u-rw, g-xw
- filename -> give rwx for all and removed something from ????

[sudo chmod a+rwx,u-wx,g-r,o-rx filename]
[sudo chmod a-rwx,u+r,g+rx,o+rw]

B. PARAMETERS IN NUMBER
- chmod 621 filename -> 6 for user, 2 for group, 1 for other (6=4+2), 6=rw
- chmod 777 filename -> 7 for users, 7 for group, 7 for others (7=4+2+1), 7=rwx
	- drwxrwxrwx
- [sudo chmod 740 qmrxe]



===P2===


### Special File Permissions
- thera are another 3 special permissions, you may envounter on your pentest journey. They are
	- SUID bits(s) - set user ID bit - add 4 infront of our numeric value -> 4000 - [4 is special 000 is normal]
	- SGID bit(s) - set group ID bit - add 2 infront of our numeric value -> 2777
	- Sticky bits(t) -> set other ID bit - add 1 infront of our numeric value -> 1602
- These are permissions like the [execute (x)], but they will set the execute permission to the user who settled them.
- Eg. if Mr. a added suit bit to a program then any user can execute the program with permission of Mr. a
	- meaning if root add suit bit on some program. Then any user got that program they can run it as root without any sudo password.
- [sudo chmod +s(or a+s -> both works for all) `<filename>`] - user & group
- [sudo chmod +t `<filename>`] for other

Example
- This is A Computer Program Written in C, We will see SUID bit Powerfullness with this Program.
- This program will try to open ["/etc/shadow"] and if the permission is correct, it wil respond "[Successfully opened/etc/shadow file]". But if the permission does not meet it will respond with "Unable to open /etc/shadow".

you can use [./] to run programs
![[Pasted image 20250521094240.png]]
![[Pasted image 20250521094256.png]]

- After changing the owner of the Binary/Program, Still is not running.
![[Pasted image 20250521094515.png]]
![[Pasted image 20250521094525.png]]
- Here comes the interesting part. Now, the owner of the file is root. So if the root user set a SUID bit on the program that means, we can run it with the file owner's privilage and permission.

2 ways alu malet new
- chown root
- cd to root argen file create senareg - which is the same thing

??????????? /etc/shadow access VS ./ VS file VS Folder access VS /etc/shadow
cd bchawn - wede HOME new???
acess the vim??? around 1:04


if it starts with 
- l - symbolic linking file 
- its like how some files start with d or -

### Package Installation on Linux
- ON linux to install softwares you use package managers.
	- Eg. apt, pacman, pkg
- We will use debian package manager.
- On debian the package manager is calle "APT" also there is called "dpkg"
- Package managers are a free-software user interface that work with an online server to handle the installation and removal of software on Debian, and Debian-based Linux distributions.
3 files are downloaded
- metadata
- packages
- dependencies
![[Pasted image 20250521111604.png]]
repository - online server


The repository
This is the site/server kali use to upload packages
- http.kali.org/kali/


## Advanced package tool /apt/
- Apt is a free-software user interface that work with an online server to handle the installation and removal of software on Debian, and Debian-based Linux Distributions. used for online and offline purpose.
- The old 'apt' used as '[apt-get]'
- Syntax
	- sudo apt update - tells u if packages on ur linix HAVE updates
	- sudo apt search `<softwarename>` 
	- sudo apt install `<softwarename>`
	- sudo apt remove `<softwarename>` - removes only the Package
	- sudo apt upgrade `<softwarename>` - INSTALLS updates 
	- sudo apt purge  `<softwarename>` - removes all the 3 - metadata, package and dependency - when u reinstall if these are found in it (metadata and dependencies) since yo used REMOVE while deleting the package, it stops installing thinking that its already installed, it so its better to delete them all.


Package dependencies
- a sw can be built based on another program called "modules." 
- So, a program to work properly, the dependencies have to be installed successfully.
- those package managers install the software + dependencies.
![[Pasted image 20250521150454.png]]



WHAT IS METADATA????


Common Linux Repository Errors
1. Could not get lock /var/lib/apt/lists/lock
	- this occurs when you run 2 different apt's or if there is another apt process running on Background, for this you can simply solve it by restarting your PC of closing the another apt process.
![[Pasted image 20250521151254.png]]
2. Could not open lock /var/lib/dpkg/lock-frontend
	- This occurs when you forget to run apt with root user aka 'sudo'
![[Pasted image 20250521151459.png]]
3. Unable to locate package
	- This occurs when you Miss spell the program name.
	- or if the one u want to install is not in the repository/server

4. The repository 'http://http.kali.org/kalikali-rolling Rekease' does not have a Release file
	- this occurs when there is a  problem on the repository configuration link. Sometimes the link might be broken.
![[Pasted image 20250521151812.png]]
	- repo confit link is on [nano /etc/apt/source.list] 
	- OR
	- [sudo apt edit-sources
	- you have to put the correct link "deb http://http.kali.org/kalikali-rolling main contrib non-free", this might differ based on the Distro you can search the repository link on google or chatGPT

For more...
- Dont close apt while installation
- Repository errors, if this happened you can fix it using 
	- sudo apt edit-sources
- For those kinds of errors what you have to do is google/youtube {detail we will see this while we learn Footprinting}


Dpkg /Debian package Manager/
- Dpkg is an offline package manager program.
- packages on debian have an extension ".deb"
- Syntax
	- sudo dpkg -i `<packagename>` - install
	- sudo dpkg -r `<packagename>` - remove only the package
	- sudo dpkg -p `<packagename>`- purge - removes all


Termux - .pkg
[sudo apt autoremove] - removes those whose packages are removed