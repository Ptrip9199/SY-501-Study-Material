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

