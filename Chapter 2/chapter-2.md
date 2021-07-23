# Understanding Identity and Access Management

**Identification** : User claims their identity with unique identifiers like email or username.  
**Authentication** : The process where a user proves their identity.  
**Authorization** : Granting permission to users based on their identity.  
**Accounting** : Tracking user activity and recording the activity carried out by the user. 

## Authentication Factors:
1. **Something you know** -> pins or passwords 
   1. *Complexity* : passwords should not be easily guessable and have a mixture of special characters, numbers and uppercase and lowercase characters.
   2.  *Expiration* : passwords should generally have an expiration time of 45-90 days so that users do not keep using the same password. 
   3.  *History and Reuse* : passwords with a fixed expiration time generally hace an issue that users keep switching a few passwords over and over, which is similar to using the same password. Hence, there should be a reuse policy where you cannot use a password you have used in the last 3-5 times. 
   4.  *Recovery* : There should be proper validation before sending a password recovery request. Also, the recovery request should be sent to an alternate email/mobile number and not given out. This ensures that there is no unauthorized request to recover passwords.
   5.  *Account lockout* : If some user tries to unsuccessfully login into their account multiple times, the account should be locked for a certain duraiton of time.
   6.  *Default Passwords* : Many systems and devices have a default password which should be changed ASAP. Also try changing name of admin accounts to that bruteforcing admin accounts becomes difficult.  
2. **Something you have** -> USB tokens, hardware wallets
   1. *Smart Cards* : cards with embedded microchips and certificate to validate a user. 
   2. *Common Access Cards/Personal Identity Verification* : Used by UD DoD and Federal agencies respectively to support dual factor authentication. 
   3. *Tokens/Key Fobs* : Hardware wallets synced to a server which keep changing value every 60 seconds or so. [example](https://www.google.com/search?q=secure+ID+image&ei=rjxrYNemN8e1rQHvuIrwDQ&oq=secure+ID+image&gs_lcp=Cgdnd3Mtd2l6EAMyAggAMgoIABAHEAUQChAeOgUIABCwAzoLCAAQsAMQCBAKEB5QzidY5ShguS5oAXAAeACAAbcBiAHPA5IBAzAuM5gBAKABAaoBB2d3cy13aXrIAQLAAQE&sclient=gws-wiz&ved=0ahUKEwjXtc_1xOfvAhXHWisKHW-cAt4Q4dUDCA0&uact=5) 
   4.  *HOTP* : open standard for creating OTPs. Uses HMAC with an incrementing counter to create 6-8 digit OTP. 
   5.  *TOTP* : Time based OTP which user timestamp instead of counter like in case of HOTP. 
3. **Something you are** -> Biometrics. 
   1. *Fingerprint scanner*
   2. *Retina scanner*
   3. *Iris scanner*
   4. *Voice recognition*
   5. *Facial recognition*
4. **Somewhere you are** -> geolocaltion technologies
5. **Something you do**  -> patterns in phones


In biometrics, there always exists some errors and failures. These can be clubbed into:
* False Acceptance(FAR)
* False Rejection(FRR)
Biometric systems allow you to set the FAR and FRR by adjusting the sensitivity. 
A CER(Crossover error rate) can be obtained by plotting the FAR and FRR and CER is at the point where the two interact. The lower the value of CER, more effective the system is.


**Methods of authentication when using the same factor DO NOT qualify as MFA. Its considered MFA iff multiple authentication methods are used.**


## Authentication Servers:

### Kerberos 
* Used in Windows AD and some Unix environments. 
* Provides mutual authentication and helps prevent MITM attacks. 
* It requires: 
    1. A method of issuing tickets used for authentication or **KDC**.
    2. Time synchronization.
    3. A database of subjects or users.
  
### NTLM -> New Technology LAN Manager  (*Deprecated*)

* suite of protocal providing authentication, integrity and confidentiality within Windows envs. 


### LDAP -> Lightweight Directory Access Protocol
* specifies formats and methods to query directories
* extension of X.500 standard. 
* Active Directory Queries use LDAP.


### SSO -> Single Sign On
* ability to login to a single system and being granted access to multiple order systems. 
* probably the most highly used and known services in todays time. 
* Both Kerberos and LDAP support SSO. 
* A down side is that the passwords need to be strong in order for better security of accounts, else all accounts of the user might be vulnerable. 

SSO leads to transitive trust. i.e. since Google has already verified me, Twitter allows me to login with Google SSO as it trusts Google to have verified my account before giving me the access to my Google account. 

**SSO and SAML** -> The above Twitter and Google example use SAML as the way they communicate with rach other. 

**SAML and Authorization** -> SSO does not generally provide authorization, however, many SSO systems do provide this functionality. 

**SSO and Federation** -> A federation requires a federated identity management system that all members of the federation use. A federated identity links a user’s credentials from different networks or operating systems, but the federation treats it as one identity. *[Shibboleth](https://en.wikipedia.org/wiki/Shibboleth_Single_Sign-on_architecture)*

**OAuth and OpenID Connect** -> OAuth is an open standard for authorization many companies use to provide secure access to protected resources. This enables users to use a single account at multiple different places. OpenID Connect works with OAuth 2.0 and it allows clients to verify the identity of end users without managing their credentials. This saves companies the hassle of storing passwords and verifying users.

## Managing Accounts

**Least Privilege** : Only the required permissions are given to a user, no more no less.  
**Need to know** : All new employees should be granted access to information they need to know to do their job. 
**Types of Accounts** 
   1. End User Accounts : Regular accounts with appropriate roles based on their responsibilities. 
   2. Privileged Accounts : A privileged account has additional rights and privileges beyond what a regular user hag
   3. Guest Accounts : Temporary accounts for outside agency, contracters etc. 
   4. Service Accounts : Similar to regular accounts, but generally used by applications or services. 

It is recommended for *administrators to have two accounts*, a regular one and an admin account. This enables them to do regular day to day work with regular privileges preventing issues where an attacker can gain direct access to the administrator account.

**Prohibiting shared and generic accounts** -> Shared accounts make it difficult to implement access controls and identification. 

## Comparing Access Control Models

**Subjects** are typically users or groups that access an object. Occasionally, the subject may be a service that is using a service account to access an object.  
**Objects** are items such as files, folders, shares, and printers that subjects access. For example, users access files and printers. The access control helps determine how a system grants authorization to objects.

The following are the Access Control methods for providing access to objects for each subjet.
* **Role-based access control (role-BAC)** -> Roles manage rights and permissions. Generally useful in places where there are multiple departments each having multiple people requring the same specific set of permissions. Role-BACs can either be heirarchy based or Job/function based.  
* **Rule-based access control (rule-BAC)** -> Rules manage access. Example, ACLs and Firewalls. 
* **Discretionary access control (DAC)** -> Here every object has an owner and the owner decides who can and cant access the required files. 
* **Mandatory access control (MAC)** -> Uses labels to determine access to a file. Iff a label on a resource matches the user label, access to the resource is granted. Generally used in military organisations. It uses a Labels and Lattice model to define security access. The access is also based on need to know basis, i.e. a person with top-secret clearance in 'X' does not have access to all top-secret info in 'Y'.
* **Attribute-based access control (ABAC)** -> Evaluates attributes and grants access based on the value of these attributes. Attributes can be almost any characteristic of a user, the environment, or the resource. Generally has:
  * *Subject* i.e. the user.
  * *Object* i.e the resource.
  * *Action* being performed by the user
  * *Environment* i.e everything outside the subject and object attributes. 

ABAC can be used to enfore both DAC and MAC. 