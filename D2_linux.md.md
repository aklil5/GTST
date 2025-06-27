Every Hacker should know
Networking , Programming, Linux, System administration

# What is Linux
- Linux is a kernel.
before, Kali Linux used to be called Backtrack 

# What is Kernel

- kernel is a "code/program" that used to meet your SW and HW. 
- And allocate some resources.
-![[Pasted image 20250430201608.png]]


# History of Linux
- in 1969 a team lead by computer scientists Ken Thompson and Dennis Ritchie created the first version of "UNIX" on a PDP-7 minicomputer.
- which was chosen mainly because of Thompson's familiarity with the system from his hobby work on it.

BUT IT WASNT CHEAP AND OPEN-SOURCE

- the person called "LINUS TORVALDS" created the "Linux kernel". And posted it online to make it open-source. And it was developed in C programming language.


- "Richard Stallman" announced the GNU project in 1983 and cofounded the Free Software Foundation in 1985.
- GNU is a free software replacement in the UNIX OS, But it was just software replacement not full os {Example: Bash, tar, emacs}

- So GNU + LINUX will give the GNU/Linux OS. 
- The GNU Linux project was started to create a Unix-like OS created with source code that could be copied, modified, and redistriibuted.
- OS - needs
	- kernel and
	- SW part

# What is Shell and there types
## What is shell
- users communicate with the kernel by shell.
- the shell is a command Line Interpreter. It translates commands entered by the user and converts them into a language understood by the Kernel.

## Types of Shells
based on their features there are many shells.
- SH
- BASH
- ZSH - kali linux default
- FISH
They differ in coloring, piping(weta geba), command compilation, some kind of features.

TO IDENTIFY YOUR SHELL "echo$SHELL"
![[Pasted image 20250430204545.png]]

		Terminal - linux shell
		cmd - windows shell
		windows Powershell - windows shell


![[Pasted image 20250430204729.png]]

![[Pasted image 20250430204800.png]]
![[Pasted image 20250430204811.png]]

# What is OS - Operating System
- we have said UNIX and GNU/Linux as OS but what is OS.
- OS is the main software part of computer that helps to work on.

- it containes:
	- Kernel
	- Softwares
	- Desktop environment - graphical interface that provides users with a visual way to interact with the linux OS - >1 in linux
	- File extensions
	- Window manager
![[Pasted image 20250430205818.png]]
???


## Types of desktop environment on linux
A) mate
B) gnome - animated
C) KDE plasma - similar to windows
D) XFCE

Which Desktop envt is best?
- Speed depends on:
	- Animation
	- High Graphics
	- Quality
- 

## Windows Manager
- i3 - windows manager
		i3 is a popular tiling window manager for Linux that is lightweight, fast, and highly customizable. Instead of overlapping windows, it automatically arranges windows in a grid-like pattern, maximizing screen space and improving workflow efficiency.
	- different tasks on one screen and you dont need mouse, keyboard driven and lightweight
 ![[Pasted image 20250430210855.png]]

## Why Linux
- Fast
- Most Used
- Most hacking tools
- most secured - what we do is not monitored because it is open source



# Linux distributions/distro
Distro is modified linux kernels, type of OS with different:
- linux kernel
- packages (GNU) - SW
- package manager - like a Microsoft in windows - to install linux SWs
- desktop UI - desktop envt 


So many distros - modified OS form GNU-linux
- Debian
	- Kali linux
	- Ubuntu
	- Parrot
- Arch
	- Black arch
	- Garuda
- Fedora 
- Red Hat
- Gentoo
- Android


What is best for hackers?
- Kali linux
- Parrot Os - developer mode and hacker mode
- Garuda
- Black Arch
- Ubuntu - no tool only terminal, you customize it, like windows

### Kali Linux
is a Debian-derived Linux distribution designed for digital forensics and penetration testing. It is maintained and funded by Offensive Security.

- Desktop Env: xfce
- Package manager: apt like app store
- Shell: zsh


### Parrot Os
is a linux distribution based on Debian with a focus on security, privacy , and development.

- Desktop env: mate
- package manager: apt
- shell: bash

### Garuda
garuda linux is a linux distribution based on the Arch Linux Os
- Desktop env: KDE plasma
- Package manager: pacman
- shell: fish


 Do windows have distros?
- windows is not open-source so people won't use/edit it, so there won't be other kind.
- it just gives updates and adds some feature on it.

## How can we use it- 6 ways
### A) Main OS/ Main - boot
- Kali Linux installed as the sole OS on the machine
- advantages: 
	- performance
	- simplicity
	- security
- disadvantages:
	- no access to other OS
	- data loss risk


### B) Dual Boot/2 in 1
- Kali linux installed alongside another operating system (usually windows or another linux distribution)
- advantages
	- access to multiple os
	- data preservation
- disadvantages
	- complexity resource sharing

### C) Live Boot
- Refers to running an OS directly from a removable media (like a USB drive or DVD) without installing it on the hard drive of your computer.
- Advantages:
	- privacy
	- no risk of data loss
- disadvantages:
	- resource sharing


### D) Cloud Terminal
https://www.webminal.org


### E) Virtual System
- you need host Os - windows or Mac
- Virtualization - method to allocate our memory to the virtual machines/Vm's
- Two types
1. Type 1 Virtualization (Bare-Metal Hypervisor)
	Hardware => Hypervisor
	- runs directly on the physical hardware
	- doesnt require a host os
	- example: VMware ESXi, Promox, Xen
	- Advantages:
		- High performance and efficiency
		- better resource management and isolation
		- commonly used in enterprise envts for server virtualization


2. Type 2 Virtualiation (Hosted Hypervisor)
	Hardware => Host OS => Hypervisor
- Runs on top of a host OS
- relies on the host OS to manage hardware resources
- Eg. VMware Workstation, Oracle Virtual Box
- Advantages
	- easier to set up and use
	- suitable for personal or devt envt

We need Hyper Visor
- Oracle VB(virtual box)
- VMware

Your have to check some system about VM
1. open task manager
2. goto performance
3. open CPU
	 - if Virtualization is disabled, you have to enable in BIOS settings (check youtube). 
	 - if it is enabled we are good to go

### F) WSL v2/Windows Subsystem for Linux

- gives you linux terminal
- Preferred
- go to windows powershell and - run as administrator
- write down 
	- Enable-WindowsOptionalFeature -Online -FeatureName Microsoft_Windows_Subsystem-Linux
- the download kali-linux or ubuntu from MS store

To decorate it
- download Windows Terminal from MS Store
### G) Termux - Android
- for running some codes
- And doing simple things!
- package manager - pkg

For iphone - ISH


Based on your computer Performance, choose one method from the 6 and setup it

Access revoked


## // INSTAL VIDEOS
 
linux ISO file
GRUB boot loader

you can change the splash screen

Hyper Visor
- Oracle VB - insert guest addition 
	- to install files for the VB
- VMware - 

