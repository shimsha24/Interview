# Interview SOC
## What’s the difference between HTTP and HTTPS?
HTTPS uses TLS (SSL) to encrypt normal HTTP requests and responses. HTTPS is more secure than HTTP since it uses TLS (SSL) encryption for all HTTP requests and responses. Hypertext transfer protocol (HTTP) is a protocol or set of communication rules for client-server communication. When you visit a website, your browser sends a HTTP request to the web server, which responds with an HTTP response. The web server and your browser exchange data as plaintext. Hypertext transfer protocol secure (HTTPS) is a more secure version or an extension of HTTP. In HTTPS, the browser and server establish a secure, encrypted connection before transferring data.

## IDS vs. IPS: Definitions, Comparisons & Why You Need Both
An intrusion detection system (IDS) monitors traffic on your network, analyses that traffic for signatures matching known attacks, and when something suspicious happens, you're alerted. In the meantime, the traffic keeps flowing. 
An intrusion prevention system (IPS) also monitors traffic. But when something unusual happens, the traffic stops altogether until you investigate and decide to open the floodgates again.
![image](https://github.com/user-attachments/assets/2e9cd0cc-5293-4855-a95f-0b5cff227301)
You want to protect the assets on your server. But you don't want to slow down the traffic, even if a problem occurs. An intrusion detection system (IDS) could be the solution you've been looking for. 
You want to stop an attack as soon as it's discovered, even if that means closing down legitimate traffic for security concerns. An intrusion protection system (IPS) could be just right for you. 

## A client is experiencing a ransomware attack, you have all the logs and tools available to you. Walk me through from start to finish on what you will do.
If a client is experiencing a ransomware attack, here's what I would do step-by-step:

#### Assess the Situation: First, I would quickly check the severity of the attack. I'd talk to the client to confirm what data has been affected and how the ransomware has spread. I'd ask questions like: Are they locked out of their files? Can they still access some systems? This will help me understand the damage.

#### Isolate Affected Systems: To stop the ransomware from spreading, I would disconnect the affected machines from the network. This means taking the infected computers offline or disabling the network connections. If it's safe to do so, I'd also block suspicious IP addresses to stop any further contact with the attacker.

#### Check Logs for the Source: I’d then look through the logs to trace the origin of the attack. Using the available logs, I would investigate how the ransomware got into the system—whether it was through a phishing email, a weak password, or unpatched software.

#### Identify the Ransomware: Based on the behavior of the ransomware (file extensions, ransom note, etc.), I would identify which type it is. There are databases of ransomware variants that can help identify possible decryption tools or strategies.

#### Look for Decryption Tools: Some ransomware types already have decryption tools available. I would check online resources to see if this particular variant has a tool that can recover the client’s files without paying the ransom.

#### Notify Authorities: Depending on the severity and type of ransomware, I would advise the client to report the attack to law enforcement or cybersecurity authorities. This helps track these attacks and may assist in finding a resolution.

#### Restore from Backup: If the client has backups that were not affected, I would help restore the systems from those backups. It’s essential to ensure the backups are clean before restoring them to prevent reinfection.

#### Full System Scan: After dealing with the immediate threat, I would run a full malware scan across the systems to ensure there are no lingering infections or hidden backdoors.

#### Implement Security Measures: Once the systems are restored, I would help the client put stronger security measures in place. This includes applying all software updates, ensuring firewalls and antivirus software are up to date, enabling multi-factor authentication, and providing security training to staff to avoid future attacks.

#### Document Everything: Finally, I’d document every step of the process for future reference, including what happened, how we responded, and what we could improve.

Throughout this process, my priority would be to minimize the damage, recover data safely, and prevent future attacks.
In a real ransomware attack where the system is locked, here’s how you would handle Step 3 (Check Logs for the Source) and Step 4 (Identify the Ransomware):

Step 3: Check Logs for the Source (If the system is locked)
- Use Centralized Logging Systems
- Network Logs: Check the firewall, intrusion detection/prevention systems (IDS/IPS), or network logs.
- Logs from Unaffected Systems

Step 4: Identify the Ransomware (If the system is locked)
 - Ransom Note: Ransomware usually leaves a ransom note (often in a text or HTML file) on the infected system.
 - ile Extensions: Look at the extensions of the encrypted files (if accessible on unaffected systems or file shares). Many ransomware variants append specific file extensions to encrypted files (e.g., .lock, .crypt). These extensions can help you identify the ransomware family.
 - Ransomware Identification Tools: You can use online resources like ID Ransomware (https://id-ransomware.malwarehunterteam.com/)
 - Threat Intelligence Platforms: Use threat intelligence feeds or platforms that monitor ransomware activity. They can help you quickly match the indicators of compromise (IOCs), such as file hashes or IP addresses, with known ransomware variants.

##    It is 3 AM and you receive 3 severity 1 alerts.
1: An IDS Outbound Cobalt Strike alert
2: Sensitive account login from China
3: Mimikatz binary blocked
All have 30-minute SLAs, which one do you take first and why?
Here's how I would prioritize and respond:
#### IDS Outbound Cobalt Strike Alert:
This alert indicates that Cobalt Strike, a known hacking tool often used for command and control (C2), is trying to send data out of the network. This could mean an attacker has already gained control of part of the system and is actively communicating with an external server.

#### Sensitive Account Login from China:
This alert shows that someone is logging in with a sensitive account from China. If this is unusual behavior for the account owner, it could be a sign that their account has been compromised. However, we don't know if this login is currently causing any harm, but it's still urgent.

#### Mimikatz Binary Blocked:
Mimikatz is a tool used by attackers to steal passwords. In this case, the system blocked it from running. Since it was successfully blocked, the immediate threat might have been stopped, but it still indicates a serious attack attempt.

Which to handle first:
Priority: IDS Outbound Cobalt Strike Alert

I would start with the Cobalt Strike alert because it suggests an ongoing attack where data might already be leaving the network. The attacker could have control of a system and be exfiltrating sensitive information. This is the most dangerous because it's an active threat, and stopping it quickly would minimize potential damage.
Next Steps:
After addressing the Cobalt Strike alert, I would:

Investigate the sensitive account login from China. If the login is unauthorized, I would disable the account to prevent any further misuse.
Finally, I would check the Mimikatz binary alert to confirm it was fully blocked and to ensure no other malicious activity occurred around it.
By prioritizing the Cobalt Strike alert, I focus on the most immediate threat, but I also ensure the other alerts are handled within their SLA.

## You accidentally clicked on a malicious link while you were investigating it, what do you do?
- Stay Calm:
First, I would stay calm. Panicking can make things worse, and quick, thoughtful action is more effective.

- Disconnect from the Network:
Immediately, I would disconnect my computer from the network (Wi-Fi or Ethernet). This would stop any potential malware from spreading or communicating with the attacker’s server.

- Check for Suspicious Activity:
I would quickly check if anything unusual happened after clicking the link, like strange pop-ups, new software downloads, or changes in my files. This would give me an idea of whether the link triggered any harmful actions.

- Run an Antivirus/Malware Scan:
I’d then run a full scan using antivirus or anti-malware software on my computer. This would help detect and remove any malware that might have been downloaded from the link.

- Report the Incident:
I would notify my security team or manager immediately to ensure they’re aware of the incident. They might need to take extra steps to protect the rest of the network, especially if I had access to sensitive data or systems.

- Review Logs and Take Precautions:
I would review system and network logs to look for any unusual behavior around the time I clicked the link. This can help identify if anything suspicious happened after the click. I would also change any passwords for accounts I might have been logged into at the time, just in case.

- Follow Up with Further Investigation:
Once the initial steps are taken, I would work with the team to investigate the link further—where it leads, what it was meant to do, and whether there’s any broader threat to the company.
