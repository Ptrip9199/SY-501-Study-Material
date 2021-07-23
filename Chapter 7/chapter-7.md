# Protecting Against Advanced Attacks

## Common Attacks Vectors 

### DoS and DDoS
A denial-of-service (DoS) attack is an attack from one attacker against one target. A distributed denial-of-service (DDoS) attack is an attack from two or more computers against a single target. The goal of both is to perform a service attack and prevent legitimate users from accessing services on the target computer.

### Privilege Escalation
When a user with normal privileges is bale to perform functions which only an admin should be able to perform its known as privilege escalation. This is a very critical attack vector as it may lead to normal users performing actions only admin should be able to perform. 

### Spoofing
Spoofing occurs when one person or entity impersonates or masquerades as someone or something else for example, MAC Spoofing and IP Spoofing.

### SYN Flood Attacks
SYN attacks are easy for attackers to launch, difficult to stop, and can cause significant problems. The SYN flood attack disrupts the TCP handshake process and can prevent legitimate clients from connecting. They are similar to DoS attacks whose main focus is to disrupt services. 

### Man-in-the-Middle Attacks
A man-in-the-middle(MITM) attack is a form of active interception or active eavesdropping. It uses a separate computer that accepts traffic from each party in a conversation and forwards the traffic between the two. 

### ARP Poisoning Attacks
ARP poisoning is an attack that misleads computers or switches about the actual MAC address of a system. ARP poisoning can lead to various attack vectors like:
1. ARP MITM: An attacker intercepts ARP packets by ARP spoofing and then forwards them to actual source. 
2. ARP DoS: An attacker sends bogus packets to the gateway leading to a disturbance in service. 

### DNS Attacks
DNS attacks aim to disrupt the DNS service. They can be divided in three categories:
1. DNS Poisoning Attacks: An attacker attempts to modify or corrupt DNS results. 
2. Pharming: Corrupts DNS Server/DNS Client to redirect users to malicous websites. 
3. DDos DNS Attacks.


### Amplification Attacks
An amplification attack is a type of DDoS attack. It typically uses a method that significantly increases the amount of traffic sent to, or requested from, a victim. 

### Password Attacks
The main idea behind password attacks is to gain pasword in order to access systems.
1. Brute-force: Try all password combinations. 
2. Dictionary Attacks: Narrowed down version of brute-force where a list of pre-defined passwords are used. 
3. Password Hashes: This attacks try to re-generate the password from the hash. 
4. Pass the Hash: If a network sends hashed passwords without encryption, an attacker can pass the captured hash and the network can sign you in. 
5. Birthday Attacks: An attacker is able to create a password that produces the same hash as the vistim’s actual password by hash collision.
6. Rainbow Table Attacks: Is similar to brute force attack, but instead of having to calculate the hash everytime a rainbow table has a database for all the hashes in a dictionary which can be used to crack the password. 
7. Replay Attacks: An attacker replays data that was already part of a communication session. In a replay attack, a third party attempts to impersonate a client that is involved in the original session. 
8. Known Plaintext Attacks: If a part of the message is known, the attacker can try to decrypt that part of the message and guess what algorithm and keys are being used to encrypt the data.

### Hijacking and Related Attacks
Typo squatting occurs when someone buys a domain name that is close to a legitimate domain name.  
Clickjacking tricks users into clicking something other than what they think they’re clicking.  
Session hijacking takes advantage of session IDs stored in cookies.  

### Domain Hijacking
In a domain hijacking attack, an attacker changes the registration of a domain name without permission from the owner.

### Man-in-the-Browser
A man-in-the-browser is a type of proxy Trojan horse that infects vulnerable web browsers. Successful man-in-the-browser attacks can capture browser session data.

### Driver Manipulation
Outdated drives need to be updated for the system to recognise devices. This can be done by two ways, either rewriting the driver, or writing a driver shim which can help run the devices. If some attcker can write a driver shim and include some malicious code in the driver, they can cause harm.

### Zero-Day Attacks
A zero-day vulnerability is a weakness or bug that is unknown to trusted sources, such as operating system and antivirus vendors. 

