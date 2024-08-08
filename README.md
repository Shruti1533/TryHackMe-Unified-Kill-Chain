# TryHackMe-Unified-Kill-Chain

# Unified Kill Chain Framework: A Comprehensive Guide

## Task 1: Introduction
In this room, you will be introduced to the UKC (Unified Kill Chain) framework that is used to help understand how cyber attacks occur.

### Learning Objectives:
- Understanding why frameworks such as the UKC are important and helpful in establishing a good cybersecurity posture
- Using the UKC to understand an attacker’s motivation, methodologies, and tactics
- Understanding the various phases of the UKC
- Discover that the UKC is a framework that is used to complement other frameworks such as MITRE.

## Task 2: What is a “Kill Chain”
Originating from the military, a “Kill Chain” is a term used to explain the various stages of an attack. In the realm of cybersecurity, a “Kill Chain” is used to describe the methodology/path attackers such as hackers or APTs use to approach and intrude a target.

For example, an attacker scanning, exploiting a web vulnerability, and escalating privileges will be a “Kill Chain”. We will come to explain these stages in much further detail later in this room.

The objective is to understand an attacker’s “Kill Chain” so that defensive measures can be put in place to either pre-emptively protect a system or disrupt an attacker’s attempt.

### Question:
Where does the term “Kill Chain” originate from?

**Answer:** The military

## Task 3: What is “Threat Modelling”
Threat modelling, in a cybersecurity context, is a series of steps to ultimately improve the security of a system. Threat modelling is about identifying risk and essentially boils down to:
- Identifying what systems and applications need to be secured and what function they serve in the environment. For example, is the system critical to normal operations, and is a system holding sensitive information like payment info or addresses?
- Assessing what vulnerabilities and weaknesses these systems and applications may have and how they could be potentially exploited
- Creating a plan of action to secure these systems and applications from the vulnerabilities highlighted
- Putting in policies to prevent these vulnerabilities from occurring again where possible (for example, implementing a software development life cycle (SDLC) for an application or training employees on phishing awareness).

Threat modelling is an important procedure in reducing the risk within a system or application, as it creates a high-level overview of an organisation’s IT assets (an asset in IT is a piece of software or hardware) and the procedures to resolve vulnerabilities.

**Frameworks used in Threat Modelling:**
- **STRIDE:** Spoofing, Tampering, Repudiation, Information disclosure, Denial of service, and Elevation of privilege
- **DREAD:** Damage, Reproducibility, Exploitability, Affected users, and Discoverability
- **CVSS:** Common Vulnerability Scoring System

### Question:
What is the technical term for a piece of software or hardware in IT (Information Technology)?

**Answer:** Asset

## Task 4: Introducing the Unified Kill Chain
The Unified Kill Chain published in 2017 aims to complement (not compete) with other cybersecurity kill chain frameworks such as Lockheed Martin’s and MITRE’s ATT&CK.

The UKC states that there are 18 phases to an attack: Everything from reconnaissance to data exfiltration and understanding an attacker’s motive. These phases have been grouped together in this room into a few areas of focus for brevity, which will be detailed in the remaining tasks.

Some large benefits of the UKC over traditional cybersecurity kill chain frameworks include the fact that it is modern and extremely detailed (reminder: it has 18 phases officially, whereas other frameworks may have a small handful).

### Questions:
1. **In what year was the Unified Kill Chain framework released?**
   - **Answer:** 2017
2. **According to the Unified Kill Chain, how many phases are there to an attack?**
   - **Answer:** 18
3. **What is the name of the attack phase where an attacker employs techniques to evade detection?**
   - **Answer:** Defense Evasion
4. **What is the name of the attack phase where an attacker employs techniques to remove data from a network?**
   - **Answer:** Exfiltration
5. **What is the name of the attack phase where an attacker achieves their objectives?**
   - **Answer:** Objectives

## Task 5: Phase: In (Initial Foothold)
The main focus of this series of phases is for an attacker to gain access to a system or networked environment.

An attacker will employ numerous tactics to investigate the system for potential vulnerabilities that can be exploited to gain a foothold in the system. For example, a common tactic is the use of reconnaissance against a system to discover potential attack vectors (such as applications and services).

