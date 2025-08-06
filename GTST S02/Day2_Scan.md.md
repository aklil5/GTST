# Scanning and Enumeration 🔥
Created on: 30/10/17

Topics:
- What is Scanning?
- why do we scan?
- Network Scanning
- Nmap
- Host Detection
- OS detection
- Banner Grabbing
- NSE
- Firewall Evasion Techniques


----
==P1==
# What is Scanning?
- Scanning is the 2nd phase of Ethical Hacking.
- It is the step which help to examine/Test a system based on the information we gathered and also sometime they help us to gather Additional information.
- Scanning is the [active phase] of probing a target to identify vulnerabilities, services, open ports, and more. It is active interaction. 
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
# Why do we do scanning?
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
	- `nmap IP/`
- It is used to scan Network, Ports, OS....
- It is made for windows and linux
- On kali linux it is built in a tool.
- To check the existence of nmap on your system
	- `nmap --version`

- it has switches or options for customized scan
	- -sT, -sS, -sU, -p, -sV, -O, -A, -T<0-5>, -oN, -oX, -oA, -sC, `--script=<filename>` ....
  
## Live System Discovery
- Discovering live system means, Checking up and running hosts (clients/servers) on a network.
- We have seen Host checking last time with ping sweep method. (getting ip of website)
	- But How does the ping worked?


### Ping Sweep
- This is a method of checking if host is up or down.
- It uses ICMP (Internet Control Message Protocol) [packets] for checking purpose
- It sends [Echo request] and waits for response if there is [Echo reply] then that system is up!
![[Pasted image 20250710101721.png]]


![[Pasted image 20250714182201.png]]

![[Pasted image 20250714182251.png]]
 


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


---
# Nmap ping sweep
 - Nmap can perform ping sweep too.
- Syntax
	- `nmap -sn IP`                 -sn = no port scan, only check if its alive or not, its a FLAG


---
# Host Discovery 
How do we identify all hosts on a network?
- ping can take 1 host only??
- Nmap can scan the whole range.
- You can do the ping sweep with little modification on the IP 
- Syntax:
	- nmap -sn NetworkAddress-255
	- nmap -sn NetworkAddress/networkBits(subnet mask)
		- CIDR notation
			- Network bits depend on the IP Class/subnet
			- Eg. `nnmap 192.168.1.0/24`
			- Vs
			- `nmap -sn 192.168.1.0/24`
- This will not work on virtual machines network.

demo
- Scanned all the network range and found how many hosts are up.
	- `nmap -sn 192.168.56.0-255` or .0/24


----
## Warning+=1
- Doing ping sweep is way of Active Recon.
- You are trying to ping the ip 192.168.56.102
- And you are trying to do security pen-test on my system. And you are script kiddie.
- But am a security Guy, so...

BOOM!!
- On wireshark
- i can see you on my system when you try to do pings on my system. BE SAFE!
	- Blue Team Hackers Do this. Like {log analysis, SOC analysis, Intrusion Detection, Incident Response}

## Warning ++
- Some organizations or system admins, will block any [ICMP requests]
- Here the ping sweep wont work, and when you try this it says "host is down" but it is normally up
- To make it work we just skip Ping requests and ask for additional things
	- `nmap IP` - will ping first then scan it so 
- Syntax:
	- `nmap -Pn IP`
- This method will jump <span style="color:rgb(255, 192, 0)">host discovery</span> because it will take the ip as Up and try to do <span style="color:rgb(255, 192, 0)">port discoveries.</span> jump ping (no need for ping)


`nmap scanme.nmap.org`
![[Pasted image 20250710104724.png]]
- nmap result have lots of things inside it

---
# What is PORT?
- Port is [process-specific] or an [application-specific] construct serving as a communication **endpoint**, which is [used by the Transport Layer protocols] of Internet Protocol suite, such as User Datagram Protocol (UDP) and Transmission Control Protocol (TCP)
- It is like a door for some purpose/service
- Example: if you want to get in the your house by which method do you get in?
	- BY DOOR
