# Cryptography 
Created on: 2025-08-02 17:30
Topics:
- What is Cryptography?
- Types of Cryptography
- Terms of Cryptography
- Xvaqf bs Pelcgbtencul
- Jbeqyvfg
- Gbbyf 
- Python for Cryptography
- Obfuscation 


=================================================================
==P1==
# What is Cryptography
- Cryptography is the science of secret, or hidden writing
- Crypto => Hidden/Secret | Graphy => Writing
- Used to secure your data/text
- It has two main Components:
	a. Encryption
		i. Practice of hiding messages so that they can not be read by anyone other than the intended recipient
	b. Integrity
		i. Ensuring that users of data/resources are not being altered


----

















=============================================================

==P2==

# 3 Terms of Cryptography
**1. Encoding/decoding
- This is a method of creating Ciphertext with out using any key
- This can be done by doing math on the given input/substitution
	- Examples: base64, base32, rot…
- Is encoding subset of encrypting??????????



**2. Encrypting/Decrypting
- This is method of creatingCipher text with keys.
- To decrypt this kind u need to have the private key
- Example: DES, ARS, RSA


**3. Hash Function
- Hashing algorithm is one-way cryptographic function that accepts a message of any length as input and returns as output a fixed-length digest value
- This means that a calculated hash cannot be reversed using just the output given. This ties back to a fundamental mathematical problem known as the [P vsNP relationship,]
- Hash is A random Hexadecimal combination
- To reverse the hash, you just search for soe match, you don’t decrypt/decode it.
- **Salt**: is a random string used for data modification for password protection, This can be adding some text as prefix/suffix
	- Example of Hashes: MD5, SHA256, bcrypt…

- `echo kidus | md5sum`



![[Pasted image 20250802183218.png]]





((((((( most of the time these types of hashing is done through async process))))


# MD5 (Message-digest algorithm)

- The MD5 message-digest algorithm is a cryptographic hash function designed to convert a message to a 128-bit hash value
- Each MD5 hash looks like 32 numbers and letters, but digit is hexa decimal and represents four bits.
- The MD5 hash function was originally designed for use as a secure cryptographic hash algorithm for authenticating digital signatures.
	- But MD5 has been deprecated for uses other than as a non-cryptographic checksum to verify data integrity and detect unintentional data corruption.
    

  
  
  ![[Pasted image 20250802183416.png]]

---
# Purpose of hashing

- Hashes are used for Confidentality
- Hashes are used to integrity



---
## Exercise 2
1. Create SSH key and observe the public and private keys
2. Download this img
	https://geezsecurity.com/wp-content/uploads/2024/09/transparent.png
3. what is the md5sum
4. what is the  sha256

answer
1. ssh-keygen
2. curl https://geezsecurity.com/wp-content/uploads/2024/09/transparent.png | md5sum


---
# Kinds of encoding/encryption

- Base2 001100010 01110010
- Base8 142 
- Base16
- Base32
- Base58
- Base62
- Base64 Yn
- Base85
- Base91
- URL encode: hello%20there%20
- Md5: 
- Sha1:
- Rot: Uryyb,Frphevgl Grfgref => look for some random word that looks rotated


---
## Tools

- There are lots of encoding/encryption Algorithms
- To identify these we need to understand every Algorithm Properties,But that is not easy for humans so we will use some automation tools/sites.
- Tools:
	- Hashid
		- `hashid <hash>`
	- Cyber chef (web)
	- Tunnelsup (web)

### Tunnels up

- This will help you analyze and determine what that hash is based on the bit length and the base
- tunnelsup.com/hash-analyzer/

  
### CyberChef

- Go to google and type cyberchef 
- Click on the 1st link.
- Link:
- https://gchq.github.io/CyberChef/

- search for magic
- Drag and drop it, to the recipe
- Add your text to the input
- Look at the output it is the guess of what the hash can be

`echo kidus | md5sum`

- if you don't know the encoding method used in cyberchef - use [Magic] in operations 
- 
```
`echo kidus | base64` - Encode -> output `a21kdXMK`
`echo a21kdXMK | base64 -d` => output kidus
```


---
# Decoding/ Decrypting

- There are so, many to reverse some hashes/ciphers.
	- Hashes
		- Crakstation.net(non-salted)
		- Own cracking (google the name)
	- Encodings
		- CyberChef


`echo kidus | md5sum` 
- how to find the name(kidus) using the hash output from above?
- use bruteforce using wordlist
	vim possible.txt
	cat possible.txt


- You can search the hash type to get the decoder/decrypter
- Searching the hash on search engines is Good way to get the match value


## Cyber chef
- by searching any encryption you can decode/decrypt it
	- we use [from] to decrypt
	- we use [to] to encrypt


## DES encrypt

- link: https://anycript.com/crypto/des


----
# Identifying Unknown Hashes
- Sometimes when you do penetration tests you will get some Hash. These hashes are not normal hashes, they are generated by some Platform/Software. So to Crack this hash.
	- Identify the Software which the has Generated with
		- Eg. The Hash can be generated by some Software called Openfire
	- Then Try to Search Some Cracking Scripts made for this hash



![[Pasted image 20250806095850.png]]


----
# Wordlist
- Wordlists are normal text file that contains Different Words that can be used to match hashes, or for checking some parameters repeatedly using some loops.


---
# Custom Wordlists
- We can create our own Wordlists. We can create text file and add our highly usable words or we can use tools like
	- Cewl
	- Cupp
	- crunch


## Cewl Tool
- Cewl is a Ruby program that crawls a URL to a defined depth, optionally following external links, and produces a list of keywords that password crackers


## Crunch
- Crunch is a popular open-source tool used for creating custom wordlists or dictionaries for password cracking, network security testing, or other security-related purposes.
- Syntax: `crunch <min_length> <max_length> [options}`
- Options:
- -t: character set `',natan^%%%'`
	- , for all uppercase letters
	- @ for all lowercase letters
	- % for all numeric characters
	- ^ for all special characters
- -p: permutation
- Eg: `crunch 4 6 abcd -o test`

## With Characterset
- `crunch 9 9 -t rexder^%% -o test`
	- The Character set and the length you put have to be equal
	- The maximum and minimum length should be the same size as the pattern you specified.


## Jogn the Ripper
- Jogn the Ripper is one of the most well known, well-loved and versatile hash cracking tools out there.
- It combines a fast cracking speed, with an extraordinary range of compatible hash types.
- Syntax: `john [options] [path to file]`
- Options:
	- `--wordlist=<path>`: to specify wordlist
		- -wordlist=/opt/rockyou.txt
	- `--format=<hashType>`: to specify the hastype if you know, else it will guess
		- -format=raw-md5
- `john hash.txt --wordlist=rockyou.txt --format=md5crypt`















=============================================================

==P3==

# Python for cryptography
- We can use programming to do tools that can do our own encryption and encoding hash type.
- There are so many methods, even you can do the encoding/decoding for the base64....
- You just need to understand the maths.
- Now i will show u simple XOR'ing example
	- What is XOR?