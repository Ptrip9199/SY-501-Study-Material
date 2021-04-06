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
3. **Something you are** -> fingerprint or other biometrics
   1. *Fingerprint scanner*
   2. *Retina scanner*
   3. *Iris scanner*
   4. *Voice recognition*
   5. *Facial recognition*
4. **Somewhere you are** -> geolocaltion technologies
5. **Something you do**  -> patterns in phones

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


