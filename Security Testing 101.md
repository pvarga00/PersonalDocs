Security Testing 101

This space is reachable from: http://shorty/Sec101 

[Secure Coding Standards](https://confluence/display/QAPOW/Secure+Coding+Standards)
[Security Code Reviews](https://confluence/display/QAPOW/Security+Code+Reviews)
 

## What is Security?
Security is set of measures to protect an application against unforeseen actions that cause it to stop functioning or being exploited. Unforeseen actions can be either intentional or unintentional.

## What is Security testing?
Security Testing is a variant of Software Testing which ensures, that system and applications in an organization, are free from any loopholes that may cause a big loss. Security testing of any system is about finding all possible loopholes and weaknesses of the system which might result into a loss of information at the hands of the employees or outsiders of the Organization.

The goal of security testing is to identify the threats in the system and measure its potential vulnerabilities. It also helps in detecting all possible security risks in the system and help developers in fixing these problems through coding.

## What is Hacking?
Hacking refers to exploiting system vulnerabilities and compromising security controls to gain unauthorized or inappropriate access to the system resources.

It involves modifying system or application features to achieve a goal outside of the creator's original purpose.

Hacking can be used to steal, pilfer, or redistribute intellectual property or data, leading to business loss.

GUMP: Breaking systems to do bad things.

 
## Ethical Hacking
Ethical hacking involves the use of hacking tools, tricks, and techniques to identify vulnerabilities so as to ensure system security

It focuses on simulating techniques used by attackers to verify the existence of exploitable vulnerabilities in the system security

Ethical hackers perform security assessments of their organization, with the permission of concerned authorities

 
## Why Ethical Hacking is Necessary
To beat a hacker, you need to think like one. By performing basic security checks, we can anticipate methods used to break into our systems first, allowing us to better/improve:
- Uncover vulnerabilities in systems and explore their potential risks
- Prevent hackers from gaining access to our organization's information, data, and systems (by finding the security holes first, and then plugging them)
- Analyze and strengthen our organization's security posture, including: policies, protection infrastructure, and end-user practices
 

## Things to Consider / Answer:
What can an  intruder see on the system? (Reconnaissance + Scanning)
What can an intruder do with that information? (Gaining Access + Maintaining access)
Does anyone at the target notice the intruder's attempts or successes? (Reconnaissance + Covering Tracks)
Are all the components of information systems are adequately protected, updated, and patched
How much time effort, and money is required to obtain adequate protection?
Are the information security measures in compliance to industry and legal standards?
 

## Elements of Information Security:
Information security is a state of well-being of information and infrastructure in which the possibility of theft, tampering, and disruption of information and services is kept low or tolerable:
- Confidentiality: Assurance that the information is accessible only to those authorized to have access
- Integrity: The trustworthiness of data in terms of preventing improper and unauthorized changes
- Availability: Assurance that the system responsible for delivering, storing, and processing information are accessible when required by the authorized users
- Authenticity: Authenticity refers to characteristic of a communication, document, or any data that ensures that quality of being genuine
- Non-Repudation: Guarantee that the sender of a message cannot later deny having sent the message and that the recipient cannot deny having received the message


## Types of Security Testing:
There are seven main types of security testing as per Open Source Security Testing methodology manual. They are explained as follows:
- Vulnerability Scanning: This is done through automated software to scan a system against known vulnerability signatures.
- Security Scanning: It involves identifying network and system weaknesses, and later provides solutions for reducing these risks. This scanning can be performed for both Manual and Automated scanning.
- Penetration testing: This kind of testing simulates an attack from a malicious hacker. This testing involves analysis of a particular system to check for potential vulnerabilities to an external hacking attempt.
- Risk Assessment:This testing involves analysis of security risks observed in the organization. Risks are classified as  Low, Medium and High. This testing recommends controls and measures to reduce the risk.
- Security Auditing: This is an internal inspection of Applications and Operating systems for security flaws. Audit can also be done via line by line inspection of code
- Ethical hacking: It's hacking an Organization Software systems. Unlike malicious hackers ,who steal for their own gains , the intent is to expose security flaws in  the system.
- Posture Assessment: This combines Security scanning, Ethical Hacking and Risk Assessments to show an overall security posture of an organization.


## Integration of security processes with the SDLC:
It is always agreed, that cost will be more, if we postpone security testing after software implementation phase or after deployment. So, it is necessary to involve security testing in SDLC life cycle in the earlier phases.

Let's look into the corresponding Security processes to be adopted for every phase in SDLC

![Security in SDLC]() 


| Agile SDLC Phases 	| Security Hardening Processes 	|  	|
|---	|---	|---	|
| Requirements Gathering 	| Security analysis for requirements and check abuse/misuse cases 	|  	|
| Design 	| Security risks analysis for designing. Development of test plan including security tests 	|  	|
| Coding and Unit Testing 	| Static and Dynamic Testing and Security white box testing 	|  	|
| Integration + System Testing 	| Black Box Testing and Vulnerability scanning 	|  	|
| Implementation System Testing + Hardening 	| Penetration Testing, Vulnerability Scanning 	|  	|
| Iterative + Continuing Support 	| Impact analysis of Patches 	|  	|
 

## Security Test Plans should include:
- Security related test cases or scenarios
- Test Data related to security testing
- Test Tools required for security testing
- Analysis on various tests outputs from different security tools

## Sample Test Scenarios for Security Testing:
Sample Test scenarios to give you a glimpse of security test cases:
- Password should be in encrypted format
- Application or System should not allow invalid users
- Check cookies and session time for application
- For financial sites, Browser back button should not work.

## Methodologies
In security testing, different methodologies are followed, and they are as follows:
- Tiger Box: This hacking is usually done on a laptop which has a collection of OSs and hacking tools. This testing helps penetration testers and security testers to conduct vulnerabilities assessment and attacks.
- [Black Box](http://www.guru99.com/black-box-testing.html): Tester is authorized to do testing on everything about the network topology and the technology.
- Grey Box: Partial information is given to the tester about the system, and it is a hybrid of white and black box models.

## Roles you should know:
Hackers - Access computer system or network without authorization
Crackers - Break into the systems to steal or destroy data
Ethical Hacker - Performs most of the breaking activities but with permission from owner
Script Kiddies or packet monkeys - Inexperienced Hackers with programming language skill
 

## Here is some stuff to do / try:
- View the source code.  (View Source + F12 Developer Tools + FireBug ) 
 - Do you see anything interesting? 
 - Any linked files in the source code? 
 - Any robots files? 
 - Any obfuscated or encoded text?
 - What language is used (PHP, ASP, JS, etc.)
- Decode or decrypt text. (MD5, SHA1, Base64, ROT13) 
- Look for clear text test credentials.
- Can any GET or POST variables be manipulated? 
 - ‘ single quote into login fields. If there is an error, the site is vulnerable. If there is no error, the input may not be vulnerable. Keep trying different stuff! 
  - SQLi Example: into any text field, URL, dropdown, hidden fields, etc.
   - ' (single quote)
   - ‘OR 1=1# 
   - (you can also then manipulate tables: join, drop, etc)
  - XSS Example: into any field: 
   - <script>alert('hi');</script>
   - <script>alert(1)<script>
   - <script>alert("xss")<script>
- Pay attention to text echos (for XSS opportunities)
 - Ex: Usernames, Error messages, other parameters
 - Test field validation with special characters (bad data): ' " < > ) 
  - Here is a great list of "naughty" strings: https://github.com/minimaxir/big-list-of-naughty-strings
- Manipulate the URLs, IPs, and query string parameters
- File upload/download issues (try different than expected formats)
 - Upload a javascript/PHP file

 

## Good Videos:
- Thinking like an attacker slides: https://youtu.be/htE7NvFMbpU
- CMD+CTRL Site walkthrough: https://youtu.be/2OkUr_ANZQE


## Exploiting! (Using your evil streak)
- Gather Info (PII/PIFI, Login Credentials)
- Deplete Resources
- Inject/Execute Malicious Code
- Deceive Interactions
- Manipulate Timing/State
- Abuse Functionality
- Exploit Authentication/Authorization
- Manipulate Data Structures / Resources
- Gain Physical Access
- Alter System Components
- Manipulate System Users


## Attack Vectors:
- Injection: XSS, SQLi, XML
- Authentication/Authorization
- Path Traversal
- File Upload/Download
- Cryptanalysis
- Document Manipulation
- Forceful browsing
- Password cracking


## Useful Reference Info: 
- CORE Helper Apps:
 - [Authorizer](https://confluence/display/CORE/Core+Authorizer)
 - [QKS](https://confluence/display/CORE/QKS+-+Quicken+Key+Service)
- Local file inclusion: LFI attacks can enumerate files that exist on a web server and could be used to inject code in to log files to execute PHP.
 - https://www.owasp.org/index.php/Testing_for_Local_File_Inclusion
 - http://hakipedia.com/index.php/Local_File_Inclusion
- Remote file inclusion: RFI attacks can open files from remote websites to run arbitrary code: https://www.owasp.org/index.php/Testing_for_Remote_File_Inclusion
- XSS reference: http://brutelogic.com.br/blog/cheat-sheet/
- SQL injection:
 - https://www.checkmarx.com/knowledge/knowledgebase/SQLi 
 - http://pentestmonkey.net/cheat-sheet/sql-injection/mysql-sql-injection-cheat-sheet
 - http://breakthesecurity.cysecurity.org/2010/12/hacking-website-using-sql-injection-step-by-step-guide.html 
 - https://blog.udemy.com/sql-injection-tutorial/ 
- [R7 SQL_Injection_Cheat_Sheet.v1.pdf](https://confluence/download/attachments/54739762/R7%20SQL_Injection_Cheat_Sheet.v1.pdf?version=1&modificationDate=1476801448000&api=v2)

## Fun Security Stuff
- Security Code Reviews (Guidance) : [OWASP_Code_Review_Guide-V1_1.pdf](https://confluence/download/attachments/45243748/OWASP_Code_Review_Guide-V1_1.pdf?version=1&modificationDate=1455126590000&api=v2)
- Security Attack Tables (Guidance): [SecurityAttackTables.pdf](https://confluence/download/attachments/45243748/SecurityAttackTables.pdf?version=1&modificationDate=1472843328000&api=v2)
- Security Cheat Sheet (Guidance): [SecurityCheatSheet.pdf](https://confluence/download/attachments/45243748/SecurityCheatSheet.pdf?version=1&modificationDate=1472843350000&api=v2)
- XSS Filter Evasion Cheat Sheet (OWASP): https://www.owasp.org/index.php/XSS_Filter_Evasion_Cheat_Sheet
- Red Team Field Manual (RTFM): [rtfm-red-team-field-manual.pdf](https://confluence/download/attachments/201857736/rtfm-red-team-field-manual.pdf?version=1&modificationDate=1581612306000&api=v2)
- Quality gates: Quality Gates: [Security Testing](https://confluence/display/RKTFUELArchive/Quality+Gates%3A+Security+Testing)
- Learning Hacking: https://www.codebashing.com/
- Learning Threat Modeling: https://dojo.ministryoftesting.com/lessons/threat-modeling


## More Learning Games:
- https://cryptopals.com/ 
- http://overthewire.org/wargames/bandit/ (Capture The Flag games)
- https://www.browserling.com/tools 
- https://www.hackthissite.org/missions/


## Useful browser plugins for Firefox (preferred browser for pen testing):
- Tamper Data – Used to intercept and modify web browser requests.
- Firebug – For looking at source code.
- User Agent Overrider
- Cookies Manager+ - Used to manage cookies. Useful if you want to change your PHPSESSID value.

## Useful sites:
- http://jsbeautifier.org/ - Helps clean up JS and sometimes deobfuscates it.
- http://jsunpack.jeek.org/ - Another way to deobfuscate JS.
- http://www.asciitohex.com/ - Good for text conversion and decoding.
- https://hashkiller.co.uk/ - MD5 and SHA1 hash cracking.
- https://leakdb.abusix.com/ - LeakDB
- https://github.com/hashcat/hashcat - hashcat
- [Docker Image for Damn Vulnerable Web App (DVWA) - For practicing hacking](https://github.com/infoslack/docker-dvwa)
- http://www.guru99.com/what-is-security-testing.html


## Other Stuff:
- https://www.defcon.org/
- http://testphp.acunetix.com/artists.php 
- http://sechow.com/bricks/index.html 
- https://www.checkmarx.com/2015/04/16/15-vulnerable-sites-to-legally-practice-your-hacking-skills/ 
- https://www.wireshark.org/ 
