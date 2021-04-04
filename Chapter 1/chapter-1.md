# Chapter 1:


## CIA Triad:  
1. **Confidentiality** : Prevents unauthorized disclosure of data.
   1.  Encryption -> scrambling data to make it unreadable.
   2.  Access Control List -> Authorization. Authentication and Indentification are examples of ACLs.
   3.  Steganography and Obfuscation -> data is hidden within data
2. **Integrity** : Provides assurance that the data hasn't changed. 
   1. Hashing -> an identification string produced from a message which cannot be obtained by any message other than the one given.
   2. Digital Signatures, Certificates, and Non-Repudiation -> covers integrity using message hash as well as source of identity as only I can use my digital signature to sign a doc and no one else. 
3. **Availability** : Ensure that data and services to access the data are available all the time. 
   1. Redundancy and Fault Tolerance -> add duplication and remove each SPOF(single point of failure).
   2. Patching -> ensuring that the software of the system is always the lastet to ensure that there are no software related issues in the systems.  


**Risk** : possibility/likelihood of a threat being exploited leading to losses to the company. 

**Threat** : a circumstance or event that has the potential to compromise confidentiality, integrity, or availability.

**Vulnerability** : a weakness in either the system, software or configuration. 

**Security Incident** : When a *Threat* exploits a *Vulnerability*, it leads to a security incident.

## Control Types:  
1. **Technical Controls**
   1. Encryption
   2. Antivirus
   3. Intrusion Detection and Prevention Systems(IDS/IPS)
   4. Firewalls
   5. Least Privilege : this implies only the required permissions should be given to a user. 
2. **Administrative Controls**
   1.  Risk Assessments : qualify and quantify risks 
   2.  Vulnerability Assessments: discover all vulnerabilities 
   3.  Penetration Tests : trying to exploit vulnerabilities.
3. **Physical Controls** eg. Mantraps, security cameras etc. 


## Control Goals:  
1. Preventative Controls : prevent security incidents
2. Detective Controls : identify security incidents
3. Corrective Controls : reverse impact of incidents
4. Deterrent Controls : attempt to discourage threats
5. Compoensatinf Controls : alternative controls used instead of primary controls.   



## Virtualization  

Virtualization helps in hosting multiple *Virtual* instances on a single physical instance. 
Parts of virtualization are:
1. **Hypervisor** : Software that createsm runs and mangers VMs. There are two types:
   1. *Type-I* -> ones that do not require an host OS to run on. eg. VMware ESXi.
   2. *Type-II* -> ones that run within an host OS. eg. Microsoft Hyper-V.  
2. **Host** : The physical system that hosts the VMs. 
3. **Guest** : The Virtual machine running on the host. 
4. **Host elasticity and scalability** : The ability to rezise the computer and memory used by a server.   
5. **Snapshots** : Point in time copies of the machine which can be used later to restore the machine in case there are any issues with it, or you want to create a clone of the machine. 

Another famous virtualization platform is **containerizartion** . Here, instead of having an entire guest OS, the kernel of the base OS is used resulting in better utilization of compute and memory resources and lighter and faster launch cycles. Additionally, you can spawn multiple containers for each service which leads to better separation of concerns. However, the above listed advantages come with a catch, since containers use the underlying OS kernel, the container cannot use any other OS.  

VMs are just a bunch of files consisting of storage and configurations. So in case some server is overloaded you can easily move the VM to some other server. Generally, data centers use technologie like NFS which is a common file storage used by multiple servers, so in case one of the server is overloaded, the VM can be moved/launced on another server. 


### Risks associated with Virtualization:
1. **VM Escape** : allows an attacker to access the host OS from the VM.
2. **VM Sprawl** : occurs when VMs are not managed properly, leading to possibly unpatched systems and extra load on the systems. 
3. **Loss of Confidentiality** : Since VMs are just files to the physical machine, they can be accessed easily from the physical machine itself and used elsewhere. Hence, it is very important to encrypt you VM as well and the contents on it whenever stoing important information. 


## List of basic Linux Commands
1. **ping** -> check if a remote system responds to an ICMP packet. 
2. **ipconfig** -> check current IP of the system.
3. **netstat** -> view stats for TCP/IP protocols on a system.
4. **tracert** -> lists a list of all routers between the source and destination. 
5. **arp** -> resolves mac address of a given IP. 