This series of phases also accommodates for an attacker creating a form of persistence (such as files or a process that allows the attacker to connect to the machine at any time). Finally, the UKC accounts for the fact that attackers will often use a combination of the tactics listed above.

### Reconnaissance (MITRE Tactic TA0043)
This phase of the UKC describes techniques that an adversary employs to gather information relating to their target. This can be achieved through means of passive and active reconnaissance. The information gathered during this phase is used all throughout the later stages of the UKC (such as the initial foothold).

**Information gathered from this phase can include:**
- Discovering what systems and services are running on the target, this is beneficial information in the weaponisation and exploitation phases of this section.
- Finding contact lists or lists of employees that can be impersonated or used in either a social engineering or phishing attack.
- Looking for potential credentials that may be of use in later stages, such as pivoting or initial access.
- Understanding the network topology and other networked systems can be used to pivot too.

### Weaponization (MITRE Tactic TA0001)
This phase of the UKC describes the adversary setting up the necessary infrastructure to perform the attack. For example, this could be setting up a command and control server, or a system capable of catching reverse shells and delivering payloads to the system.

### Social Engineering (MITRE Tactic TA0001)
This phase of the UKC describes techniques that an adversary can employ to manipulate employees to perform actions that will aid in the adversaries attack. For example, a social engineering attack could include:
- Getting a user to open a malicious attachment.
- Impersonating a web page and having the user enter their credentials.
- Calling or visiting the target and impersonating a user (for example, requesting a password reset) or being able to gain access to areas of a site that the attacker would not previously be capable of (for example, impersonating a utility engineer).

### Exploitation (MITRE Tactic TA0002)
This phase of the UKC describes how an attacker takes advantage of weaknesses or vulnerabilities present in a system. The UKC defines “Exploitation” as abuse of vulnerabilities to perform code execution. For example:
- Uploading and executing a reverse shell to a web application.
- Interfering with an automated script on the system to execute code.
- Abusing a web application vulnerability to execute code on the system it is running on.

### Persistence (MITRE Tactic TA0003)
This phase of the UKC is rather short and simple. Specifically, this phase of the UKC describes the techniques an adversary uses to maintain access to a system they have gained an initial foothold on. For example:
- Creating a service on the target system that will allow the attacker to regain access.
- Adding the target system to a Command & Control server where commands can be executed remotely at any time.
- Leaving other forms of backdoors that execute when a certain action occurs on the system (i.e. a reverse shell will execute when a system administrator logs in).

### Defence Evasion (MITRE Tactic TA0005)
The “Defence Evasion” section of the UKC is one of the more valuable phases of the UKC. This phase specifically is used to understand the techniques an adversary uses to evade defensive measures put in place in the system or network. For example, this could be:
- Web application firewalls.
- Network firewalls.
- Anti-virus systems on the target machine.
- Intrusion detection systems.

This phase is valuable when analysing an attack as it helps form a response and better yet — gives the defensive team information on how they can improve their defence systems in the future.

### Questions:
1. **What is an example of a tactic to gain a foothold using emails?**
   - **Answer:** Phishing
2. **Impersonating an employee to request a password reset is a form of what?**
   - **Answer:** Social Engineering
3. **An adversary setting up the Command & Control server infrastructure is what phase of the Unified Kill Chain?**
   - **Answer:** Weaponization
4. **Exploiting a vulnerability present on a system is what phase of the Unified Kill Chain?**
   - **Answer:** Exploitation
5. **Moving from one system to another is an example of?**
   - **Answer:** Pivoting
6. **Leaving behind a malicious service that allows the adversary to log back into the target is what?**
   - **Answer:** Persistence

## Task 6: Phase: Through (Network Propagation)
This phase follows a successful foothold being established on the target network. An attacker would seek to gain additional access and privileges to systems and data to fulfil their goals. The attacker would set up a base on one of the systems to act as their pivot point and use it to gather information about the internal network.

### Pivoting (MITRE Tactic TA0008)
Once the attacker has access to the system, they would use it as their staging site and a tunnel between their command operations and the victim’s network. The system would also be used as the distribution point for all malware and backdoors at later stages.

### Discovery (MITRE Tactic TA0007)
The adversary would uncover information about the system and the network it is connected to. Within this stage, the knowledge base would be built from the active user accounts, the permissions granted, applications and software in use, web browser activity, files, directories and network shares, and system configurations.

