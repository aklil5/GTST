# Network Hacking 🔥
Created on: 

Topics:
- What is Network Hacking?
- Network footprinting
- Network sniffing
- Network Captures
- Network Captures
- Mac attack
- Arp poisoning
- DNS Spoofing Attack
- DOS and DDOS Attacks
- General Prevention Techniques




----
==P1==
# What is Network Hacking?
- Network Hacking is [gathering and exploiting of networks.]
- Network Hacking is a branch of computer security related to networks hacking an dthe penetration of a target via the networkig services or equipment.
- This includes:
	- Network information gathering
	- Sniffing
	- Network Attacks


----
# Network footprinting
- There are Different tools, that cna help Us on Our Network Recon Process.
	- Nmap
	- Ping
	- TraceRoute
	- Arp
	- Netstat
	- ss

---
## Ping
- Ping is one of the most fundamental and widely used network utilities.
- It's primarily used to test the connectivity between two network devices by sending ICMP.
- We can Perform Different Changes With Ping Command
	- Count (-c)
	- Packet Size (-s)
- Variants of Ping:
	- fping: to ping multiple hosts simultaneously.
	- nping: allowing more advanced packet crafting and timing tests.
	- hping: A more advanced tool that allows sending custom TCP, UDP and ICMP packets.


## Traceroute
- Traceroute is a network diagnostic tool used to trace the path that packets take from a source to a destination across a network.
- It helps determine the route taken by packets and measures the time taken for each hop along the way.
- By Default uses ICMP requests track.
- Some Routes Block ICMP's or might be set to be invisible then we might see (`****`) so to fix that we can use Dynamic Traces Usig MTR.
	- Syntax `mtr google.com`

## Netstat
- netstat (short for Network Statistics) is a command-line utility used to display network connections. You made, routing tables, interface statistics, and multicast memberships.
- Functions of netstat
	- Display Active Connections
	- Show Listening Ports
	- View Network Interface Statistics
	- Display Routing Tables



## ss
- ss (Socket Statistics) is a utility used to investigate sockets and it provides detailed info about network connections, listening ports and more
- It is often preffered over netstat for its faster performance and more detailed output
- -t: tcp
- -u: udp
- -l: listening
- -p: process


# Exercise 1
1. Send a 100 size ping request to google.com
2. What ports are open on your Computer
	1. and observe which services opened the port
3. What are the network routes to get geezsecurity.com




----
# Network Sniffing
- Sniffing is the process of monitoring and capturing all the packets passing through a given network using sniffing tools. It is a form of "tapping phone wires" and get to know about the conversation

## Types of Sniffing
1. Passive Sniffing
	- 
2. Active Sniffing


# ...
- To Sniff on Networks, There are many Tools we can use
	- 

## WireShark
- 
















========================================================


==P2==
