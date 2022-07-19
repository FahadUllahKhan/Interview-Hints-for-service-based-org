# Interview-Hints
This interview questions check list is created for the post of Information security consultant / ethical hacker


Questions 

------------- 

What is CIA..? 

CIA is a model, designed to guide policies for information security within an organization. 

 
Confidentiality: 

ensure to prevent the sensitive data or information from unauthorized access attempts. 

 
Integrity: 

ensure that the data must not be changed during transmission. it maintaining the consistency, accuracy and trustworthiness. 

 
Availability: 

means, that the information should be available and accessible for authorized parties whenever they needs to do so. 

 
Non-Repudiation: 

Non-Repudiation ensure that someone cannot deny the validity of something. 

  

SQl injection..? what is blind and error based..? 

sql injection is a type of injection attack which hacker can inject maleciuse sql code to manipulate backend database and gain access to potentially valueable information. 

 
Type of sql Injtections..? 

error based > in this attacker inject meliciouse code and database generate sql error. 

union based > ths technequce take advantage of UNION operater, which fuses multiple select statements generate 

blind sql > in this, the attacker uses the reponse and behavioral patterns of the server post-sending data payloads to learn about its structure. 

blind boolean based > attacker send sql query to the database, letting the application respond by generating either a true or false result 

blind time based > attacker send a sql query to database, making the database waiting before it finally respond. 

out of band sql injection > this attack is executed under two cirumstances, 

 
how to Mitigate..? 

use parameterized queries 

use stored procedure  

white list user's inputs 

Enforce least privilege's to the database tables. 

 

what we can do with Sql injection..? 

 
we can get valuable information  

we can damage the organization assets. 

we can delete the hole database or some valuable information from BD. 

we can get reverse shell. 

 
how we can get reverse shell using sql Injection.. 

steps: 

identification of sql injection and use UNION operator 

 
first identify sql injection. 

use UNION operator to identify the current user and database and its version 

use load_file() and enter /etc/passwd into load_file() and hit enter to show passwords. 

 
Upload the web shell and get reverse connection 

 
very important to identity the correct Webroot. for apache the Webroot path is "/var/www". 

use UNION SELECT to create a php file in the Webroot using INTO OUTFILE'/var/www/directory/cmd.php'. following is the complete syntxt  

