# Securing Your Network

## Intrusion Detection Systems

IDS monitor a network and send alerts when they detect suspicious events on a system or network.

**HIDS**  or Host based IDS are softwares installed on servers or workstations as an addition measure to monitor traffic passing through the NIC.

**NIDS** or Netowrk based IDS monitor activity on a netowrk. A NIDS might be limited in its ability to detect anomalies as it might be monitoring encrypted traffic and hence not be as effective as HIDS. 

### Detection Methods

**Signature Based Detection** which has a collection of all existing threat actors and block them. These can be used to identify more common and known attacks. 

**Heuristic/Behavioral Detection** identifies normal operation and then in case there are any anomailes, they raise alerts for them. These can be used to identify zero days or unknown vulnerabilites. However, these need to be re-configured every time there are changes in network which might lead to a change in the network traffic or else it can lead to false positives. 

All IDS systems require raw data sources such as firewall logs, system logs, application logs etc. These logs help detect anomalies. Some IDS do real time log nmonitoring, whereas some perform periodic polling of all devices to get the logs and then analyse them.

IDS send alerts to the Administrator who has to finally decide whether the alerts are actual threats that need to be acted upon or not. 

IDS are susceptible to both false positives and false negatives, reducing both is not possible so the Administrator has to set a balance and adjust the IDS accordingly. 



## Intrusion Prevention Systems
IPS react to attacks in progress and prevent them from reaching systems and networks.

IPS are an extesnsion of IDS, but while IDS are passive, IPS can respond to the threat and possibly prevent attacks from happening. 

IPS are located inline in the network and all the traffic has to pass through them, hence they can help in blocking malicious traffic. 



## SSL/TLS Accelerators

SSL/TLS Accelerators are hardware devices which are used in the process of handling TLs traffic. These accelerators help in freeing up the resources of the machine and make it more available for the task they are acrually supposed to perform. TLS Acceleratoes should be placed as close to the device which is using the decrypted traffic. 

## SSL Decryptors

SSl Decryptors are used to combat threats and malware which might otherwise go undetected in encrypted traffic. SSL encrypted malwares are hard to catcn, so a SSL Decryptor after performing the decryption can check if the traffic is malicious or not. Generally NIPS might use something like this to actively prevent attacks on te systems. 

## SDN(Software Defined Networking)

SDN uses virtualization technologies to route traffic instead of using hardware routers and switches. This can help organisations move away from proprietary hardware and use only software for routing mechanism. ABAC are commonly used in SDNs in place of ACLs in routers. 

## Honeypots

A honeypot is a server placed in the network which might look like its an easy place to attack in the network and hence attackers may try to attack the server. The honeypot in response alerts the organisation that some malicious actor is on the network giving time for the Network and Security Teams to respond to the threat. 

Honeypots serve 2 purposes:  
1. Divert attackers from the network.
2. Allow observing the attacker and help IDS in protecting against the same threats in the future. 

**Honeynets** are groups of honeypots in a separate network from the primary network. 

## IEEE 802.1x Security

802.1x is a port based authentication protocol and requires users and devices to authenticate when connecting to a port or a network. It prevents rogue devices from connecting to the network and performing any active or passive attacks on the network. 

### Securing Wireless Networks

**Fat AP** includes everything reqiured to connect wireless clients to a wireless network and has NAT, DHCP etc built=in. 

**Thin AP** is a controller-based AP which are managed by controllers and can't be used. 

802.11 includes 2 Bands 2.4GHz and 5GHz which can be used. Each band has multiple channels ranging in size from 20MHz-160MHz.

Wider channels allow to transfer more data, but lead to more interference in the network and their ranges are limited. 

**AP SSID** is the identifier that is used to uniquely identify a wireless network.

SSID Broadcasting happens to let systems around the AP identify the presence of a near-by AP. Disabling broadcast **does not help in security** of the AP.

**MAC Filtering** can set a blacklist/whitelist to limit the number and what devices can be connected to an AP. 

### Wireless Cryptographic Protocols

**WPA** or Wi-Fi Protected Access is a replacement of WEP as a solution not requiring an hardware update to the AP. WPA is susceptible to password cracking attempts.

**WPA2** uses stronger cryptography than WPA. WPA2 is also not enough for organisations which require enterprise level security. WPA2 requires the use of  Counter Mode with Cipher Block Chaining Message Authentication Code Protocol (CCMP).

**PSK** or pre-shared key is used in most of the places and devices can connect anonymously to the network and use it. 

**Enterprise** mode forces users to authenticate with unique credentials before granting them access to the AP. The AP connects to a RADIUS server which helps authenticate the user. 


### Authentication Protocols

**EAP** provides a method for two systems to create a secure encryption key, also known as a Pairwise Master Key (PMK). Systems then use this key to encrypt all data transmitted between the devices. TKIP and CCMP use this type of authentication. 

**EAP-Flexible Authentication via Secure Tunneling (EAPFAST)** was designed by Cisco as a secure replacement for Lightweight EAP (LEAP). EAP-FAST supports certificates, but they are optional.

**Protected EAP (PEAP)** provides an extra layer of protection for EAP. EAP assumed physical security would always be accounted for which was ont the case,and henace PEAP was formed. PEAP encapsulates and encrypts the EAP conversation in a Transport Layer Security (TLS) tunnel. PEAP requires a certificate on the server, but not the clients.

**EAP-Tunneled TLS (EAP-TTLS)** is an extension of PEAP, allowing systems to use some older authentication methods such as Password Authentication Protocol (PAP) within a TLS tunnel. EAPTTLS requires a certificate on the 802.1x server but not the clients.

