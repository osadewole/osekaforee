# Hackviser CORE – Lessons (Security Fundamentals)

One of the key things any organization must secure is its information. You can't
be an effective information security professional without a solid foundation,
which is why I started (and am close to finishing) Hackviser's CORE course.
Here's what I've learned so far.

## Security standards and frameworks

Three widely used frameworks help standardize how systems are secured and tested:

- **OWASP** – Open Worldwide Application Security Project
- **OSSTMM** – Open Source Security Testing Methodology Manual
- **NIST** – National Institute of Standards and Technology

(There are others I expect to meet as I go, but these are the three CORE introduced.)

## Ports and shells

A system has **65,535 ports** (numbered 0–65535). A **port** is a virtual
communication endpoint where services and protocols run. A **shell** is different:
it's an interface that lets a user execute commands directly on the operating system.

Both are prime targets. An attacker can exploit a service running on a port, and
a shell gives them a direct way to interact with the target's OS. CORE also covered
common ports and the services tied to them, which I expect to cement through more labs.

## The Cyber Kill Chain

The Cyber Kill Chain (often paired with MITRE ATT&CK) is a core model for beginners.
It matters because when reading logs, you need to pinpoint **what stage of an attack**
an intruder has reached. Misreading that can cause you to underestimate how deep an
attacker is, or to miss the "golden hour", the critical early window after detection.
It's also a useful way to explain an incident to stakeholders in non-technical terms.

**The 7 stages:**

1. **Reconnaissance** – Passive (OSINT) or active (directly probing the target).
   Reveals open ports, services, and server versions.
2. **Weaponization** – The attacker crafts malware to exploit a found vulnerability
   (e.g. using a tool like msfvenom).
3. **Delivery** – Getting the malware to the target: malicious links, ads, or emails.
4. **Exploitation** – The malware triggers the vulnerability and gains execution rights.
5. **Installation** – The attacker establishes persistence (a backdoor that survives
   reboots or lost connections), e.g. registering as a service, a scheduled task, or
   via DLL hijacking.
6. **Command and Control (C2)** – The attacker sets up communication with the system
   to issue commands and exfiltrate data. DNS tunnelling is common because it's
   outbound and usually passes through firewall restrictions.
7. **Actions on Objectives** – The attacker executes their goal: ransomware, data
   destruction, exfiltration, or resource hijacking.

At every stage there are **Indicators of Compromise (IOCs)**. Tracing these, and
feeding them into a **SIEM**, helps strengthen the system against future attacks.

## Kill Chain vs MITRE ATT&CK

For reports aimed at threat hunters, CSIRTs, and other analysts, **MITRE ATT&CK**
is better suited. It focuses on the specific tactics and techniques an attacker used,
their behavioural patterns, and how they moved after the initial compromise.
