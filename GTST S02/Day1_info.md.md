Date: 25/10/17
Topics: 
- Introduction to Penetration testing
- Pre-Engagement Steps
- What is information Gathering /Footprinting/
- What informations can be Gathered?
- Types of Recon
- How we gather information
- Reverse image search
- Google hacking Database
- Shodan Dorking
- Github Dorking

===========================================================
==P1==
# Introduction to Penetration Testing
- We have discussed what penetration testing is and its Types.
- Now we are going to see steps we take before getting to Penetration testing tasks, as an Organization which gives Penetration Testing Service.
- On performing Penetration testing for companies, there are some additional steps than the 5 Phases of Ethical Hacking.
	a. Pre-Engagement
	b. Information gathering
	c. Scanning
	d. Gaining Access
	e. Maintaining Access
	f. Proof-of-concept
	g. Post-Engagement
- This course approach is more Red-Team side. But we try to see some Blue team.
	- Red Team Understanding is very crucial for the blue team.

---
## A. Pre-Engagement Step
- Thisis the 1st step, and the **Main Legal Part** of the process.
- This is Held, before Starting any kind of penetration tests.
- This step will give you full permission and understanding about the system you are going to Test on.
- This consists
	a. Scoping Questionnaires
	b. Pre-Engagement meeting
	c. Kick-off meeting

1. Scoping Questionnaire
- This Step will help us **to gather detailed information about the target environment**, including **what assets will be tested (Scope),** the **type of testing required** (eg. black-box, white-box), **any restrictions,** and **timelines.**
- This scoping questionnaire should clearly explain our services and may typically ask them to choose one or more from Our Cyber Security Service.
	- Example:
		- we can hack on 172.16.2.32/18 but not on another subnets.
		- We can hack their internet Facing website but not their intranet.
		- Your Customer May want a Black-Box Pen-test.

2. Pre-Engagement Meeting
- Here we will **discuss the details gathered from the scoping questionnaire** and clarify any uncertainties.
- **Participants:** key stakeholders from both the client and the security team, including project managers, technical leads, and legal representatives.
- **Outcome:** This meeting finalizes the scope, discuss potential risks, and addresses any legal or compliance concerns.
- There are some Agreements you do on this step
	- [Non-Disclosure Agreement (NDA)] refers to a secrecy contract between the client and the contractor regarding all written or verbal information concerning an order/project.
	- [Rule of Engagement (RoE):] rules that set, how the engagement will happen, what are the scopes, what are the contact address and more. Then client and the pen-tester will sign on it.

3. Kick-OFF meeting
- "Kick-Off" means [be started].
- Purpose of this Step is **To officially start the engagement** after all preparations are complete.
- Try to Discuss the **engagement schedule communication protocols, escalation processes,** and the final testing approach (retest, or no-retest).
- It finally Ensures everyone involved understands their roles and responsibilities and that the testing can proceed as planed.


---
# B. Recon (Information Gathering) /Footprint/
- Information Gathering is collecting data about [some network/host/system.]
- Footprinting => Footstep + printing (logging)
- Most of the people find Footprinting boring, but it is a very important part of Ethical Hacking. Almost 85% of The Actual Hacking.

Why do we need recon?
- Imagine, You are going to rob a bank...... What do you do?
	- know how much polices are there in the bank
	- know the doors (way in and out)
	- know if there is cctv
	- know which person is the CEO
	- know which time is good for robbery
- [To Get access on system, you have to know the system.]
- Will help us, to know which attack methodology and attacking tool we need to use.
- **Knowing the system** will lead you to know if the system is [vulnerable.]

---
### Types of information gathering
- Based on how we do the recon
	1. Active Footprinting/recon
	2. Passive Footprinting/recon

1. Active Footprinting
- This kind is when we try to gather information directly by contacting that person.
- Example:
	- When you go to the bank and ask for some informations.
	- Chatting with person on social media to know about them
- Doing Active Footprinting without permission is <span style="color:rgb(255, 0, 0)">ILLEGAL.</span>


2. Passive Footprinting
- This kind of recon is when you gather informations from another person, 3rd party or by checking public sources.
- Example:
	- To know the bank working time i can see the posted texts.
	- To know someone name by reading the username.


----
What type of information do you gather?
- We gather different kinds of infos:
	a. Host
		- Websites
		- Computers 
		- Smart Phone
	b. Network
		- Home Network
		- Companie Networks
	c. Person/Organization
	d. Application


----
### OSINT - Open Source Intelligence
- Gathering and Analyzing Different Informations Based on **Public resource** Passively is called [OSINT] (Open Source Intelligence).
- We can get lot of informations for system, user, host.... through passive activity.
- Sources include websites, social media, forums, public records, and search engines.

