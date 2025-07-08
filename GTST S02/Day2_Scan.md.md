# Scanning and Enumeration 🔥
Created on: 30/10/17

Topics:
- What is Scanning?
- why do we scan?
- Network Scanning
- Nmap
- Host Detection


----
==P1==
# What is Scanning?
- Scanning is the 2nd phase of Ethical Hacking.
- It is the step which help to examine/Test a system based on the information we gathered and also sometime they help us to gather Additional information.
- Scanning is the [active phase] of probing a target to identify vulnerabilities, services, open ports, and more.
- Scanning Focus more on [Systems] than peoples.

## Focus
- **Reconnaissance**: Focus on [broad, high-level information] about the target.
	- It may include:
		- Organizational Structure and employee details (social engineering possibilities).
		- Publicly available IP addresses and domain names.
		- Technology stack (eg. web servers, frameworks).
		- Potential entry points from open sources (e.g. website vulnerabilities, exposed subdomains).
- **Scanning**: Focuses on [technical, low-level details] about the target's systems, 
	- such as:
		- Open ports and services
		- Operating system and service versions.
		- Network topology
		- Specific vulnerabilities in the systems and services.


---
# Why do we do scan?
- It helps to identify HOST's System informations
	- Operation system
	- service versions
- To Discover Open Ports
- To Discover Live Systems


---
# Network Scanning

- This is a method of Scanning a network and getting more informations.
- There are Many kinds of scanning methods and tools for different purpose
	- **For Network mainly**: NMAP, netdiscovery
	- **For Subdomain**: Sublist3r, subfinder, amass
	- **For website**: Nikto, WhatWeb, FFUF..


---
## Nmap - Network Mapper
- Nmap is A network scanning and exploring tool used by network and security experts.
- It is used to scan Network, Ports, OS....
- It is made for windows and linux
- On kali linux it is built in a tool.
- To check the existence of nmap on your system
	- `nmap --version`


## Live SYstem Discovery
- Discovering live system means, Checking up and running hosts (clients/servers) on a network.
- We have seen Host checking last time with ping sweep method. (getting ip of website)
	- But How does the ping worked?


## Ping Sweep
- This is a method od checking if host is up or down.
- It uses ICMP (Internet Control Message Protocol) [packets] for checking purpose
- It sends [Echo request] and waits for response if there is [Echo reply] then that system is up!

This is my ubuntu server and the ip is "192".............

Lets check if my ubuntu server is UP! With ping sweep
- From echo requests we can gather the following informations
	- OS type
		- Windows (32 byte)
			- ttl=108
		- Linux (64 byte)
			- ttl=64
	- Connection stability
		- Time
- TTL: time to live
	- determines how long a packet should exist in the network before being discarded
	- **Decrementing TTL:** each time the packet passes through a router (a hop), the TTL value is decreased by 1.
	- **TTL Expiration:** If the TTL reaches 0, the packet is discarded, and an ICMP "Time Exceeded" message is sent back to the sender. (not reached)

delivering or reaching time???????? which one

## Nmap ping sweep
- Nmap can perform ping sweep too.
- Syntax
	- `nmap -sn IP`                 -sn = no port scan, its s FLAG??????


---
# How do we identify all hosts on a network?
- ping can take 1 host only??
- Nmap can scan the whole range.
- You can do the ping sweep with little modification on the IP 
- Syntax:
	- nmap -sn NetworkAddress-255
	- nmap -sn NetworkAddress/networkBits(subnet mask)
		- CIDR notation
			- Network bits depend on the IP Class/subnet
- This will not work on virtual machines network.


- 

![[Pasted image 20250707204743.png]]

Warning+=1
- Doing ping sweep is way of Active Recon.
- You are trying to ping the ip 192.168.56.102
- And you are trying to do security pentest on my system. And you are script kiddie.
- But am a security Guy, so...

BOOM!!
- i can see you on my system when you try to do pings on my system. BE SAFE!
	- Blue Team Hackers Do this. Like {log analysis, SOC analysis, Intrusion, Detection, Incident Response}

Warning ++
- Some organizations or system admins, will block any [ICMP requests]
- Here the poing sweep wont work, and when you try this it says "host is down" but it is normally up
- To make it work we just skip Ping requests and ask for additional things
- Syntax:
	- nmap -Pn IP
- This method will //////////////////


`nmap scanme .nmap.org`



---
# What is PORT?
- Port is [process-specific] or an [application-specific] construct serving as a communication **endpoint**, which is [used by the Transport Layer protocols] of Internet Protocol suite, such as User Datagram Protocol (UDP) and Transmission Control Protocol (TCP)
- It is like a door for some purpose/service
- Example: if you want to get in the your house by which method do you get in?
	- BY DOOR
- Here there are different objects to get in, if wind is needed in the house we might use windows.
- So here in there senario
	- Windows are for winds
	- t


////
A port is just a number that tells the computer what kind of data is coming or going, and which program should handle it.


- Also your home can have different doors and the main gate in your bedroom can be number 1, the salon door is number 2.....
- On computer there are different 65,536 ports with different jobs (like the window and door)
	- 1-1025 = reserved (well known) ports
- Example:
	- HTTP(80) - unsecured Web port
	- HTTPS(443) - secured web port
	- FTP(21) - File transferring port
	- SSH(22) - Secure shell port
![[Pasted image 20250707211741.png]]

Port status
ports can be on different status
- Open ports
	- These are ports open for accepting any requests
	- Having an open window can lead to any kind of gas or air getting to our house
- Closed ports
	- These are ports which are not accepting ay request but there is some service 
	- Ex. Having your home door close
		- still the door helps sometime, but not for now
- Filtered ports
	- Thesea re ports which nmap can/////////////////

## Open port discovery
- On some system ports can be open for some purpose
- Example:
	- anywhere when you access websites there is web port open (80, 443, 8080 mostly),
	- If you are getting some shell activity there is port 22 open
- The Main Problem/Vulnerability is there Might be someports open without intention or Opened Once and forgot closing, this leads to attack
- We can use nmap to check which port is open/closed
- And this is called port discovery
- Syntax:
	- nmap IP(Domain) => only the 1000 ports
	- nmap -p port1,port2,port3 IP(Domain) => only port 1,2,3
	- nmap -p -IP(Domain) => All the 65K port

Red Team Perspective
- Port Scan will be done, By sending TCP request to that specific port to try to connect.

Blue Team Perspective
- Every port////////

We can use Another Trick with netcat
- `nc -nv IP port`



============================================================
==P2==


