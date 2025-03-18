# Keylogger Project for Cybersecurity

## Introduction
This report documents a controlled cybersecurity experiment designed to demonstrate the exploitation of human error and inadequate security measures. The experiment centered on deploying a custom-built keylogger disguised as a calculator application on a Windows 10 (version 1507) system. Through this analysis, we examine the vulnerabilities exploited, attack methodology, and essential risk mitigation strategies.

## Objectives
The experiment focused on three primary objectives:
- Demonstrating human error exploitation in a controlled environment
- Analyzing deployment and activation methods of malicious software
- Developing comprehensive recommendations for attack prevention

---

# Vulnerability Analysis

## Introduction
As organizations increasingly rely on digital communication, the risk of cyberattacks has escalated. Email remains a primary vector for cybercriminals, who exploit human psychology to trick users into executing malicious files or divulging sensitive information. This report examines several vulnerabilities that can arise from email-based social engineering, including the execution of unsigned software, lack of endpoint protection, and the consequences of excessive user privileges.

## Vulnerabilities Involved

### 1. Email-Based Social Engineering

**Vulnerability:** Execution of Malicious Files Delivered via Email  
**Root Cause:** Lack of Proper Email Filtering, Awareness, or Endpoint Protection  
**Fixes:**  
- Implement robust email security solutions (spam filters, attachment scanning, and URL filtering).  
- Conduct regular user training on recognizing phishing attempts.  
- Simulated phishing exercises to reinforce awareness.  

---

### 2. Execution of Unsigned or Untrusted Software

**Vulnerability:** Execution of Untrusted or Unsigned Software  
**Root Cause:** Insufficient Application Control Policies  
**Fixes:**  
- Enable **Application Control** (e.g., Microsoft AppLocker) to restrict unauthorized applications.  
- Ensure **software integrity verification** by allowing only digitally signed applications.  

---

### 3. Lack of Endpoint Protection

**Vulnerability:** Failure to Detect or Block Keyloggers  
**Root Cause:** Ineffective or Outdated Antivirus/Antimalware Solutions  
**Fixes:**  
- Install and update robust antivirus software.  
- Utilize **real-time threat detection** and behavior-based analysis.  

---

### 4. Outbound Communication to Command and Control (C2) Server

**Vulnerability:** Successful Communication with Remote Servers  
**Root Cause:** Lack of Outbound Network Traffic Monitoring  
**Fixes:**  
- Configure **firewalls** to block unauthorized outbound connections.  
- Use **DNS filtering and IDS/IPS** to monitor and block suspicious traffic.  

---

### 5. User Account Privileges

**Vulnerability:** Excessive Privileges Granted to User Accounts  
**Root Cause:** Lack of Privilege Separation  
**Fixes:**  
- **Enforce least privilege principles** to limit user permissions.  
- Encourage users to operate with **standard user accounts** instead of admin accounts.  

---

### 6. Outdated Operating System (Windows 1507)

**Vulnerability:** Running Unsupported OS Versions  
**Root Cause:** Lack of Ongoing Support or Patch Management  

---

# Methodology

## 1. Malicious File Development
The team developed a Python-based keylogger with the following capabilities:
- Keystroke recording utilizing the `pynput` library  
- Functional calculator interface serving as camouflage  
- Azure-hosted remote server communication  
- Executable conversion through `pyinstaller`  

## 2. Payload Delivery
The attack vector followed a straightforward path:
1. Initial file upload to **OneDrive**  
2. Distribution via **Outlook email attachment**  
3. Local machine **download by the target**  

## 3. Payload Execution
Upon execution, the application:
- Presented a **fully functional calculator interface**  
- Activated the **keylogger component** in the background  
- Maintained persistent keystroke logging and **server communication**  
- Continued operation **even after application closure**  

---

# Tools and Technical Implementation

## 1. Technical Stack
The experiment utilized the following tools:
- **Python** for core development  
- **PyInstaller** for executable creation  
- **Azure Virtual Machine** for C2 server hosting  

## 2. Core Functionality
The application integrated three primary components:
- **Keystroke capture** through `pynput`  
- **Server communication** via the `requests` library  
- **Calculator interface** implementation using `tkinter`  

---

# Key Observations
The experiment revealed several critical findings:
- The **payload successfully exploited user trust** through disguise.  
- **Windows SmartScreen (version 1507) failed to detect the threat.**  
- The keylogger **maintained undetected server communication.**  
- **Real-time keystroke transmission persisted** beyond application termination.  

---

# Mitigation Strategies

## 1. User-Level Protection
- **Avoid execution of untrusted executable files.**  
- **Verify file authenticity** before execution.  

## 2. Organizational Security
Organizations should implement:
- **Email attachment scanning.**  
- **Group Policy restrictions on unverified executables.**  
- **Regular security awareness training.**  

## 3. Administrative Controls
System administrators should deploy:
- **Regular Windows security updates.**  
- **Comprehensive network traffic monitoring.**  
- **Strict firewall configuration.**  
- **DNS filtering and IDS/IPS implementation.**  
- **EDR (Endpoint Detection and Response) solution deployment.**  

---

# Conclusion
This experiment effectively demonstrates the **critical intersection of user awareness and security measures** in cybersecurity defense. The successful exploitation of **user trust, outdated security features, and inadequate traffic monitoring** enabled the attack’s success in our controlled environment.  

Organizations can **significantly enhance their security posture** by implementing the recommended mitigation strategies.