- Here there are different objects to get in, if wind is needed in the house we might use windows.
- So here in there senario
	- Windows are for winds
	- Doors are for human
- These are ports those can help u to get it.


A port is just a number that tells the computer what kind of data is coming or going, and which program should handle it.


- Also your home can have different doors and the main gate in your bedroom can be number 1, the salon door is number 2.....
- On computer there are different 65,536 ports with different jobs (like the window and door)
	- 1-1024 = reserved (well known) ports
- Example:
	- HTTP(80) - unsecured Web port
	- HTTPS(443) - secured web port
	- FTP(21) - File transferring port
	- SSH(22) - Secure shell port
![[Pasted image 20250707211741.png]]

----
# Port status
ports can be on different status
- *Open ports
	- These are ports open for accepting any requests/connections
	- service is running on that port
	- Having an open window can lead to any kind of gas or air getting to our house
- *Closed ports
	- These are ports which are not accepting ay request but there is some service 
	- Ex. Having your home door close
		- still the door helps sometime, but not for now
- *Filtered ports
	- These are ports which nmap is not sure of being open or closed.


----
## Open port discovery
- On some system ports can be open for some purpose
- Example:
	- anywhere when you access websites there is web port open (80, 443, 8080 mostly),
	- If you are getting some shell activity there is port 22 open
- The Main Problem/Vulnerability is there Might be some ports open without intention or Opened Once and forgot closing, this leads to attack
- We can use nmap to check which port is open/closed
- And this is called port discovery
- Syntax:
	- `nmap IP(Domain)` => only the 1000 ports
	- `nmap -p port1,port2,port3 IP(Domain)` => only port 1,2,3
	- `nmap -p- IP(Domain)` => All the 65K port

Red Team Perspective
- Port Scan will be done, By sending TCP request to that specific port to try to connect.
![[Pasted image 20250715080813.png]]

Blue Team Perspective
- Every port Connecting Trials are Recorded in the network packets you send.
![[Pasted image 20250715080959.png]]


---
## We can use Another Trick with netcat
if you dont have nmap
- `nc -nv IP port`

![[Pasted image 20250710110135.png]]

----
# Scanning methods
- Nmap scans network in different modes
	a. TCP connect (TCP scan)
	b. TCP SYN (Stealth scan)
	c. UDP scan
	d. Xmas scan


