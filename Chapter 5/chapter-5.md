# Securing Hosts and Data

## Implementing Secure Systems

Secure systems design concepts help ensure that computing systems are deployed and maintained in a secure state.

*Hardening* is the practice of making an operating system (OS) or
application more secure from its default installation. It helps eliminate vulnerabilities from default configurations, misconfigurations, and weak configurations. A core principle helping with this is principle of least privilege. 

## Operating Systems

One of the most important parts of an computer. Three different varieties:
1. Windows OS. Closed source.
2. MacOS. Closed source and based on Unix.
3. Linux/Unix OSes. Open source OS created by the community. 

### Secure OS Configurations

A trusted operating system meets a set of predetermined requirements with a heavy emphasis on authentication and authorization. A trusted OS aims to ensuer that only authorized users are able to access the data based on their permissions. 

**Using Master Images** uses a common starting image to install OS on all systems. The process for creatinig Master Images goes as follows:  
1. Admins start with a blank image and configure the OS, install required applications and perform security testing on the image. 
2. A snapshot is created from the OS once everything is tested and the image is stored on a storage device. 
3. When a system is to be deployed, the snapshot can be used for many times. 

Imaging has two main benefits: 
* *Secure Starting Point* so that requied softwares are configurations are not required for each deployment. 
* *Reduced Maintainance Costs and increased relaibility* as the basic environment is setup and any extra troubleshooting need not include the steps for the same. This helps greatly in reducing TCO for systems. 

**Resiliency and Automation Strategies** include strategies for automation like scripting and templating and help deploy systems securely. For example, Microsoft offers GPO(Group Policy Object) which can be deployed within the domain. 

**Secure Baseline and Integrity Measurements** help knowing the starting point for the system. Having a baseline helps in:  
1. Knowing Initial Configuration. 
2. Check for deviation from baseline using devices like NAC and automation in order to reduce risk. 
3. Remediation of devices which have deviated from the baseline configuration. 
 
**Patch Management** ensures that systems are patched to the latest version of the software. There are tools that help in the process of patching so that the system administrators do not have to login to each system to deploy the patch.

**Change Management Policy** Unrestrained changes to a network can cause major problems in the network.
defines the process for any type of system modifications or upgrades, including changes to applications. It provides two key goals:
* To ensure changes to IT systems do not result in unintended outages
* To provide an accounting structure or method to document all changes

Policies prevent admins from making changes without proper review and approval.

**Unauthorized Softwares** cause many different problems with malwares being installed on the system being the biggest issue. 

**Compliance Violations** like unauthorized use of licensed software can cause issues as well. 

**Application Whitelisting and Blacklisting** helps in protecting the systems from unauthorized softwares. A whitelist a used to list all applications that are allowed to run on the system. A blacklist blocks all known malicious/vulnerable applications. 


### Secure Staging and Deployment

**Sandboxing with VMs** is the use of an isolated area on a system and it is often used for testing. Sandboxed environments are used for testing, setting up a baseline system. 

**Sandboxing with Chroot** helps in setting a sandboxed environment for non-root users. An application in the sandboxed environment is not able to access any other folder/directory/files in the system other than the directory provided to it. 

**Secure Staging Environment** includes multiple environments for different types of deployments. 
*Development* is used by software developers in order to test their under-development softwares. 
*Test* is used by application testers who try to dicover bugs and errors in the software. 
*Staging* simulates production environment and is used for integration testing and replicating issues in production. 
*Production* is the final deployment, where the software is used by clients and users. 

**Peripherals** are an important part of secure system design. Use of wireless devices can let attackers perform MITM attacks, Monitors can show sensitive/private information, and external storage devices can be used to capture confidential data which can be misused. 

### Hardware and Firmware Security

**EMI(ElectroMagnetic Interference)** from devices such as motors, power lines can affect the signals trasmitted. Proper shielding of wires can help prevent this. 

**EMP(ElectroMagnetic Pulse)** comes in short bursts from Electrostatic discharge, lightning and sometimes weapons. 

**FDE and SED** are disks which are either can be encrypted fully using softwares, or the disks themselves contain hardware and software which can help with the same. 

**UEFI(Unified Extensible Firmware Interface) and BIOS(Basic Input/Output System)** are used to provide basic checks and instructions for the OS to be loaded and the system to start. UEFI has a few enhancments over BIOS and helps in loading OS independently of the CPU. 

**Trusted Platform Module** is a hardware chip the system which stores cryptographic keys for encryption. TPM provides full disk encryption and keeps drives locked till system complets verification of the user. A TPM supports secure boot and attestation processes. Each TPM has an unique RSA key birned into it which is used for asymmetrix encryption. The private key is mateched with the public key to provide a hardware level of trust. For example, Bitlocker uses a TPM to detect tampering of any critical OS files or processes as a part of platform verification process. 