OSINT Framework
- a useful collection of tools in the landscpa eof intelligence gathering in our digital era.
- This guide cuts through the complexity, offering you a clear pathway to explore publicly available data across diverse sectors for security, strategic planning, or research purposes.
- link: https://osintframework.com/
![[Pasted image 20250707091227.png]]

---
Search Engines
- Search Engines are websites used to search any Document and Medias on the internet.
- They are very essential tools for performing OSINT.
- Example: google, Bing, Yahoo

## Shodan
- It is a specialized search engine designed to find and index internet-connected devices, often referred to as the "[search engine for the Internet of Things (IoT)]."
- Unlike traditional search engines like Google or Bing that index web pages, Shodan focuses on discovering devices *such as servers, routers, webcams, industrial control system, and other IoT devices.* if They are [Publicly Exposed.]
- Link: https://www.shodan.io/

## Maltego
- A powerful data mining and visualization tool used for link analysis.
- It helps in mapping relationships between entities like people, domains, IP addresses, and more.
- Graphical representation of relationships, making it easier to analyze complex networks.
- link: https://www.maltego.com/

---
## A. Websites
- The infomations we gather about a website are 
	- IP Addresses
	- Development frameworks
		- Technologies used and versions
	- Name
	- DNS Informations
	- VHOST, Subdomains on "[Web Hacking]" class

To get ip
- To get ip address of some website:
	- Active recon
		- `ping <website link>`
		- `nslookup <website link>`
		- `host <website link>`
		- DON'T ADD THE HTTPS.
	- Passive recon
		- www.nslookup.io

![[Pasted image 20250707101032.png]]
![[Pasted image 20250707101204.png]]

## To get development frameworks
- Use simple browser extension
	- wapplyzer
	- Built with
- Terminal tool
	- `sudo apt install whatweb`
	- `whatweb`

## To get the name
- you can see the title of thw website or texts inside the page also the url.

## Details about the domains
- For this you can use whois terminal +website tool
	- `sudo apt install whois`
	- `whois`
	- `dig <website>`


----
## B. Computers/Phone
- The informations we gather about a Computer/Host are
	- IP addresses
	- OS informations
	- HostName
	- MAC address
	- Oper services or ports
- Detail on "[Scanning and Enumeration]" class

---
## C. Networks
- The informations we gather about a Network are
	- IP addresses
	- Architecture
	- Class and Type of Network
	- Subnets/ VLANs
	- Hosts on that Network
	- Strength and security of that Network
- Detail on "[Network Penetration testing]" class
![[Pasted image 20250707103904.png]]

---
## D. Personal Informations
- The informations we gather about a person are
	- Full Name
	- Address
		- Physical Address
		- All Social Media Address
		- Phone address
	- What the person loves
	- Job
	- Friends
	- Status
	- skills
- There are many methods To gather these information, lets see about personal infos...

Getting Names by Phone Number
- For this purpose you can use https://www.truecaller.com/
- You can get the phone number from social media like telegram, some posted promotion, from websites.
	- You can get Email and Locations too.

Getting social media Addresses
- if you have Full name of a person, just use search engines (google, bing, yahoo)

Sherlock
- also you can use tool called sherlock from github
	- search sherlock github
- `python3 sherlock.py nathanhailu`

BlackBird
- Blackbird is a robust OSINT tool that facilitates rapid searches for user accounts by usernamme or emails across a wide array of platforms, enhancing digital investigations.
- `python blackbird.py --username hnathan26`
- uses whatsmyname website, which u can find
![[Pasted image 20250707145405.png]]

Getting Physical Addresses
- People share their living place on social medias info page.
- Else there are many methods:
	- Sending links and when people access the link u can get the IP then you can just geolocate the place.

IP geo-location
- If you got the private ip address of someone you can insert it to
- https://www.iplocation.net
- The method of getting the IP might be tricky but detail we will learn Social Engineering class.

Behavior and Obsession Recon
- People are being open on social medias, so we **Security testers** have access about the person's behaviors and likes.
- Example: Instagram is the best place to get info about some user.
- also by seeing telegram Profiles you can get more info about:
	- Their religion
	- Status
	- Mindset
	- ideology
	- family
- By checking their followings/friends you can get more common pictures and events, etc...
THIS IS OSINT!!!
- Detial on Exploiting the Person Using this Information will be on our "[Social Engineering]" Class.


===========================================================

BEHIND A SUCCESSFUL EXPLOITATION THERE IS A SUCCESSFUL RECON