### Memory Buffer Vulnerabilities
Many application attacks take advantage of vulnerabilities in a system’s memory or buffers.
1. Memory Leak: It is a bug in a computer application that causes the application to consume more and more memory the longer it runs.
2. Integer Overflow: An integer overflow attack attempts to use or create a numeric value that is too big for an application to handle.
3. Buffer Overflows: A buffer overflow occurs when an application receives more input, or different input, than it expects. The result is an error that exposes system memory that would otherwise be protected and inaccessible.
4. Pointer Dereference: Dereferencing is the process of using the pointer to access the data array. A failed dereference operation can cause an application to crash. In some programming languages, it can subtly corrupt memory.
5. DLL Injection: A DLL(Dynamic Link Library) is a compiled set of code that an application can use without recreating the code. DLL injection is an attack that injects a DLL into a system’s memory and causes it to run.


## Secure Coding Concepts

### Proper Input Validation
One of the most important security steps that developers should take is to include input validation. Input validation is the practice of checking data for validity before using it. Some validations include, verifying proper characters, implementing boundary or range checking, block code, prevent use of special characteres. 

### Client-Side and Server-Side Input Validation
Client-side input validation is quicker, but is vulnerable to attacks. Server-side input validation takes longer, but is secure because it ensures the application doesn’t receive invalid data. Mostly applicatons use both to ensure better user experience for normal users. 

### Avoiding Race Conditions

When two or more modules of an application, or two or more applications, attempt to access a resource at the same time, it can cause a conflict known as a race condition.

### Proper Error Handling

Error-handling and exception-handling routines ensure that an application can handle an error gracefully. They catch errors and provide user-friendly feedback to the user. When an application doesn’t catch an error, it often provides debugging information that attackers can use against the application.

### Cryptographic Techniques

Sensitive data is often encrypted to prevent the unauthorized
disclosure of data. If an application is accessing any sensitive data, developers need to ensure that this access doesn’t result in inadvertent data exposure.

### Code Reuse and SDKs

Code reuse might lead to dead code if all the logic copied is not being used somewhere. 

### Code Obfuscation

It helps in making the code unreadble by other people in order to discourage others from copyinng code. 

### Code Quality and Testing

1. Static Code analysers: examines the code without executing it.
2. Dynamic analysers: checks the code as it is running.
3. Stress Testing: attempt to simulate a live environment and determine how effective or efficient an application operates with a load.
4. Sandboxing: an isolated area used for testing programs.
5. Model Verification: helps identify and remove bugs.

### Development Life-Cycle Models

Mainly Waterfall and Agile models are used.Waterfall is a bit old school and follows one step at a time. The agile model uses a set of principles shared by cross-functional teams.

### Secure DevOps

Secure DevOps is a software development process that includes extensive communication between software developers and operations personnel. Security Automation, CI, Baselining, Immutable systems and IaC.

### Version Control and Change Management

Change management helps ensure that developers do not make unauthorized changes. The change management process allows several people to examine the change to ensure it won’t cause unintended consequences.

Version control tracks the versions of software as it is updated, including who made the update and when.

### Provisioning and Deprovisioning

Provisioning and deprovisioning typically refers to user accounts. For example, when an employee starts working at an organization, administrators create the account and give the account appropriate privileges.


## Identifying Application Attacks

### Web Servers

Web servers most commonly host web sites accessible on the Internet, but they can also serve pages within an internal network. Organizations place web servers within a demilitarized zone (DMZ) to provide a layer of protection. Apache and IIS are the most widely used web servers. 

### Databases. 

Databases host the data related to customers. Most databases are also used to store confidential information as well so they need utmost protection. Databases can be queried using SQL.  

**SQL Injection** attacks happen when a web page can query the underlying database directly leading to uncontrolled access to the database.  
To prevent SQL  injections, proper input validation and stored procedures can be used. 


### Injection Attacks

Apart from SQL and DLL injection there are other multiple types of injection attacks like, code injection etc. 

### Cross-site scripting

Cross-site scripting (XSS) is another web application vulnerability that can be prevented with input validation techniques. Attackers embed malicious HTML or JavaScript code into a web site’s code. The code executes when the user visits the site.

### Cross-Site Request Forgery

Cross-site request forgery (XSRF or CSRF) is an attack where an attacker tricks a user into performing an action on a web site. The attacker creates a specially crafted HTML link and the user performs the action without realizing it.

### Understanding Frameworks and Guides

Framework is a structure used to provide a foundation. Cybersecurity frameworks typically use a structure of basic concepts and they provide guidance to professionals on how to implement security in various systems.

* *Regulatory* : based on relevant laws and regulations.
* *Non-regulatory* : not required by law, but based on common standards and best practices. 
* *National vs International*.
* *Industry specific* : apply to certain industries, Eg, PCI to credit card industry.   

