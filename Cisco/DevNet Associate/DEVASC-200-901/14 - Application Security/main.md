#   Identifying Potential Risks

&nbsp;

The Nation Institute of STandards and Technology (NIST) defines a framework called the Cybersecurity Framework that is shown in Figure 14-1.  The framework organizes necessary cybersecurity activities into the following functions:

-   Identify:  An organization needs to understand what kinds of cybersecurity risks can affect daily modes of operation.  Areas such as data theft, network breaches, and employee information are some of the risks that need to be identified.
-   Protect:  An organization needs to understand what it can do to prevent attacks.  Protection could include deploying proper networking elements such as firewalls and tools for better software development.  Protection helps minimize the impact of any attack.
-   Detect:  It is important to install tools that detect any data breaches or attacks in a time-sensitive manner or while attacks are happening.
-   Respond:  An organization needs to have a plan in place to deal with an attack.  It needs to know what procedures need to be followed and what can be done to minimize the impact of an attack.
-   Recover:  An organization needs to be able to quickly resolve any services or systems that have been affected.

&nbsp;

**Figure 14-1** *NIST Cybersecurity Framework*

![Figure 14-1 NIST Cybersecurity Framework](assets/images/Figure%2014-1%20NIST%20Cybersecurity%20Framework.jpeg)

&nbsp;

For more details about the Cybersecurity Framework, visit https://www.nist.gov/cyberframework/online-learning/components-framework.

&nbsp;

Application security, as explained in this chapter, uses the Cybersecurity Framework as a substratum to understand some of the key concepts.  To ensure application security, it is important to identify threats and what they affect.

&nbsp;

>   ***`Key Topic`***

&nbsp;

Before we talk about the potential risks, it is essential to understand some key terms and their relationships.  The following are some commonly misunderstood terms:

-   Asset:  An asset is something you're trying to protect.  It could be information, data, people, or physical property.  Assets are of two types: tangible and intangible.  Information and data may include databases, software code, and critical company records.  People include employees and customers.  Intangible assets include reputation and proprietary information.
-   Threat:  Anything you are trying to protect against is known as a threat.  A threat is any code or person that can exploit a vulnerability when it has access to an asset and can control or damage the asset.
-   Vulnerability:  A vulnerability is a weakness or gap in protection efforts.  It can be exploited by threats to gain unauthorized access to an asset.
-   Risk:  Risk is the intersection of assets, threats, and vulnerabilities.  Certain risks can potentially compensate for loss, damage, or destruction of an asset as a result of a threat exploiting a vulnerability.  Threats can always exist, but if vulnerabilities don't exist, then there is little to no risk.  Similarly, you can have a weakness, but if you have no threat, then you have little or no risk.

&nbsp;

##  Common Threats and Mitigations

&nbsp;

In this section, we examine the most common threats.  Table 14-2 describe some of the dangers to application and some mitigation tips for each one of them.

&nbsp;

**Table 14-2** Threats and Sample Mitigation Options

&nbsp;

>   ***`Key Topic`***

&nbsp;

| Threat | What It Does | Mitigation Options |
| -- | -- | -- |
| Buffer overflow | An attacker uses a program to try to cause an application to store that input in a buffer that isn't large enough.  The attacker's data overwrites portions of memory connected to the buffer space.  Attackers can use a buffer overflow to modify a computer's memory and undermine or take control of program execution. | <li>Separate executable memory from non-executable memory.  <li>Randomize address spaces in data.  <li>Use the built-in protection options in newer software OSs and languages |
| Man-in-the-middle | Attackers insert themselves between two endpoints (such as a browser and a web server) and intercept or modify communications between the two.  The attackers can then collect information as well as impersonate either of the two agents.  In addition to targeting websites, these attacks can target email communications, DNS lookup, and public Wi-Fi networks. | <li>Adopt a Secure Socket Layer (SSL)/Transport Layer Security (TLS) strategy for both web and email.  <li>Avoid sensitive data in public Wi-Fi or computers. |
| Denial-of-service (DoS) attack | A threat actor sends multiple requests that flood the server or networks with traffic to exhaust resources and bandwidth.  As they system performance degrades, the system becomes more and more nonresponsive, and legitimate requests are left unfulfilled.  These kinds of attacks can be coordinated, with multiple devices launching attacks at the same time.  Such an attack is known as a distributed denial-of-service (DDoS) attack. | <li>Use specially designed protection services (cloud or network). |
| Cross-site scripting (XSS) | An attacker attaches to a legitimate website code that will execute when the victim loads that website.  This is the typical process:  <ol><li>The webpage is loaded, and the malicious code copies the user's cookies.  <li>The system sends an HTTP request to an attacker's web server with the stolen cookies in the body of the request.  <li>The attacker can then use cookies to access sensitive data.</ol> | <li>Validate and sanitize input data.  <li>Employ cookie security, such as timeouts, encoding the client IP address, and so on. |
| Phishing | A threat actor procures sensitive information - typically usernames, passwords, and so on - from emails or web pages. | <li>Educate users to avoid falling for the bait.  <li>Detect and mark emails and sites as spam. |
| Malware | Malware is a piece of malicious code suh as spyware, ransomware, a virus, or a worm.  Malware is usually triggered when someone clicks a link or an email attachment and inadvertently installs malicious software.  | <li>Deploy technologies that continually monitor and detect malware that has evaded perimeter defenses. |
| SQL injection | Structured Query Language (SQL) injection is a code injection technique used to modify or retrieve data from SQL databases.  By inserting specialized SQL statements into an entry field, an attacker can execute commands that allow for the retrieval of data from the database.  | <li>Use character escaping.  <li>Use stored procedures as opposed to queries.  Enforce privileges. |
| Brute force | A threat actor may use trial and error to decode data.  Brute-force methods can be used to crack passwords and encryption keys.  Other targets include API keys, SSH logins, and Wi-Fi passwords. | <li>Lock the system after a specified number of attempts.  Use two-factor authorization. |

