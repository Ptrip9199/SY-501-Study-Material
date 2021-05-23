# Using Risk Management Tools

*Risk* is the likelihood that a threat will exploit a vulnerability. A vulnerability is a weakness, and a threat is a potential danger.

A *threat* is a potential danger. Within the context of risk management, a threat is any circumstance or event that can compromise the confidentiality, integrity, or availability of data or a system. *Threat assessment* helps an organization identify and categorize threats.

A *vulnerability* is a flaw or weakness in software or hardware, or a weakness in a process that a threat could exploit, resulting in a security breach.

*Risk management* is the practice of identifying, monitoring, and limiting risks to a manageable level. It doesn’t eliminate risks, but instead identifies methods to limit or mitigate them. The amount of risk that remains after managing risk is residual risk. The techniques used to mitigate risks are:
1. **Avoid** : Risk can be avoided by not using or providing services which can be risky.
2. **Transfer** : Risk can be transferred/shared by using insurance. 
3. **Mitigate** : Controls can be used to mitigate and reduce risks. 
4. **Accept** : If the cost of control outweights the cost of risk, the organisation accepts the risk.


## Risk Assessment

A risk assessment, or risk analysis, is an important task in risk management. 
1. Quantify and qualify risks based on different values of assets.
2. Identify threats and vulnerabilities, determine likelihood of exploitation and identify impact of threats.
3. Make recommendations for what controls to implement.

### Quantitative Risk Assessment
Here the risk is measured according to its monetary value which helps in prioritizing risks.

The following are used to identify quantitative risks:
* Single loss expectancy (SLE). The SLE is the cost of any single loss.
* Annual rate of occurrence (ARO). The ARO indicates how many times the loss will occur in a year. 
* Annual loss expectancy (ALE). The ALE is the value of SLE × ARO.

The cost helps identifying whether the risk should be mitigated or accepted.

### Qualitative Risk Assessment
Here the risk is judged on the basis of likelihood of the occurence and impact. These assessments are based on judgements and not pure numbers. 

Risks which have high impact and high occurences are more likely to have better mitigations in place. 

### Risk Registers

Risk registers are used to record all risk present. They might include:
* Category
* Specific Risk
* Likelihood of occurence
* Impact
* Risk Score
* Security controls or mitigation steps
* Contingencies
* Risk score with security controls
* Action assigned
* Action deadline

### Supply Chain Assessment

A supply chain assessment evaluates these elements—the raw materials supply sources and all the processes required to create, sell, and distribute the product.

## Scanning and Testing Tools

### Checking for vulnerabilities

Vulnerability assessments and various scans such as network scans and vulnerability scans help in identifying weaknesses in a network. The overall goal of a vulnerability assessment is to assess the security posture of systems and networks.

### Password Crackers

A password cracker attempts to discover passwords from hashes or encrypted text. It can be done online(brute force) or offline(hash cracking/decrypting text). 

### Network Scanners

A network scanner uses various techniques to gather information about hosts within a network. They use techniques like ping scan, ARP ping scan, Syn health scan, port scan, service scan and OS detection.  
They also have in creating a network map which shows how the network is laid out. 

### Wireless Scanners
Wireless scanners can typically use both passive and active scans.  
When using a passive scan, a scanner just listens to all the traffic being broadcast on known channels within the 2.4 GHz and 5 GHz frequency ranges.  
When using an active scan, a wireless scanner acts like a scanner/cracker and can gain more information about an AP by sending queries to it.  
Wireless scanners can also help in rogue endpoint detection for administrators of the network.

### Banner Grabbing

Banner grabbing is a technique used to gain information about remote systems and many network scanners use it. It is often used to identify the operating system along with information about some applications.

### Vulnerability Scanning

A key part of a vulnerability assessment is a vulnerability scan. Security administrators often use a vulnerability scanner to identify which systems are susceptible to attacks. 

* Identify Vulnerabilities and Misconfigurations: Open ports, weak passowrds, default accounts, sensitive data leakage etc are checked for.
* Passively test Security Controls
* Identify lack of Security Controls

### Configuration Compliance Scanner

A configuration compliance scanner verifies that systems are configured correctly. They will often use a file that identifies the proper configuration for systems.

### Penetration Testing

Penetration testing actively assesses deployed security controls within a system or network. It starts with passive reconnaissance, such as a vulnerability scan, but takes it a step further and tries to exploit vulnerabilities by simulating or performing an attack.

Steps in a pentest:
* **Passive reconnaissance** : Collect information about a targeted system, network, or organization using open-source intelligence.
* **Active reconnaissance** : Using tools to send data to systems and analyzing the responses. It may use network scanners vulnerability scanner and other such tools. 
* **Initial exploitation** : After an active scan the pentesters try to exploit one of the vulnerabilities to gain access to the systems. 
* **Escalation of privilege** : After gaining access to low-level system the pentester tries to gain access to higher privileged accounts.  
* **Pivot** : The process of using various tools to gain additional information.
* **Persistence** : Attackers often use various threats that allow them to stay within a network for weeks, months, or even years without being detected. Penetration testing techniques use similar techniques to maintain persistence within the network.
* **White Box Testing** : Testers have full knowledge of the environment before starting a white box test.
* **Grey Box Testing** : Testers have some knowledge of the environment prior to starting a gray box test.
* **Black Box Testing** : Testers have zero knowledge of the environment prior to starting a black box test.


### Intrusive Versus Non-Intrusive Testing

Intrusive testing might lead to disruption of service in some cases. Generally, Pentests are more intrusive as compared to vulnerability scans. 