' UNION SELECT 1,C'<?php system($_GET[\'cmd\']) ?>' INTO OUTFILE '/var/www' 

Now, Open the browser and open the cmd.php file where we uploaded in the webroot. 

and let run come command like id and you will get some result. 

 

What is XXS..? and its types..? 

XSS occurs when attacker can injects malicious JavaScript code into the website and steel browser informations to inpersonate user. 

 
types: 

Reflected XSS: > occur when a malicious script is reflected on web application to the victim’s browser. and steel user's browser information. 

Stored XSS: > this type of vulnerability occurs when malicious JavaScript directly stored on a target server. every user of the website whenever they open the     web application the malicious script will be run. 

DOM XSS: > DOM XSS attack ariase when the attacker's payload is executed as a result of modifying the DOM - Document Object Model “environment”. 

A DOM-based XSS attack is often a client-side attack and the malicious payload is never sent to the server. 

 
Prevention of DOM XSS: 

Sanitize user's inputs, 

Use escaping/encoding, 

Sanitize HTML, 

Set the HttpOnly flag, 

Use a Content Security Policy,  

sanitize all untrusted data,  

 

Validate user inputs 

Sanitize user inputs 

Encode special characters 

Use Anti-XSS services/tools 

Use XSS HTML Filter 

  

What is IDOR..? 

IDOR is a type of access control vulnerability that arises when an application uses user-supplied input to access objects directly. 

 
IDOR Types: 

Obtaining unauthorized data access:, 

Performing unauthorized operations, 

Manipulating application objects, 

Getting direct access to files, 
 

Prevention: 

The best way to prevent IDOR vulnerabilities is to implement strict access control checks on every functionality 

to see if the user is authorized to access and/or manipulate the requested object. 

Use an Indirect Reference Map, 

Validate User Access, 
 

What is SSRF..? 

A server-side request forgery (SSRF) attack involves an attacker abusing server functionality to access or modify resources. 

  

Process of Penetration testing..? 

steps: 

Planning and reconesinsse 

scanning  

gaining access  

Maintaining access 

covering tracks 
 

ICMP and Ping..? 

PING: 

Ping is a troubleshooting tool used by system administrators/pentester to manually test for connectivity between network devices, ping use ICMP protocols to check whether the machine live or not. 

ICMP: 

ICMP is a network layer protocols, 

diagnose network communication issues, 

used to determine whether or not data is reaching its destination 

send echo message to server and get echo reply if server/machine is live. 

 

As a black box hacker, you only know the name of the target. how to enumerate further..? 

steps1: 

find subdomains 

tools: 

Sublist3r 

subFinder 

knockPi 

FindSubDomains 

etc. 

step2: 

Port and Service enumeration: > Nmap 

run Nmap with -sV flag and observe the open ports and runing services. 

if port 21 FTP open. try anonymouse. 

if port 25 SMTP open. try to check mail relay. 

if there is out-dated service is runing agianst any service, search for publix exploit if avialble. 

if port 445 open check for SMB enumerat 

if port 80 or 443 open, the attack surfece will be incress. 

 

Actice and Passive recon..? 

 
Active Recon: > Active recon is when you interact directly with a computer system in order to gather specific information about the target.  

Nmap 

Nessus 

OpenVAS 

Nikto 

Metasploit 

 
Passive Recon: > Passive recon is when you gather information about a target without directly interacting with the target. this means that you don't send any type of request to the target. 

wireShark 

Google Hacking 

Netcraft 

FindSubDomains.com 

shodan 

 
What is DNS..? and what is forward lookup and reverse lookup..? 

DNS: 

The Domain Name System (DNS) is the phonebook of the Internet. that resolve hostname aginst IP address. 

 
forword lookup: 

The process of finding an IP address based on the hostname in DNS is called forward lookup. 

 
Reverse Lookup 

the process of finding hostname based on the IP address in DNS is called reverse lookup. 

 

What is Port scanning..? 

Port Scanning is the technique used to identify open ports and service available on a host. 

port scanning is used to find informations that can be helpful to exploit vulnerabilities. 
 

Techniques are: 

Ping Scan 

TCP Half-Open 

TCP Connect 

UDP 

Stealth Scanning 

 
What is XML Injection..? 

XXE is a type of attack against an application that parses XML input. This attack occurs when XML input containing a reference to an external entity is processed by a weakly configured XML parser. 

This attack may lead to the disclosure of confidential data, denial of service, server side request forgery, port scanning from the perspective of the machine where the parser is located, 

and other system impacts.” 

 
Types: 

Exploiting XXE to retrieve files, 

Exploiting XXE to perform SSRF attacks, 

Exploiting blind XXE exfiltrate data out-of-band, 

Exploiting blind XXE to retrieve data via error messages 

 
Preventation: 

use less complex data formats such as JSON 

Patch or upgrade all XML processors and libraries 

Disable XML external entity and DTD processing in all XML parsers 

("whitelisting") server-side input validation, 

SAST tools can help detect XXE in source code, 

 
What is Penetration  Testing Methodologies..? 

There are four types of methodologies.. 

    OSSTMM 

    OWASP 

    NIST 

    PTES 

 

What is Ethical hacking methodologies/Steps..? 

    Reconnaissance  

    Scanning 

    Gaining access 

    Maintaining access 

    Covering tracks 

 
What is the Penetration testing approach..? 

    Black Box  

    White box 

    Grey Box 

 
Types of penetration testing..? 

    Web application penetration testing 

    Network services / Infrastructure Penetration testing 

    Client-side penetration testing 

    Wireless penetration testing  

    Social engineering penetration testing 

    Physical penetration testing 

 
Mobile application Penetration Testing Methodologies/Stages..? 

    Discovery 

        Open source Intelligence  

        Understand the architecture 

        Client side vs server side scenario 

    Assessment and analysis 

        Static analysis 

        Dynamic analysis 

        Reverse engineering  

        Local file analysis 

        Archive analysis 

    Exploitation  

        Open source Intelligence 

        Architecture understanding 

        Client and server side situation 

    Reporting 

        Preparation report 

        presentation 
         

 
What is Application Security..? 

Application Security is aim to protect software application code and data against cyber threats. You can and should apply application security during all phases of development, including design, development and deployment. 


What types of applications does a modern organization needs to secure..? 

    Web Application Security 

    API Security. 

    Cloud Native Application Security. 

 
What is application security testing..? 

Application Security Testing (AST) is a processes of making application more resilient to security threats by identifying and remediating security vulnerabilities. 

    Key Consideration before testing application. 

        Create a complete inventory of your applications. 

        Understand the business use, impact and sensitivity of your applications. 

        Determine which applications to test—start from public-facing systems like web and mobile applications. 

     
    How to Test..? 

        Authenticated vs Non-authenticated testing 

        Which tool to use 

        Testing production vs Staging 

        Whether to disable security system while testing 

        When to test 

        What to report 

        Validation testing 

     
Types of Application Security Testing..? 

    Black Box 

    White Box  

    Grey Box 

 
Application Security Tools and Solution..? 

    Web Application Firewall (WAF) 

    Runtime Application Self-Protection (RASP) 

    Software Composition Analysis  (SCA) 

    Static Application Security Testing (SAST) 

    Dynamic Application Security Testing (DAST) 

    Intractive Application Security Testing (IAST) 

    Mobile Application Security Testing (MAST) 

    Cloud Native Application Protection Platform (CNAPP) 