### Privilege Escalation (MITRE Tactic TA0004)
Following their knowledge-gathering, the adversary would try to gain more prominent permissions within the pivot system. They would leverage the information on the accounts present with vulnerabilities and misconfigurations found to elevate their access to one of the following superior levels:
- SYSTEM/ ROOT.
- Local Administrator.
- A user account with Admin-like access.
- A user account with specific access or functions.

### Execution (MITRE Tactic TA0002)
This is where they deploy their malicious code using the pivot system as their host. Remote trojans, C2 scripts, malicious links, and scheduled tasks are deployed and created to facilitate a recurring presence on the system and uphold their persistence.

### Credential Access (MITRE Tactic TA0006)
Working hand in hand with the Privilege Escalation stage, the adversary would attempt to steal account names and passwords through various methods, including keylogging and credential dumping. This makes them harder to detect during their attack as they would be using legitimate credentials.

### Lateral Movement (MITRE Tactic TA0008)
With the credentials and elevated privileges, the adversary would seek to move through the network and jump onto other targeted systems to achieve their primary objective. The stealthier the technique used, the better.

### Questions:
1. **As a SOC analyst, you pick up numerous alerts pointing to failed login attempts from an administrator account. What stage of the kill chain would an attacker be seeking to achieve?**
   - **Answer:** Privilege Escalation
2. **Mimikatz, a known attack tool, was detected running on the IT Manager’s computer. What is the mission of the tool?**
   - **Answer:** Credential dumping

## Task 7: Phase: Out (Action on Objectives)
This phase wraps up the journey of an adversary’s attack on an environment, where they have critical asset access and can fulfil their attack goals. These goals are usually geared toward compromising the confidentiality, integrity, and availability (CIA) triad.

The tactics to be deployed by an attacker would include:

### Collection (MITRE Tactic TA0009)
After all the hunting for access and assets, the adversary will be seeking to gather all the valuable data of interest. This, in turn, compromises the confidentiality of the data and would lead to the next attack stage — Exfiltration. The main target sources include drives, browsers, audio, video, and email.

### Exfiltration (MITRE Tactic TA0010)
To elevate their compromise, the adversary would seek to steal data, which would be packaged using encryption measures and compression to avoid any detection. The C2 channel and tunnel deployed in the earlier phases will come in handy during this process.

### Impact (MITRE Tactic TA0040)
If the adversary seeks to compromise the integrity and availability of the data assets, they would manipulate, interrupt, or destroy these assets. The goal would be to disrupt business and operational processes and may involve removing account access, disk wipes, and data encryption such as ransomware, defacement, and denial of service (DoS) attacks.

### Objectives
With all the power and access to the systems and network, the adversary would seek to achieve their strategic goal for the attack.

For example, if the attack was financially motivated, they may seek to encrypt files and systems with ransomware and ask for payment to release the data. In other instances, the attacker may seek to damage the reputation of the business, and they would release private and confidential information to the public.

### Questions:
1. **While monitoring the network as a SOC analyst, you realise that there is a spike in the network activity, and all the traffic is outbound to an unknown IP address. What stage could describe this activity?**
   - **Answer:** Exfiltration
2. **Personally identifiable information (PII) has been released to the public by an adversary, and your organisation is facing scrutiny for the breach. What part of the CIA triad would be affected by this action?**
   - **Answer:** Confidentiality

## Task 8: Practical
Match the scenario prompt to the correct phase of the Unified Kill Chain to reveal the flag at the end. What is the flag?
![Q1](https://github.com/Shruti1533/TryHackMe-Unified-Kill-Chain/blob/main/kill%20chain%20q1.png)
![Q2](https://github.com/Shruti1533/TryHackMe-Unified-Kill-Chain/blob/main/image2.png)
![Q3](https://github.com/Shruti1533/TryHackMe-Unified-Kill-Chain/blob/main/image3.png)
![Q4](https://github.com/Shruti1533/TryHackMe-Unified-Kill-Chain/blob/main/image4.png)
![Q5](https://github.com/Shruti1533/TryHackMe-Unified-Kill-Chain/blob/main/image5.png)

**Flag:** THM{UKC_SCENARIO}
