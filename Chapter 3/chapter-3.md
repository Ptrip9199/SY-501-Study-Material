# Exploring Network Technologies and Tools

## Types of Attacks: 
1. Sniffing Attacks : Capture data over the internet and read that data using protocol analyser. 
2. DoS and DDos : Service disruption attacks. 
3. Poisoning Attacks : Try to change cached values with different values.

## Networking Protocols: 

1. **TCP** -> connection oriented traffic with guaranteed delivery. it uses a 3 way handshake to start a session. 
2. **UDP** -> connectionless session without the guarantee of delivery. 
3. **IP** -> Network layer protocol with ensures delivery of TCP/UDP packets to the right host. Uses 32/128 bit IPv4/6 addresses to uniquely identify devices. 
4. **ICMP** -> Network layer protocol which is used to test basic connectivity. 
5. **ARP** -> Resolves IP addresses to MAC addresses i.e physical addresses of the device the message is being sent to. 
6. **NDP** -> IPv6 version of ARP and discovers IPv6 devices on the network.

## Use case wise protocols:

### Voice and Video Use Case:
In case of streaming services its UDP that is used as it ensures once only delivery.   
**RTP(Realtime Transport Protocol)** delivers audio and video over IP. VoIP, streaming, video teleconferencing all use RTP/Secure-RTP. 

### File Transfer Use Case:

Users might want to transfer files over the internet for multiple use cases like Online Cloud Backups. 

**FTP** is the most widely used protocol for the same and uses TCP. It uses port 21 for control signals and 20 for data. FTP passive uses port 21 for control and a random port for data. 

**TFTP** Trivial FTP uses UDP port 69 and is useful for transferring small amounts of data. 
FTP can be secured by using any of TLS, SSL, SSH or IpSec. 

**SFTP** uses SSH for secure FTP. It uses port 22 to transmit data. 

**FTPS** uses TLS to encrypt traffic. It generally uses 989 and 990 but this can be changed to 21 and 20.  

### Email and Web Use Case:

**SMTP(Simple Mail Transfer Protocol)** transfers emails between clients and SMTP servers.  It uses YCP port 25 and unofficially uses 587 for TLS and 465 for SSL. Recommended pracitce is to use STARTTLS for secure communication.  

**POP3(Post Office Protocol)** transfers emails from servers to client. Uses TCP 110.  

**IMAP(Internet Message Access Protocol)** is used to store email on email servers. Uses TCP 143. Gmail uses IMAP4.  

**HTTP/HTTPS** : protocol of the web. uses 80 for insecure and 443 with TLS/SSL. Used by browser.

### Directory Access Use Case:

**Kerberos** is used in Windows and Unix environments and it uses a KDC to issue timestamped tickets. It uses UDP 88.  

**LDAP** is used to communicate with services such as AD. It uses TCP 389. LDAPS uses 636 for using TLS/SSL.

### Remote Access Use Case:

Telnet(23). SSH(22) and Netcat(any) are generally used in remote access. Windows uses RDP(3389 TCP or UDP) for remote GUI access. 

### Time Synchronization Use Case:

In some systems the time needs to be synchronised for proper functioning of the system. For example, Kerberos where the tokens are time based. NTP(Network Time Protocol) is used in such scenarios.

### Network Allocation Use Case:

**IPv4** which is a 32-bit address expressed in dotted decimal format. Limited public IPs available and all of them are exhausted, so IPv6 was created. IPv4 is still very widely used as the infra is available for the same and NAT helps share public IPs. 

**IPv6** has 128-bit addresses expressed in hexadecimal format with 8 groups of 4 hexadecimal numbers. It has local workspace and no private IP space due to the large number of addresses available. *fc00* is the prefix for local addresses.


### Domain Name Resolution Use Case:

**DNS** is used to resolve IP for a given URL. Uses UDP and port 53. 
Types of DNS records:
1. *A* -> host record. Holds hostname along with IP and is used in IP lookup. 
2. *AAAA* -> IPv6 host record.
3. *PTR* -> Pointer record which gives the DNS of a given IP. 
4. *MX* -> Mail Exchanger. Identifies mail server used for email. 
5. *CNAME* -> Allows a single system to have multiple associated IPs. 
6. *SOA* -> Start of Authority record includes information about DNS zone and related settings. 

**DNSSEC** is used to overcome DNS poisoning. Adds a digital signature to each DNS record for validating DNS response. 

**Nslookup** or name server lookup is used to troubleshoot DNS related problems. It can resolve specific hostname or FQDNs(Fully Qualified Domain Names) to IP address. 

## Ports Identification:
There are 65536 ports. 
Port numbers used are assigned by IANA. 
1. 0-1023 : Well Known Ports and generally used for commonly used protocols. 
2. 1024-49151 : Ports are regestered to companies for their services. eg, Apache Tomcat on 8080, MySQL on 3306 etc. 
3. 49152-65535 : Dynamic and private ports which can be used by any application. Sometimes even to launch temporary services. 

Port scanning attacks generally target Well known ports plus a few company allocated ports, for example 3306 which is used by MySQL. 

Ports are used to direct the traffic received to the correct service. For proper communicatoin to take place, a client side port also has to be opened for communication along with the server accepting the traffic. Generally, ports 49152 and above are used on the client side for the server to communicate with the client. 