==P2==
## E. Applications/Softwares
- The informations we gather about an application are:
	- **Static Analysis**: analyzing with codes (no execution)
		- which programming language used
			- Android app: java, kotlin, flutter, js
			- Desktop: js, C#, C++
		- Which framework used
		- File structure and [Assets] /resources
			- here they may de-compile an app it then they find the source code, alter API... then they recompile it 
			- [jadx-gui] - decompiles java tools
	- **Dynamic Analysis**: Analysis with Executing the program
		- Their logic and Function
		- Their Requests with servers
		- 


---
# Reverse image search
- Reverse image search is a technique of searching with images.
- We all search with text but we can search with images to This can give us more information
- Ex: think like user posted a picture with a background of some area, if the user didnt talk about the place we can just search the image and the search engines will give as some similar photos where they are taken in some place (not 100% accurate)
- We can use
	- https://tineye.com/
	- https://labnol.org/reverse/
	- https://images.google.com/ 

---
# Google Dorking (Google Hacking)
- it's not hacking into Google servers!
- Google hacking is using different [Google operators] to effectively.
- It also involves using Google to [identify vulnerabilities in websites.]
- Results are [highly customizable].
- [THIS IS THE MOST POWERFUL SKILL OF HACKER!]


# Basic Operators
- For inclusion of something common (+)
	- Terms you want to exclude (-)        > don't add space between the sign and the word
- Terms you want to execlude (-)
	- Antivirus -software
	- Georgia -america -state
- Search for an exact term (")
	- "How to eat food"
	- "Nathan Hailu" => what is the difference?
- (\*) any word (wild card)
	- if you include * with a query, it tells Google to try to treat the star as a placeholder for any unknown term(s) and then find the best matches.
	- Estonia parlament votes on the * bill
- (|) boolean "OR"
	- "Nathan Hailu" | "Natan Hailu"


# Advanced Operators
- These are Syntaxes used by Google
	- intitle
		- Google returns results with the word/phrase found within the title of the page
			- `intitle:index.of
			- `intitle:"Hackers Bible"
	- inurl
		- Finds a specific term within the URL
			- `inurl:view/index.shtml
	- site
		- To Get results from specific domain
			- `site:*.geezsecurity.com
	- Filetype | ext
		- Searches for a specific filetype
			- `"Hacking" filetype:pdf
			- `filetype:txt
	- intext
		- Google return links that contain Texts from that link
			- `intext:"Hackers in Ethiopia"

# Mixing Operators
![[Pasted image 20250707165206.png]]

# Hackers Power
- Hackers do anything with these operators
- When they get errors or any problems they use the operators and other.
- As security tester, we can also use them to optimize our search also to create a script to do that.



# GHD - Google hacking Database
- link: https://www.exploit-db.com/google-hacking-database


Warning
- if you do a lot of dorkings with same ip address, Google will block you for some hours, and shows you this. This is Because Google Want to Get rid of Bots/Scripts


# GooFUZZ
- GooFuxx is a tool to perform fuzzing with an OSINT approach, managing to enumerate directories, files, subdomains or parameters without leaving evidence on the target's server and by means of advanced Google searches (Google Dorking).
- link: https://github.com/m3n0sd0n4ld/GooFuzz



# Shodan Dorking
- Shodan Dorking, is Advanced Method of using Shodan.io for advanced Search with Different Operational words and symbols.
- To Perform Shodan Dorking, You need to Create Shodan Account.
- Filters/Operator
	- Normal Search
		- `http or webcam`
	- title: "YOUR TITLE"
		- `title:"Geez"`
	- Websites that have the word "Apache" in their HTML
		- `http.html:Apache`
	- Services with a hostname containing either "geeztech.com" OR "geezsecurity.com"
		- `hostname:geeztech.com,geezsecurity.com`
	- Specific Port
		- `Port:1000`
	- SSH on non-standard ports
		- `ssh -port:22`
	- Specific Country & City
		- `country:"ET"`
		- `city:"Addis Ababa"`
	- For Specific Product Search
		- `product:Apache`
	- For Specific OS Search
		- `os:Windows`
- You can combine these operations together.

- university is org
- tomcat is product or apache(less result)


# Github Dorking
- GitHub is where over 56 million developers shape the future of software, together. Contribute the open-source community, manage their Git repositoreis, and doing lots of stuff and sometimes the repository contains much sensitive information like [api, db credentials, ftb credentials, and much more]
- Recon
	- At first, you should just simply search your target like xyz.com to understand their repo architecture
		- how many repos, commits, and what kind of languages are found stuff like that.
	- Dork: Search for different Sensitive Keywords
		- Ex: api_key, key, password, secret, DB_PASSWORD, admin