**Hardware Security Module** is used to store, manage and generate cryptographic keys. HSMs are removable and are external devices as compared to TPMs which are built into the systems. These can used used in systems which have no TPM preinstalled.  

**Additional Vulnerabilities** like EOL devices, lack of support from vendor also cause unexpected vulnerabilities in the network and the security teams and network admins need to deal with these as well. 


## Cloud Concepts
Cloud computing refers to accessing computing resources via a different location than your local computer. Cloud allows scaling and reducing costs due to the economies of scale at which the providers operate. 

Types of Cloud services:
1. *SaaS(Software as a Service)* are softwares provided to users. 
2. *Paas(Platform as a Service)* are pre-configured compute platform provided to the user. 
3. *IaaS(Infrastructure as a Service)* is a service generally provided to businesses who want to use the cloud to get all benefits of the cloud.

![IaaS vs PaaS vs SaaS vs On-prem](IaaS%20vs%20PaaS%20vs%20SaaS.png)



### Security Responsibilities with Cloud Models

Cloud environments work on a shared responsibility model where the service provider is responsible for security of the underlying infrastructure and the services offered by them, and the user is responsible for security of the applications deployed. 

**Cloud Deployment Models** can be divided in 4 categories:
1. Public which can be used by anyone. 
2. Private which are accessible to only select organisations. For example, gov clouds in US are reserved for Government of USA applications. 
3. Communities with shared concerns (such as goals, security requirements, or compliance considerations) can share cloud resources within a community cloud.
4. A hbrid cloud is a combinatin of more than one of the above three categories. 

**Deployment Models** used by corporates include:
1. Corporate-Owned. 
2. COPE(Corporate Owned and Personally Enabled). are owned by organisation but can be used as personal devices. 
3. BYOD(Bring your Own Device) allows employees to bring their own devices, but this might make the org vulnerable if proper precautions are not taken.  
4. CYOD(Choose your own Device) is a modification to BYOD, but the list of permitted devices is given by the organisation. 
5. VDI (Virtual Desktop Infrastructure) has virtual devices hosted on a server. Users can connect to the VDI using VPNs from any device. 

**Mobile Device Management** are technologies which can help in management of mobile devices. It may cover points like 
* Application Management
* Full device encryption
* Storage segmentation
* Content Management 
* Containerization
* Password and PINs
* Biometrics
* Screen Locks
* Remote Wipes
* Geolocation
* Geofencing
* GPS tagging
* Context-aware authentication
* Push notification services

**Mobile Device Enforcement and Monitoring** help manage devices based on who owns the devices. These can help keep softwares upto date and block harmful and unnecessary softwares. 

**Unauthorized Software** are a source of problem when managing devices. Softwares downloaded from unknown places might contain malware and can cause harm to the entire organisation. 

*Jailbreaking* is the process of removing software based restrictions from an iOS device. Similarly, *Rooting* is the process of getting root level privileges for andriod devices. 

**Hardware Control** is used to disable cameras and microphones for devices as they can cause possible security threats to organisations. 

**Unauthorized Connections** Management within an organization might want to limit a mobile device’s connection. 

**Embedded Systems** are devices that have a dedicated function and use a computer systems to perform the function. All electronic devices have some or the other type of embedded system in their 


## Protecting Data

Data is one of the most valuable resources any organization manages, second only to its people. Losing control of data directly affects the reputation, and often the bottom line, of an organization. The importance of taking steps to protect valuable data cannot be overstated.

### Protecting Confidentiality with Encryption

Data at rest is encrypted so that even if the data gets into the hand of the attackers, it cannot be read. 

Securing *Databases* and *File Systems* are the required parts of securing data. 

**Permission Issues and Access Violations** also lead to security issues. Generally, principle of least privilege is followed in order to set proper access management. 


### Linux Permission Structure:

Types of file owners:
1. Owner -> user who owns file and directory.
2. Group -> members of group have a list of similar permissions on a file. 
3. Others -> All users except owners and groups fall under other. 

Types of permission:
1. Read(r)
2. Write(w)
3. Execute(x)


### Windows Permission Structure:
1. Read -> view the contents of a file or folder.
2. Read & Execute-> Read permission + run or execute programs.
3. Write. create new files and folders + Read permission
4. Modify. read, execute, write, and delete files and folders.


## Data Loss Prevention

DLP techniques help in preventing data loss. A DLP solution is more selective and it can prevent a user from copying or printing files with specific content. 