&nbsp;

##  Open Web Application Security Project

&nbsp;

The goal of penetration (pen) test is to identify the possible weak links in applications, servers, or networks that could be used to gain sensitive information or privileged access for an attacker.  It is important to detect such vulnerabilities not only to know that they exist and calculate the risk attached to them but also to make an effort to mitigate them or reduce them to the minimum risk level.

&nbsp;

The Open Web Application Security Project (OWASP) is a community that produces and articulates various reports, tool,s methodologies, and technologies for web application security.  OWASP classifies and defines many application security vulnerabilities.

&nbsp;

>   ***`Key Topic`***

&nbsp;

OWASP has defined a list of security risks called the OWASP Top 10, which can be found at https://owasp.org/www-project-top-ten/.

&nbsp;

This is the current OWASP Top 10 list:

1.  Injection
2.  Broken authentication
3.  Sensitive data exposure
4.  XML external entities
5.  Broken access control
6.  Security misconfiguration
7.  Cross-site scripting
8.  Insecure deserialization
9.  Using components with known vulnerabilities
10. Insufficient logging and monitoring

&nbsp;

The ***CVE (which stands for Common Vulnerabilities and Exposures)*** is a list of publicly disclosed computer security vulnerabilities.  When someone refers to a CVE, he or she usually means the CVE ID number assigned to a security defect.  Security advisories issued by vendors and researches almost always mention at least one CVE ID.  CVEs help IT professionals coordinate their efforts to prioritize and address these vulnerabilities to make computer systems more secure.  CVEs are supervised by the MITRE Corporation, with funding from the cybersecurity and Infrastructure Security Agency, part of the U.S. Department of Homeland Security.  A CVE record usually provides a short one-line description.  Details are usually available on sites such as the U.S. Nation Vulnerabilities Database NVD; (https://nvd.nist.gov/) and the CERT/CC Vulnerabilities Notes Database (https://www.kb.cert.org/vuls/), as well as the sites of prominent vendors in the industry.

&nbsp;

A CVE record consists of the following:

-   ID
-   Description
-   Impact (low/moderate/important/critical)
-   Date published

&nbsp;

A CVE record would look something like this:

-   ID:  CVE-2020-5313
-   Description:  An out-of-bounds read was discovered in python-pillow in the way it decodes FLI images.  An application that uses python-pillow to load untrusted images may be vulnerable to this flaw, which can allow attackers to read the memory of the application they should be not allowed to read.
-   Impact:  Moderate
-   Date:  January 3, 2020

&nbsp;

##  Using Nmap for Vulnerability Scanning

&nbsp;

Nmap, which is short for Network Mapper, is a free open-source utility for network discovery and security auditing.  Nmap is commonly used for network scanning or vulnerability scanning.  Target users for this tool are pent testers, security professionals, and system administrators.  Nmap provides detailed and real-time snapshot information of the devices or hosts on a network.  Nmap primarily provides three functionalities.

-   It gives detailed information on every IP active on a network, and each IP address can then be scanned for more details, if needed.
-   It provides a list of live hosts and open ports and identifies the OS of every connected device.  This makes Nmap an excellent system-monitoring and pen-testing tool.
-   It helps identify security vulnerabilities to protect against attacks.

&nbsp;

The best way to get familiar with Nmap is to use it.  Nmap is available with macOs and Linux by default.  Example 14-1 shows some of the command-line options available.  

>   ***`Key Topic`***

&nbsp;

**Example 14-1** *Using Nmap for Network and Vulnerability Scanning*

```
$ nmap --help
Nmap 7.80 ( https://nmap.org )
Usage: nmap [Scan Type(s)] [Options] {target specification}
TARGET SPECIFICATION:
  Can pass hostnames, IP addresses, networks, etc.
  Ex: scanme.nmap.org, microsoft.com/24, 192.168.0.1; 10.0.0-255.1-254
  -iL <inputfilename>: Input from list of hosts/networks
  -iR <num hosts>: Choose random targets
  --exclude <host1[,host2][,host3],...>: Exclude hosts/networks
  --excludefile <exclude_file>: Exclude list from file
HOST DISCOVERY:
  -sL: List Scan - simply list targets to scan
  -sn: Ping Scan - disable port scan
  -Pn: Treat all hosts as online -- skip host discovery
  -PS/PA/PU/PY[portlist]: TCP SYN/ACK, UDP or SCTP discovery to given ports
  -PE/PP/PM: ICMP echo, timestamp, and netmask request discovery probes
  -PO[protocol list]: IP Protocol Ping
  -n/-R: Never do DNS resolution/Always resolve [default: sometimes]
  --dns-servers <serv1[,serv2],...>: Specify custom DNS servers
  --system-dns: Use OS's DNS resolver
  --traceroute: Trace hop path to each host

<cut for brevity>
```

&nbsp;

##  Basic Nmap Scan Against an IP Address or a Host

&nbsp;

Many switch options can be used with Nmap, and here we focus on a practical one.  To run Nmap against an IP address or a host, you can scan the hostname with the **nmap** *hostname* command, as shown in Example 14-2.  (In this example, *hostname* is www.google.com, but you can replace it with any IP address or hostname, including localhost.)  Use the **-vv** option as shown in this example to see a more verbose output.

&nbsp;

Example 14-2 Using Nmap to Get Details About a Host or an IP address

```
$ nmap -vv www.google.com
Starting Nmap 7.80 ( https://nmap.org ) at 2019-12-08 22:10 PST
Warning: Hostname www.google.com resolves to 2 IPs. Using 216.58.194.196.
Initiating Ping Scan at 22:10
Scanning www.google.com (216.58.194.196) [2 ports]
Completed Ping Scan at 22:10, 0.02s elapsed (1 total hosts)
Initiating Parallel DNS resolution of 1 host. at 22:10
Completed Parallel DNS resolution of 1 host. at 22:10, 0.06s elapsed
Initiating Connect Scan at 22:10
Scanning www.google.com (216.58.194.196) [1000 ports]
Discovered open port 443/tcp on 216.58.194.196
Discovered open port 80/tcp on 216.58.194.196
Completed Connect Scan at 22:10, 8.49s elapsed (1000 total ports)
Nmap scan report for www.google.com (216.58.194.196)
Host is up, received syn-ack (0.025s latency).
Other addresses for www.google.com (not scanned): 2607:f8b0:4005:804::2004
rDNS record for 216.58.194.196: sfo03s01-in-f196.1e100.net
Scanned at 2019-12-08 22:10:05 PST for 9s
Not shown: 998 filtered ports
Reason: 998 no-responses
PORT    STATE SERVICE REASON
80/tcp  open  http    syn-ack
443/tcp open  https   syn-ack
```

&nbsp;

##  CVE Detection Using Nmap

&nbsp;

One of Nmap's most magnificent features for finding vulnerabilities is called the ***Nmap Scripting Engine (NSE)***.  The NSE allows you to use a predefined script or even write your own by using Lua programming language.

&nbsp;

Using NSE is a crucial part of automating system and vulnerability scans.  It request the following syntax:

<pre>nmap -Pn --script vuln <i>hostname</i></pre>

&nbsp;

Example 14-3 shows an example of a vulnerability scan for a device on my home network.

&nbsp;

**Example 14-3** *Using the Nmap Scripting Engine*

```
$ nmap -Pn --script vuln 10.168.243.179
Starting Nmap 7.80 ( https://nmap.org ) at 2019-12-08 22:18 PST
Pre-scan script results:
| broadcast-avahi-dos:
|   Discovered hosts:
|     224.0.0.251
|   After NULL UDP avahi packet DoS (CVE-2011-1002).
|_  Hosts are all up (not vulnerable).
Illegal character(s) in hostname -- replacing with '*'
Nmap scan report for RX-V677*B9772F.hsd1.ca.domain.net (10.168.243.179)
Host is up (0.029s latency).
Not shown: 995 closed ports
PORT      STATE SERVICE
80/tcp    open  http
|_clamav-exec: ERROR: Script execution failed (use -d to debug)
| http-csrf:
| Spidering limited to: maxdepth=3; maxpagecount=20; withinhost=RX-V677*B9772F.hsd1.ca.domain.net
|   Found the following possible CSRF vulnerabilities:
|
|     Path: http://RX-V677*B9772F.hsd1.ca.domain.net:80/
|     Form id: recoveryform
|_    Form action: /Config/avr_recovery.cgi
|_http-dombased-xss: Couldn't find any DOM based XSS.
| http-fileupload-exploiter:
|
|     Couldn't find a file-type field.
|
|     Couldn't find a file-type field.
|
|     Couldn't find a file-type field.
|
|     Couldn't find a file-type field.
|
|     Couldn't find a file-type field.
|
|     Couldn't find a file-type field.
|
|     Couldn't find a file-type field.
|
|     Failed to upload and execute a payload.
|
|     Failed to upload and execute a payload.
| 
|     Failed to upload and execute a payload.
|
|     Failed to upload and execute a payload.
|
|_    Failed to upload and execute a payload.
|_http-stored-xss: Couldn't find any stored XSS vulnerabilities.
1029/tcp  open  ms-lsa
|_clamav-exec: ERROR: Script execution failed (use -d to debug)
1900/tcp  open  upnp
|_clamav-exec: ERROR: Script execution failed (use -d to debug)
8080/tcp  open  http-proxy
|_clamav-exec: ERROR: Script execution failed (use -d to debug)
|_http-aspnet-debug: ERROR: Script execution failed (use -d to debug)
| http-enum:
|_  /test.html: Test page
| http-slowloris-check:
|   VULNERABLE:
|   Slowloris DOS attack
|     State: LIKELY VULNERABLE
|     IDs:  CVE:CVE-2007-6750
|       Slowloris tries to keep many connections to the target web server open and
        hold
|       them open as long as possible.  It accomplishes this by opening connections
        to
|       the target web server and sending a partial request. By doing so, it starves
|       the http server's resources causing Denial Of Service.
|
|     Disclosure date: 2009-09-17
|     References:
|       https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2007-6750
|_      http://ha.ckers.org/slowloris/
50000/tcp open  ibm-db2
|_clamav-exec: ERROR: Script execution failed (use -d to debug)

Nmap done: 1 IP address (1 host up) scanned in 130.29 seconds
```

&nbsp;

#   Protecting Applications

&nbsp;

An important step in protecting applications it to recognize the risks.  Before we talk about the potential risks, it is essential to understand some key terms and their relationships:

-   Hacker or attacker:  These terms are applied to the people who seek to exploit weaknesses in software and computer systems for gain.  The majority of the time, hackers have benign intentions and are simply motivated by curiosity; however, their actions may violate the intended use of the systems they are exploiting.  The results can range from mere mischief (such as creating a virus with no intentionally negative impact) to malicious activity (such as stealing or altering information).
-   Malicious code:  Malicious code is unwanted files or programs that can cause harm to a computer or compromise data stored on a computer.  Malicious code includes viruses, worms, and Trojan horses.

&nbsp;

##  Tiers of Securing and Protecting

&nbsp;

Enterprises depend on applications to run their businesses.  Apps not only help customers and partners connect with the enterprise, but a lot of times they enable employees to get their jobs done as well.  Unfortunately, applications remain one of the most commonly exploited threat vectors.  An enterprise needs to secure and protect web, mobile, and API applications form being compromised and preventing data breaches.  As mentioned earlier, application security is a framework that involves making applications more secure and, therefore, an end-to-end approach is needed.

&nbsp;

The multilayered software architecture is one of the most famous architectural patterns.  Figure 14-2 shows a simple three-tier application architecture that has the following foundations:

-   **Tier 1 (Presentation)**:  This tier presents content to the end user through a web user interface or a mobile app or via APIs.  To present the content, it is essential for this tier to interact with the other tiers.  From a security standpoint, it is very important that access be authorized, timed, and encrypted and that the attack surface be minimized.
-   **Tier 2 (Application)**:  This is the middle tier of the architecture, and it is where the business logic of the application runs.  The components of this tier typically run on one or more application servers; hence, from a security standpoint, load balancing, limiting access, and proxying help.
-   **Tier 3 (Data)**:  This is hte lowest tier of this architecture, and it is mainly concerned with the storage and retrieval of application data.  The application data is typically stored in a database server, a file server, or any other device or media that supports data access logic and provides the necessary steps to ensure that only the data is exposed, without providing any access to the data storage and retrieval mechanisms.

&nbsp;

**Figure 14-2** *Three-Tier Approach to Application Security*

![Figure 14-2 Three-Tier Approach to Application Security](assets/images/Figure%2014-2%20Three-Tier%20Approach%20to%20Application%20Security.jpeg)

&nbsp;

To minimize risks, the following are some of the best practices in the industry:

-   **Keep software up-to-date**:  Install software patches so that attackers cannot take advantage of known problems or vulnerabilities.  Many operating systems offer automatic updates.
-   **Install end-user or device security**:  Install endpoint security software on an end user's device so that viruses and malware are kept as far away as possible.
-   Use strong passwords:  Using a strong password ensures that only authorized users can access resources.  With strong passwords, it becomes hard to guess and hence decreases security risk.
-   **Implement multifactor authentication (MFA)**:  Authentication is a process used to validate a user's identity.  Attackers commonly exploit weak authentication processes.  MFA uses at least two identity components to authenticate a user's identity, maximizing the risk of a cyberattacker gaining access to an account by knowing the username and password.
-   **Install a firewall**:  Firewalls may be able to prevent some types of attack vectors by blocking malicious traffic before it can enter a computer system and by restricting unnecessary outbound communications.
-   **Encrypt data**:  Ensure that data cannot be accessed even if storage can be reached.

&nbsp;

##  Encryption Fundamentals

&nbsp;

Cryptography is the science of transmitting information securely against potential third-party adversaries.  The main objectives of cryptography are the following:

-   **Confidentiality**:  Guaranteeing that the information exchanged between two parties is confidential between them and is not visible to anyone else
-   **Integrity**:  Ensuring that the integrity of a message is not changed while the message is in transits
-   **Availability**:  Ensuring that systems are available to fulfill requests all the time

&nbsp;

Encryption is an operation that involves applying an encryption key to plaintext by using an encryption algorithm.  Encryption turns the plaintext into ciphertext.  Decryption is the inverse operation: The decryption key is applied to the ciphertext, and the result is the original plaintext.  Encryption and decryption both involve symmetric keys or public/private key pairs.

&nbsp;

##  Public Key Encryption

&nbsp;

Public key encryption is a method of encrypting data that involves a pair of keys known as a public key and a private key (or a public/private key pair).  The public key is usually published, and the corresponding private key is kept secret.  Data that is encrypted with the public key can be decrypted only with the corresponding private key.  Figure 14-3 illustrates a very simplified way to understand public key encryption.

&nbsp;

**Figure 14-3** *Simple Public Key Encryption*

![Figure 14-3 Simple Public Key Encryption](assets/images/Figure%2014-3%20Simple%20Public%20Key%20Encryption.jpeg)

&nbsp;

Public key encryption is used to establish secure communications over the Internet (via HTTPS).  A website's SSL/TLS certificate, which is shared publicly, contains the public key, and the private key is installed on the web server.

&nbsp;

A TLS handshake uses a public key to authenticate the identity of the origin server and to exchange data that is used for generating the session keys.  A key exchange algorithm, such as Rivest - Shamir - Adleman (RSA), uses the public/private key pair to agree on session keys, which are used for symmetric encryption when the handshake is complete.  Clients and servers can agree on new session keys for each communication session, so that bad actors are unable to decrypt communications even if they identify or steal one of the session keys.

&nbsp;

##  Data Integrity (One-Way Hash)

&nbsp;

As data and documents move across networks or storage devices, it is crucial to ensure that this data is identically maintained during any operation.

&nbsp;

In the case of data transfer, data flowing between applications in a public network environment can flow across many network elements, each of which can "see" the data.  Encryption ensures that even though these elements can see the data, they cannot understand the data.  But because the data can flow across nodes that you do not control, there is a risk that a node in the network could alter the data before it reaches the destination.

&nbsp;

You cannot prevent the data from being altered by someone on the network, so the receiving element (destination) must be able to detect whether data has been modified and, if so, not pass the corrupted data to the application.  A one-way hash is used for this purpose.  The message hash is a fingerprint of the data.  If the data changes, the finger print (that is, the message digest or hash) changes as well.  Someone who alters the data would have no idea what the corresponding digest will be for the modified data.  The content of the hashed data cannot be determined from the hash.  This is why it is called a *one-way* hash.

&nbsp;

##  Digital Signatures

&nbsp;

You can use a private key for encryption and your public key for decryption.  Rather than encrypting the data itself, you can create a one-way hash of the data and then use the private key to encrypt the hash.  The encrypted hash, along with other information, such as the hashing algorithm, is known as a *digital signature*.  Figure 14-4 illustrates the use of a digital signature to validate the integrity of signed data.  The data and the digital signature are sent across the network.  On the receiving end, two hashes are calculated: one from the received data and the other by decrypting the digital signature using the public key.  If the two hashes match, you know that the private and public keys match, and the identity of the sender is verified.

&nbsp;

**Figure 14-4** *Digitally Signed Data*

![Figure 14-4 Digitally Signed Data](assets/images/Figure%2014-4%20Digitally%20Signed%20Data.jpeg)

&nbsp;

##  Data Security

&nbsp;

Today, all our interactions with the world involve online systems in some way, and all these systems deal with data.  Data is typically an organization's most valuable asset, and it is very often sensitive.  Data security is the process of securing data and protecting it from unauthorized access.  As data traverses various points of interaction, it needs to be secured at all these various places.  Data needs to be protected in three places, as shown in figure 14-5:

-   Network (data in motion)
-   Storage (data at rest)
-   Memory (data in use)

&nbsp;

**Figure 14-5** *Data Security*

![Figure 14-5 Data Security](assets/images/Figure%2014-5%20Data%20Security.jpeg)

&nbsp;

>   ***`Key Topic`***

&nbsp;

Table 14-3 shows each of these types of security and describes some ways to secure or protect each type.

&nbsp;

**Table 14-3** Data Security Types

| Data Type | Description | Examples |
| -- | -- | -- |
| Data in motion (network) | Data travels across various networks and entities.  It is prone to be inspected, and data can be stolen.  <br>Transport Layer Security (TLS) is a widely adopted security protocol designed to facilitate privacy and data security for communication over the Internet.  A primary use case of TLS is encrypting the communication between web applications and servers, such as web browsers loading a website. | <ul><li>HTTPS <li>Firewalls</ul> |
| Data at rest (storage) | Any data that is stored can be accessed digitally or physically. <br>Encrypting data at rest protects it against physical theft of the file system storage devices, protecting against unauthorized access to data, and satisfies information security or regulatory requirements.  | <ul><li>Full disk encryption <li>File system encryption <li>Database encryption </ul> |
| Data in use (memory) | When a running application is processing data, the data is in memory (or in use)..  All open files are considered data in use by operating systems.  When an encrypted file is unencrypted in memory, it is vulnerable to being stolen, or "scraped." | <ul><li>Fully memory encryption<li>CPU-based key storage (keys stored in CPU registers)<li>Enclaves, which are guarded and secure memory segments</ul> |

&nbsp;

#   Secure Development Methods

&nbsp;

As mentioned earlier in this chapter, the application security process starts during the development phase.  Instead of trying to bring in security at the end of the development process, secure development needs to be baked in from the start.  Addressing security issues from the very beginning saves a company time and money in the long run.

&nbsp;

It is a common practice for corporations to use some type of **software development lifecycle (SDLC)**.  Best practices in secure software development suggest integrating security aspects into each phase of the SDLC.  Figure 14-6 show the various aspects of the SDLC.

&nbsp;

**Figure 14-6** *Secure Development*

![Figure 14-6 Secure Development](assets/images/Figure%2014-6%20Secure%20Development.jpeg)

&nbsp;

As you can see in the figure, the SDLC includes these steps:

-   **Training**:  Training helps get everyone on the project teams into a security frame of mind.  Teach and train developers on the team to analyze the business application attack surface as well as the associated potential threats.  Not just developers but all team members should understand the exposure points of their applications (user inputs, front-facing code, exposed function calls, and so on) and take steps to design more secure systems wherever possible.<br><br>
-   **Threat modeling**:  For every component and module in a system, ask the "what-how-what" questions: What can go wrong?  How can someone try to hack into it?  What can we do to prevent this from happening?  Various frameworks for threat modeling are available, including the following:
    -   STRIDE (Spoofing, Tampering, Repudiation, Information Leak, DoS, Elevation of Privilege)
    -   PASTA (Process for Attack Simulation and Threat Analysis)
    -   VAST (Visual, Agile, and Simple Threat Modeling)<br><br>
-   **Secure coding**:  Build and use code libraries that are already secured or approved by an official committee.  The industry has several guidelines for secure coding, and we have listed some of the standard ones here:
    -   Validating inputs
    -   Encoding output
    -   Ensuring authentication and credential management
    -   Managing sessions
    -   Using access control lists
    -   Monitoring error handling and logging
    -   Protecting data, including files, databases, and memory<br><br>
-   **Code review**:  Code review is one of the most essential steps in securing an application.  Usually, the rule that you have to keep in mind is that pen testing and other forms of testing should not be discovering new vulnerabilities.  Code review has to be a way to make sure that an application is self-defending.  Also, it should be conducted using a combination fo tools and human effort.  It is important to designate a security lead who can help review code from a security point of view.<br><br>
-   **Secure tooling**:  Static analysis helps catch vulnerabilities.  Static analysis tools detect errors or potential errors in the structure of a program and can be useful for documentation or understanding a program.  Static analysis is a very cost-effective way of discovering errors.  Data flow analysis is a form of static analysis that concentrates on the use of data by programs and detects some data flow anomalies.  <br><br>Dlint (see https://github.com/duo-labs/dlint) is a tool from Duo Labs (Cisco) that defines and checks for common best practices when it comes to writing secure Python.  To evaluate a variety of rules over a code base, Dlint leverages Flake8.  Flake8 does the heavy lifting of parsing Python's AST, allowing you to focus on writing robust rule sets.<br><br>
-   **Testing**:  Testing includes penetration (pen) testing and system testing, black box testing, and white box testing.  Black box testing is a method used to test software without knowing the internal structure of code or program.  Testing teams usually do this type of testing, and programming knowledge is not required.  Black box testing includes functional testing, behavior testing, and closed box testing.  White box testing, on the other hand, is a software testing method in which internal structure is known to the tester who is testing the software.  Generally, this type of testing is carried out by software developers.  Programming knowledge is usually required for white box testing.  White box testing includes structural testing, logic testing, path testing, loop testing, code coverage testing, and open box testing.<br>Testing involves the following steps:
    -   **Intelligence gathering**:  Define the goals, understand what's included in the application, and identify potential areas of vulnerabilities.
    -   **Scanning**:  Understanding both running and non-running behaviors.  Static analysis tools enable developers and testers to see faults without actually running an application.  These tools can save a lot of time and effort in the long run, and the more errors and defects found here, the better.  Dynamic analysis, on the other hand, involves actually running the application in a real or virtual environment.  Usually, a lot of external services and interactions are exercised here.
    -   **Access**:  Use various methods to try to hack the application, such as testing the app for SQL injection, back doors, traffic interception, and so on.  Long-term access testing looks at the kinds of vulnerabilities exposed when a system is exploited for a long time.<br><br>
-   **Reporting**:  Include all details on the vulnerabilities and sensitive data exposed, as well as the amount of time the system remained unhacked.

&nbsp;

##  Securing Network Devices

&nbsp;

Network devices are the components of a network that transport communications needed for data, applications, services, and multimedia.  These devices include routers, firewalls, switches, servers, load balancers, intrusion detection systems, Domain Name System servers, and storage area networks.  These devices are ideal targets for malicious actors because most or all organizational and customer traffic must pass through them.

&nbsp;

##  Firewalls

&nbsp;

A firewall is a barrier that's put in place to limit damage.  A firewall can be either hardware or software that's installed to limit damage from external and internal cyberattacks.  It monitors and controls network traffic based on a set of security rules.  Figure 14-7 shows how firewalls can monitor and control network traffica s it flows between a local-area network (LAN) and the Internet (WAN).

&nbsp;

>   ***`Key Topic`***

&nbsp;

**Figure 14-7** *Firewall*

![Figure 14-7 Firewall](assets/images/Figure%2014-7%20Firewall.jpeg)

&nbsp;

The primary function of all firewalls is to screen network traffic and prevent unauthorized access between two network entities.  There are several types of firewalls:

-   **Packet filtering firewalls**:  Individual packets are examined, although the firewall does not know the content of a packet.  These firewalls provide this security by filtering the packets of incoming traffic and distinguishing between TCP/UDP traffic and port numbers.  The packets are either allowed entry onto the network or denied access, based on either their source or destination address or some other static information such as the traffic type.  Figure 14-8 shows an example of a stateless firewall that has a very simple rule engine and shows which traffic is allowed and which is denied.

&nbsp;

**Figure 14-8** *Stateless Firewall (Packet Filtering)*

![Figure 14-8 Stateless Firewall (Packet Filtering)](assets/images/Figure%2014-8%20Stateless%20Firewall%20(Packet%20Filtering).jpeg)

&nbsp;

-   **Stateful inspections firewalls**:  Packets are examined with other packets in the flow.  Such firewalls monitor the state of active connections and use this information to determine which network packets to allow.  Stateful firewalls are advanced compared to stateless packet filtering firewalls.  They continuously keep track of the state of the network and the active connections it has, such as TCP streams or ***User Datagram Protocol (UDP)*** communication.  The ability to acknowledge and use the contents of incoming traffic and data packets is one of the principal advantages of stateful firewalls, as it enables these firewalls to tell the difference between legitimate and malicious traffic or packets.  This ultimately makes stateful firewalls one of the most powerful security tools in modern policies that protect network connections through the implementation of additional security procedures for new or ongoing/active links.  Figure 14-9 shows an example of a stateful firewall that keeps track of the data from User1 and allows it to flow to the email and web server.

&nbsp;

**Figure 14-9** *Stateful Firewall (Context Aware)*

![Figure 14-9 Stateful Firewall (Context Aware)](assets/images/Figure%2014-9%20Stateful%20Firewall%20(Context%20Aware).jpeg)

&nbsp;

-   **Application-level or proxy firewall**:  This type of firewall protects network resources by filtering messages at the application layer.  In addition to determining which traffic is allowed and which is denied, a proxy firewall uses stateful inspection and deep packet inspection to analyze incoming traffic for signs of attack.  The key benefit of application-layer filtering is the ability to block specific content, such as known malware or content from individual websites.  A proxy firewall can recognize when particular applications and protocols, such as Hypertext Transfer Protocol (HTTP), File Transfer Protocol (FTP), and Domain Name System (DNS), are being misused.  As the firewall sees incoming packets, it inspects each protocol in the stack, noting the various states.  At Layer 7 (the application layer), the firewall looks up the rules and applies them to incoming packets.  Based on the system rules, it may perform other functions, such as URL filtering, data modification, logging, and object caching.<br><br>

-   **Next-generation firewall**:  Some standard features of next-generation firewall architectures include deep-packet inspection (checking the actual contents of the data packet), TCP handshake checks, and surface-level packet inspection.  Next-generation firewalls may include other technologies as well, such as intrusion prevention to stop attacks against a network automatically.

&nbsp;

##  Intrusion Detection Systems (IDSs)

&nbsp;

**An intrusion detection system (IDS), as shown in Figure 14-10, is a passive system that monitors network traffic.**  The traffic in this case is a copy of the traffic as the network sees it.  In a typical network scenario, packets or flows are replicated in hardware and sent to the IDS.  the IDS processes the packets and detects malicious signatures.  In this case, the IDS cannot detect any suspicious activity in real time; it has to let a few packets pass before it can initiate any action.  An IDS usually has to rely on other networking elements, such as routers or switches, to take any corrective measures to stop suspicious traffic from passing through.  One of the most significant disadvantages of an IDS is that a single packet attack is almost always successful, which means it is hard to prevent these attacks.

&nbsp;

>   ***`Key Topic`***

&nbsp;

**Figure 14-10** *IDS Receiving a Copy of the Packets*

![Figure 14-10 IDS Receiving a Copy of the Packets](assets/images/Figure%2014-10%20IDS%20Receiving%20a%20Copy%20of%20the%20Packets.jpeg)

&nbsp;

##  Intrusion Prevention Systems (IPSs)

&nbsp;

***An intrusion prevention system, as shown in Figure 14-11, works in real time and in an inline manner.  Usually, an IPS is collocated with a network element such as a router or switch.  Like an IDS, an IPS does deep-packet inspection of packets; however an IPS takes action immediately if it determines that a packet is vulnerable.***  Therefore, only trusted packets are allowed into the enterprise network.

&nbsp;

>   ***`Key Topic`***

&nbsp;

**Figure 14-11** *IPS Inline with Traffic*

![Figure 14-11 IPS Inline with Traffic](assets/images/Figure%2014-11%20IPS%20Inline%20with%20Traffic.jpeg)

&nbsp;

##  Domain Name System (DNS)

&nbsp;

You probably don't remember a lot of phone numbers but instead record them in your contacts so that you can look up a name of a person you want to call.  Domain Name system works quite similarly:  It keeps a mapping of domain names and the IP addresses of the servers where the domains can be reached.  Each device on the Internet has a unique IP address, and DNS eliminates the need to memorize any IP addresses that it uses.  Figure 14-12 shows how a client request gets to the DNS resolver, which in turn gets to the primary DNS server.

&nbsp;

>   ***`Key Topic`***

&nbsp;

**Figure 14-12** *DNS Operation*

![Figure 14-12 DNS Operation](assets/images/Figure%2014-12%20DNS%20Operation.jpeg)

&nbsp;

To understand how DNs works, the following steps walk through how a client, such as a web browser, asks for a new website:

-   **Step 1.**  The user clicks on a link or types a URL for a site to visit (for example, https://developer.cisco.com).
-   **Step 2.**  The browser looks in the local cache to see if the name can be resolved locally on the client.
-   **Step 3.**  The browser sends a query to the DNS recursive resolver in an attempt to resolve the name.  The DNS recursive resolver usually rides with the Internet service provider, and it can reply if it has the IP address or pass on the query to the next resolve in the chain.  (There are public name resolvers, such as Cisco Umbrella and Google.)  Eventually, one of the resolvers may respond with the IP address.
-   **Step 4.**  If the DNs resolvers cannot find the IP address, the browser tries the root name servers, which in turn forward the query to top-level domain (TLD) servers and eventually authoritative servers, until results are achieved.
-   **Step 5.**  When the client has the IP address for the domain, it gives the IP address to the browser.

&nbsp;

***Nslookup (Name Server Lookup)*** is an excellent utility that most operating systems can use to get details about a particular host or domain from a DNS server.  The syntax for the command is as follows:

`nslookup [-option] [name | -] [server]`

&nbsp;

Example 14-4 and 14-5 show examples of using Nslookup.

&nbsp;

**Example 14-4** *Using Nslookup for a **Simple Host Lookup***

```
nslookup stanford.edu :
nslookup with a simple domain name will return the IP address of the stanford.edu

$ nslookup standford.edu
Server: 2601:647:5500:1ea:9610:3eff:fe18:22a5
Address: 2601:647:5500:1ea:9610:3eff:fe18:22a5#53

** server can't find standford.edu: NXDOMAIN

$ nslookup stanford.edu
Server: 2601:647:5500:1ea:9610:3eff:fe18:22a5
Address: 2601:647:5500:1ea:9610:3eff:fe18:22a5#53

Non-authoritative answer:
Name: stanford.edu
Address: 171.67.215.200
```

&nbsp;

**Example 14-5** *Using Nslookup to Get Information About a Domain*

```
nslookup -type=any stanford.edu :
The -type=any parameter allows us to get all the DNS records for that domain,
including the mail servers, etc.

$ nslookup -type=any stanford.edu
;; Truncated, retrying in TCP mode.
Server: 10.168.243.90
Address: 10.168.243.90#53

Non-authoritative answer:
stanford.edu mail exchanger = 10 mxa-00000d03.gslb.pphosted.com.
stanford.edu mail exchanger = 10 mxb-00000d03.gslb.pphosted.com.
stanford.edu nameserver = ns5.dnsmadeeasy.com.
stanford.edu nameserver = ns6.dnsmadeeasy.com.
stanford.edu nameserver = ns7.dnsmadeeasy.com.
stanford.edu nameserver = argus.stanford.edu.
stanford.edu nameserver = atalante.stanford.edu.
stanford.edu nameserver = avallone.stanford.edu.
stanford.edu
 origin = argus.stanford.edu
 mail addr = hostmaster.stanford.edu
 serial = 2019138199
 refresh = 1200
 retry = 600
 expire = 1296000
 minimum = 1800
 ```

 &nbsp;

 ## Load Balancing

 &nbsp;

** Load balancing is the process of distributing user requests across multiple servers.**  The goal is to ensure that no single server bears too much demand.  In essence, load balancers are like virtual servers, receiving all user requests and forwarding these requests based on the load balancer's policy to one of the servers that host the website.  The load balancer attempts to ensure that each server receives a similar number of requests.  Many load balancers are capable of monitoring servers and compensating for any servers that become unavailable.  By spreading the work evenly, load balancing improves application responsiveness.

&nbsp;

**Figure 14-13** *Load Balancing*

![Figure 14-13 Load Balancing](assets/images/Figure%2014-13%20Load%20Balancing.jpeg)

&nbsp;

Load balancing uses algorithms such as the following:

-   **Round-robin**:  Selects server in turn
-   **Least connected**:  Selects the server with the lowest number of connections; this is recommended for more extended sessions
-   **Source/IP-hash**:  Choose a server based on a hash of the source IP
-   **Cookie marking**:  Adds a field in the HTTP cookies, which could be used for decision marking
-   **Consistent IP-hash**:  Adds and removes servers without alarming cached items or session persistence

&nbsp;

A reverse proxy accepts a request from a user, forwards it to a server that can fulfill it, and returns the server's response to the client.  A reverse proxy can include some or all of the following functionality:

&nbsp;

>   ***`Key Topic`***

&nbsp;

-   **Security**:  The web server or application servers are not visible from the external network, so malicious clients cannot access them directly to exploit any vulnerabilities.  Many reverse proxy servers include features that help protect backend servers from distributed denial-of-service (DDoS) attacks - for example, by rejecting traffic from particular client IP addresses (blacklisting) or limiting the number of connections accepted from each client.
-   **Scalability and flexibility**:  Clients see only the reverse proxy's IP address.  This is particularly useful in a load-balancing environment, where you can scale the number of servers up and down to match fluctuations in traffic volume.
-   **Web acceleration**:  Acceleration in this case means reducing the time it takes to generate a response and return it to the client.  Some of the techniques for web acceleration include the following:
    -   **Compression**:  Compressing server responses before returning them to the client (for instance, with gzip) reduces the amount of bandwidth they require, which speeds their transit over the network.
    -   **SSL termination**:  Encrypting the traffic between clients and servers protects it as it crosses a public network such as the Internet.  However, decryption and encryption can be computationally expensive.  By decrypting incoming requests and encrypting server responses, the reverse proxy frees up resources on backend servers, which the servers can then devote to their primary purpose - serving the content.
    -   **Caching**:  Before returning the backend server's response to the client, the reverse proxy stores a copy of it locally.  When the client (or any other client) makes the same request, the reverse proxy can provide the response itself rom the cache instead of forwarding the request to the backend server.  This both decreases the response time to the client and reduces the lod on the backend server.  This works great for "static" content, but there are new techniques that can be used for "dynamic" content as well.
-   **Content filtering**:  This involves monitoring traffic to and from the web server for potentially sensitive or inappropriate data and taking action as necessary.
-   **Authentication**:  The reverse proxy authenticates users via a variety of mechanisms and controls access to URLs hosted on the web server.

&nbsp;

Figure 14-14 shows how requests come in from various clients.  The reverse proxy can terminate an SSL connection or even inspect incoming traffic.

&nbsp;

**Figure 14-14** *Reverse Proxy*

![Figure 14-14 Reverse Proxy](assets/images/Figure%2014-14%20Reverse%20Proxy.jpeg)

&nbsp;

Figure 14-15 illustrates the concept of a reverse proxy with a user requesting a web page from ht<span>tps://server.com.  In this case, server.com is the reverse proxy, which first terminates SSL and then translates the request and issues a new request, gathering and translating the response and sending it back to the client.  Translation could mean applying compression (gzip) to the response).

&nbsp;

**Figure 14-15** *Reverse Proxy Flow Diagram*

![Figure 14-15 Reverse Proxy Flow Diagram](assets/images/Figure%2014-15%20Reverse%20Proxy%20Flow%20Diagram.jpeg)