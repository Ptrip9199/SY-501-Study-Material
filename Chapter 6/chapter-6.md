# Comparing Threats, Vulnerabilities, and Common Attacks

## Threat Actors
* *Script Kiddie* is an attacker who uses existing scripts to attack the systems. 
* *Hacktivist* launches attacks as part of an activist movement or to further a cause. 
* *Insider Threat* is someone inside the company who has legitimate access to the information and misuses the access.
* *Organized crime* is an enterprise that employs a group of individuals working together in criminal activities. These are generally very highly trained individuals/businesses who attack organisations for a living. These can also be backed by governments organisations or competitors and can launch **APTs(Advanced Persistent Threats)** into the network. 

## Types of Threats:

1. *Virus* : A virus is malicious code that attaches itself to a host application. The host application must be executed to run, and the malicious code executes when the host application is executed. The virus tries to replicate by finding other host applications to infect with the malicious code. At some point, the virus activates and delivers its payload.
2. *Worms* : A worm is self-replicating malware that travels throughout a network without the assistance of a host application or user interaction.
3. *Logic Bomb* : A logic bomb is a string of code embedded into an application or script that will execute in response to an event.
4. *Backdoor* : A backdoor provides another way of accessing a system, similar to how a backdoor in a house provides another method of entry. 
5. *Trojans* : A Trojan, also called a Trojan horse, looks like something beneficial, but it’s actually something malicious.
6. *RAT(Remote Access Tool)* : A RAT is a type of malware that allows attackers to take control of systems from remote locations.
7. *Ransomware* : A type of trojan which encrypts all the data and takes control of the system until the user pays up a ransom to get back the data. 
8. *Keylogger* : A keylogger attempts to capture a user’s keystrokes. 
9. *Spyware* : A Spyware is software installed on users’ systems without their awareness or consent. Its purpose is often to monitor the user’s computer and the user’s activity.
10. *Adware* : When first introduced adware was used to learn users habits and help in targeted advertising. It also refers to software which are free but include advertisements. 
11. *Rootkits* : A rootkit is a group of programs that hides the fact that the system has been infected or compromised by malicious code.


## Recognizing Common Attacks

**Social Engineering** : The practice of using social tactics to gain information. It’s often low-tech and encourages individuals to do something they wouldn’t normally do, or cause them to reveal some piece of information, such as user credentials.

**Shoulder Surfing** : Looking over the shoulder of someone to gain information. The goal is to gain unauthorized information by casual observation, and it’s likely to occur within an office environment. This can be to learn credentials, such as a username and password, or a PIN used for a smart card or debit card.

**Tricking Users with Hoaxes** : Circulating hoax messages to which warn user of non-existent threats which can cause user to delete important files. 

**Tailgating and Mantraps** : Tailgating is the practice of one person following closely behind another without showing credentials. Mantrap help in avoiding such activities by limiting the number of people who can enter at a time to one.

**Dumpster Diving** : The practice of searching through trash or recycling containers to gain information from discarded documents. Many organizations either shred or burn paper instead of throwing it away.

**Watering Hole Attacks** : It attempts to discover which web sites a group of people are likely to visit and then infects those web sites with malware that can infect the visitors.

**Attacks via Email and Phone**: There are various categories of attack via phone or email.
* *Spam* is unwanted or unsolicited email.  
* *Phishing* is sending email to users with the purpose of tricking them into revealing personal information or clicking on a link. Phishing can serve many purposes, like install malware, validate email or scam the user.
* *Spear Phishing* is a targeted form of phishing. Instead of sending the email out to everyone indiscriminately, a spear phishing attack attempts to target specific groups of users, or even a single user.
* *Whaling* is a form of spear phishing that attempts to target high-level executives.
* *Vishing* attacks use the phone system to trick users into giving up personal and financial information. 


## Blocking Malware and Other Attacks

**Protecting Systems from Malware** : Spam filters on email gateways, anti-malware software on mail gateways, anti-malware softwares on all workstations are some ways in which systems can be protected from malware.  
**Antivirus and Anti-Malware Software** : Antivirus and Anti-malware softwares provide protection against known viruses and malwares. They work on either signature-based or heuristic-based detection. 
* *Signature-Based Detection* : Viruses and other malware have known patterns. Signature files define the patterns, and the antivirus software scans files for matching patterns.
* *Heuristic-Based Detection* : Heuristic based detection attempts to detect viruses that were previously unknown and do not have signatures. Heuristic-based analysis runs questionable code in a sandbox or virtualized environment specifically designed to protect the live environment, while it observes the code’s behavior.
* *Checking File Integrity* : A file integrity checker calculates hashes on system files as a baseline. It then periodically recalculates the hashes on these files and compares them with the hashes in the baseline. A different hash points towards file being modified without permission.

**Data Execution Prevention** : DEP is a security feature that prevents code from executing in memory regions marked as nonexecutable. It helps prevent an application or service from executing code from a nonexecutable memory region. The primary purpose of DEP is to protect a system from malware.

**Advanced Malware Tools** : AMTs Are advanced tools which can help in prevention, detection and fighting malwares attacks. For example, AMP(Advanced Malware Protection by Cisco).

**Spam Filters** : Spam filters try to filter out the spam emails and only send required emails to the mailserver. Generally, the settings of spam filters are tuned down so that valid emails are not detected as spam.

**Educating Users** : Untrained users provide a significant risk to any organization and are often one of the largest vulnerabilities. The single best protection against many attacks, such as social engineering and phishing attacks, is to train and raise the security awareness of users.

**Why Social Engineering Works**:
1. Authority
2. Intimidation
3. Consensus
4. Scarcity
5. Urgency
6. Familiarity
7. Trust