**EAP-TLS** is one of the most secure EAP standards and is widely implemented. The primary difference between PEAP and EAP-TLS is that it requires certificates on the 802.1x server and on each of the wireless clients.

**RADIUS Federation** uses Federation servers by which users can log into multiple systems using a single authentication service. 

**Captive Portals** force a web client to login before being able to access the network. They can be used for public Free Internet access, Paid Access where internet charges are charged on a pay-as-you-go basis, or as a replacement for 802.1x which is sometimes very expensive for smaller places. 


### Wireless Attacks

**Disassociation Attack** disconnects the client from the AP. The AP generally keeps the MAC of associated devices stored in its memory, but disassociation attacks are able to clear this memory forcing the client to reconnect.

**WPS/WEP Attacks** is possible because WPS pin is a 8 digit number which can be easily brute-forced. If this PIN is brute-forced, WPA/WPA2 passphrases can be easily discovered. WPS is generally kept off by default in all APs for this reason. 

**Rogue AP** is an AP which is placed in a network without authorization. This type of attack can make the network vulnerable to outside attacks, and even sniffing attacks. 

**Evil Twin** is an attack vector where the attacker AP has the same SSID as your legitimate AP. This can be used for credential capturing as well.

**Jamming Attacks** transmit noise at the frequesncy used by wireless network causing the entire network to fail or have very poor performance. 

**IV Attacks** attempt to discover the preshared key from the IV. In many IV attacks, the attacker uses packet injection techniques to add additional packets into the data stream. The AP responds with more packets, increasing the probability that it will reuse a key.

**NFC Attacks** use NFC readers to capture NFC data from other NFC devices. 

**Bluetooth Attacks** include various different attacks like *Bluejacking* where unsolicited messages are sent to nearby devices, *Bluesnarfing* is the unauthorized access or theft of info from Bluetooth device or *Bluebugging* which goes further from bluesnarfing to gain complete access of the device. 

**Wireless Replay Attack** happens when an attacker captures data between two entities and replays the message. WPA2 using CCMP and AES is not vulnerable to replay attacks. however, WPA using TKIP is vulberable.

**RFID Attacks** include various different attacks like *Sniffing*, *Replay* and *DoS*.

**Misconfigured Access Points** are the main reason wireless attacks are successful. It is best if you use WPA2 with CCMP and AES to secure your Wi=Fi. 

### VPN for remote access

VPNs allow users to access private networks via a public network. Different tunneling protocols encapsulate and encrypt the traffic to protect the data from unauthorized disclosure. The tunnel prevents anyone from reading the data transferred through it.

**VPN Concentrators** are servers/computers which provide a secure network for traffic. These server require 2 NICs, one accessible from the internet and other providing access to internal network. 

**IPsec Tunneling**  
IPsec supports both Tunnel mode and Transport mode. *Tunnel mode* encrypts the entire IP packet used in the internal network, and is the mode used with VPNs transmitted over the Internet. Transport mode only encrypts the payload and is commonly used in private networks, but not with VPNs.

IPsec provides **AH**(Authentication and Integrity) and **ESP**(Confidentiality, Authentication and Integrity)


**TLS Tunneling**  
Some tunneling protocols like OpenVPN and OpenConnect use TLS to secure the VPN channel. 

**Split Tunnel vs Full Tunnel**  
In split tunnel the admin decides what traffic goes thriugh the VPN and what not. In case of full tunnels, all the traffic goes through the VPN. In case of full tunnel, a UTM device would be making the required external calls and returning the response. 


**Site-to-Site VPNs** have two VPNs at the either end of the geographically separated network. The user can use the different networks as a single network without any extra measures in case of site-to-sire VPNs.  

Devices with **Always-On VPN** connect to the VPN as soon as they are turned on. 

**Network Access Control** methods provide continous security monitoring and prevent compromised devices from connecting to the network. NAC provides a measure of control for these other computers. 

**Host Health Checks** are used to identify where a given device is working normally or not. Administrators set predefined conditions, which meet conditions for the machine being healthy. NACs use these conditions to verify if a given system is healthy or not to allow the device from connecting to the network. If a client doesn’t meet the health conditions mandated by the NAC server, the VPN server redirects the client to a remediation network (also called a quarantine network). The remediation network includes resources the client can use to get healthy.

**Permanent NACs/Persistent NACs** stay on the client forever. **Dissolvable NACs** are downloaded and run whenever a client tries to connect to a network and these do not persist. Dissolvable NAcs are useful for organisations with a BYOD policy. 

**Identity and Access Services** help in ensuring that only authorized entities can access the network. 
1. PAP(Password Authentication Protocol):
   *  sends plaintext password.
   *  generally used in PPP to authenticate clients.  
2. CHAP(Challenge Handshake Authentication Protocol): 
   * uses handshake process between server and client to authenticate user.
   * sends a hash of the password and a server issued nonce so no one can snoop on it 
3. MS-CHAP and MS-CHAPv2: 
   * are Microsoft implementations for CHAP:
   * MS-CHAPv2 supports mutual authentication, i.e client can verify server as well. 
4. RADIUS(Remote Authentication Dial-In User Service): 
   * has a centralized authentication service. 
   * can connect with domain controllers or LDAP as a database for user details. 
   * encrypts the password packets, but not the entire authentication process
   * uses only UDP.
5. Diameter: to overcome limitations of RADIUS. 
   * added features over RADIUS
   * adds suport for TCP and UDP
   * backwards compatible with RADIUS
6. TACACS+(Terminal Access Controller Access-Control System Plus): 
   * CISCO alternative to RADIUS. 
   * unlike RADIUS, TACACS+ encrypts all packages and not just password package. 
   * supports Kerberos and hence can communicate with Microsoft AD. 