----
## TCP Scan
- As we saw last time TCP is the best on doing connection oriented things.
- This is [Nmap's default Scan.]
- It is reliable But how?
- This is Because it used [3-way HANDSHAKE]!!!
- what is 3-way handshake?

## 3 way handshake
- When you establish a TCP connection there is something going behind the scenes
- What was the packet sent while the Ping sweep, it was the ICMP.
	- Here when we start connection we will send a synchronization flag.
	- When the server got and accepted our request, it will reply with synchronization and Acknowledgemnet.
	- Finally, we will send Acknowledgement or Reset (RST) and continue because we have connection/network now.

It is like meeting someone.
1. You: hi.
2. They: hello
3. You: Nice to meet you..

- TCP scan works like this, so nmap will send the SYN request to the ports and if they reply with SYN/ACK nmap will reply with ACK 
- BOOM!!! The port is open!! Else the port is closed/filtered.
v
Syntax
- `nmap -sT IP`

Red Teamer Perspective
- An attacker can Run this Scan.
- Note: <span style="color:rgb(255, 192, 0)">By Default Nmap performs TCP scan whether you provide -sT or not.</span>

Blue Team Perspective
- As you can See there is a 3 way Handshake this means, this scan is a TCP scan.


----
## Stealth Scan
- This is TCP scan but here we dont send the last ACK flag.
- But we send the RESET flag.
- Syntax:
	- `sudo nmap -sS IP`
![[Pasted image 20250710165607.png]]

Red Teamer Perspective
- An Attacker Can Run this Scan

Blue Team Perspective
![[Pasted image 20250710165810.png]]
- As you can see the last ACK flag is replaced with RST, so this one is Sealth Scan.


----
## UDP Scan
- This is a method to scan if any service/port is using UDP
![[Pasted image 20250710165949.png]]

- it is a slow process
- Syntax:
	- sudo nmap -sU IP
- There are some ports work on UDP, SO we need UDP scan

- So we can do Pentest do UDP and TCP scans together
	- `nmap -sU -sS -sV IP`


----
## Xmas Scan
- Here the 1st thing to send is FIN/PSH/URG (finish, push, urgent) instead of SYN.
- If there is response like RST flag Then the system is closed.
- If there is no response the system is open.
- Syntax
	- `sudo nmap -sX IP`

Red Teamer Perspective
- An attacker can run this Scan
	- `sudo nmap -sX google.com -p 80,8080,2`


============================================================
==P2==

# Operating System Detection
- Nmap have a feature to detect the operating system of the host. The OS is Determined By the Response of the Open and Closed Ports.
- Syntax:
	- `sudo nmap -O IP` => OS detection only
	- `sudo nmap -A IP` => OS detection including version

nmap flags
- -sT
- -sS
- -sU
- -sA
- -O
- -A (aggressive scan)

# Banner Grabbing
- Banner Grabbing is a technique of Ex-filtrating [Version] of some Service.
- The "[banner]" refers to the text or metadata that a service or application sends back when you connect to it, which often contains details about the software, its version, and sometimes even the operating system.
- We Use -sV Flag to get the Version and Service Detail
- Syntax:
	- `nmap -sV IP`

Red Teamers View
- sudo nmap localhost -p 80 -sV

Blue Teamers View
- On different Blue Teaming Software You can click on the Packet and Get Details


----
## Scan Speeds
- when nmap do its scan, it have a time waiting, after sending 1 packets to a host.
- There are 5 time waitings.
- The nmap time template is -T<0-5>
	- Insane -T5
	- Aggressive -T4
	- Normal -T3
	- Polite -T2
	- Sneaky -T1
Blue Teamers View


----
## 5. Nmap Insane
- sending packets insanely fast and waits **only 0.3 seconds**  for the response
- scan superfast but accuracy is sacrificed sometimes.
- Nmap gives-up on a host if it couldn't complete the scan within 15 minutes
- Other than than, -T5 should be used on a [fast network] and high-end systems as sending packets this fast can affect the working of the network or system and can result in system failure (DOS).
- Syntax:
	- `nmap -T5 IP`


----
## 4. Nmap Aggressive
- This template is used for sending packets very fast and waits only **1.25 seconds** for the response
- Nmap official documentation recomends using -T4 for "reasonably modern and reliable networks."
- Syntax:
	- `nmap -T4 IP`


----
## 3. Nmap Normal
- This is a [defualt] nmap timing
- Syntax:
	- `nmap -T3 IP`


---
## 2. Nmap Polite and Sneaky
- These are the slowest timing.
- Being slow, helps to not be detected on some risky projects.
- Syntax:
	- `nmap -T2 IP`
	- `nmap -T1 IP`


----
# Nmap Scripting Engine (NSE)
- Nmap is capable of running some script on ports and services.
- These scripts are written in lua-programming language.
- These scripts are located in /usr/share/nmap/scripts.
- Nmap contains a total number of 589 scripts (Version 7.70), there are a lot of scripts that are useful but not all of them work perfectly, it's like other tools a better for that particular task, so we'll look at how we can use the powerful NSE and what scripts to use.
- You can Write your own script too if you can do lua
- Syntax:
	- `nmap -sC IP`
	- `nmap --script scriptname.nse IP`
	- `nmap -p 22 --script ssh* IP`

cd /usr/share/nmap/scripts

- Some known scripts
	- --script banner
		- grabbing some detials
	- --script broadcast
		- reveals broadcast information
	- --script vuln
		- test if the ports are vulnerable

`nmap -sV -A isS -o 21 10.2.3.1 --script ftp\*


we can combine them like
- -sTCV


---
# Nmap Outputs
- Nmap can Save your output using the "-oGl-oXl-oN"
	- -oG -> For Greppable formats
	- -oX -> for xml Formats
	- -oN -> for Normal Saving Formats



after saving it to file named grepable
- cat grepable
- cat grepable | grep 80

---
## Nmap Verbose
- Displaying more information and Logging them is called Verbose.
- You can also add -v flag to call verbose
	- -v - little detail
	- -vv - more detail
	- -vvv - much more detials


----
![[Pasted image 20250719103159.png]]

1. nmap -sU geezsecurity.com
2. nmap -sS geezsecurity.com
3. nmap -O  geezsecurity.com
4. nc -nv geezsecurity.com 80
5. nmap --script vuln 
	1. nmap --script vuln -T4 geez
	2. nmap --script vuln vv geez
	3. nmap -oN --script vuln vv geez output.txt


![[Pasted image 20250710213021.png]]

![[Pasted image 20250710213042.png]]

![[Pasted image 20250710213120.png]]
nv -nv geezsecurity.com 80



---
# Nmap Firewall Evasion
evasion - the act of avoiding something or someone
- Firewall Evasion Techniques Using Nmap is a subset of network security exploration aimed at bypassing or circumventing firewall protections using the Nmap tool.
- Nmap, known for its versatility in network scanning and reconnaissance, can be leveraged to craft pockets in ways that attempt to evade detection by firewalls or intrusion detection systems (IDS).
- **IDS (Intrusion Detection System)** is a security technology designed to monitor network traffic or system activities for signs of malicious behavior, policy violations, or other unauthorized activities.

Firewall Evasion Techniques
1. Decoy Scan
2. Fragment packets
3. MAC Address Spoofing
4. Source Port Manipulation

-----
## 1. Decoy Scan
- Nmap employs decoy IP addresses to obscure the origin of a scan, complicating the identification of the actual scanner.
- You can specify multiple decoy IP addresses using the -D option within the Nmap command.
	- `nmap -D decoy1, decoy2, decoy3.... Target IP`
- You can make Nmap to add some random IPs
	- `nmap -D RND:5 Target IP`
- This makes it Hard for the sysadmin to block 

----
## 2. Fragment Packets
- Fragmented requests refer to the technique of sending packets in smaller fragments rather than as whole packets.
- This is done to evade detection by firewalls, intrusion detection systems (IDS), or intrusion prevention systems (IPS)that [rely on analyzing entire packets] to detect malicious activity.
- To perform this:
	- `nmap -f -p21 Target IP`


---
## 3. MAC Address Spoofing
- This approach can be particularly potent, particularly when a firewall employs MAC filtering to permit communication exclusively from designated MAC addresses,
- By employing a spoofed MAC address, your scan operates stealthily as your genuine MAC address remains concealed in the firewall log files.
- To do this:
	- `nmap -spoof -max Apple/MAC_ADDRESS -On IP


---
## 4. Source Port Manipulation
- The source port identifies the specific application or process on the client device that initiated the communication.
- The destination server uses the source port of 




===================================================
# Creating Virtual Environment in VSCode

1. make sure Python is installed
	- python3 --version
2. Open Vscode and your project
	- open the folder or workspace where you want to use the nmap module
3. Open the terminal in VSCode
	- Terminal > New Terminal
4. Create and activate a virtual environment
	1. python -m venv venv
	2. source venv/bin/activate
5. install the python-nmap package
	1. pip install python-nmap
6. Verify the installation
	1. pip list | grep python-nmap
7. Use the module in your Python code
	1. import nmap


if its netifaces
1. 1. **Activate your virtual environment** (if you're using one)  
    If you're using a virtual environment, activate it first:
    
    - On Windows:
        
        css
        
        `path\to\your\venv\Scripts\activate`
        
    - On macOS/Linux:
        
        bash
        
        `source /path/to/your/venv/bin/activate`
        
2. **Run the pip install command**  
    Type the following command and press Enter:
    
    bash
    
    `pip install netifaces`
3. `python -m pip install netifaces`