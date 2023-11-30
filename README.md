# IIPP-Internship Documentation
## Overview

This repository serves as the documentation and code repository for the International Internship Pilot Program conducted at the National Yang Ming Chiao Tung University. The internship focused on exploring and implementing actions under the MITRE Engage 'Expose' goal, utilizing the Tpot CE Honeypot framework.

### Internship Institution: National Yang Ming Chiao Tung University
### PI/Professor: Prof. Ren-Hung Hwang

## Table of Contents

- [Internship Goals](#internship-goals)
- [Introduction to MITRE Engage](#introduction-to-mitre-engage)
- [Tools Used](#tools-used)
- [Introduction to Tpot CE Honeypot](#introduction-to-tpot-ce-honeypot)
- [Implementation of Mitre Engage Expose Goals](#implementation-of-mitre-engage-expose-goals)
  - [1. Network Monitoring (ID: EAC0002)](#1-network-monitoring-id-eac0002)
  - [2. System Activity Monitoring (ID: EAC0003)](#2-system-activity-monitoring-id-eac0003)
  - [3. Malware Detonation (ID: EAC0013)](#3-malware-detonation-id-eac0013)
  - [4. Network Analysis (ID: EAC0004)](#4-network-analysis-id-eac0004)
- [Introduction to Wazuh](#introduction-to-wazuh)
- [Deploying Wazuh as an Agent in Tpot Honeypot and Integrating with Kibana Dashboard](#deploying-wazuh-as-an-agent-in-tpot-honeypot-and-integrating-with-kibana-dashboard)
- [Integrating All Mitre Engage Expose Goals in Wazuh](#integrating-all-mitre-engage-expose-goals-in-wazuh)
- [Generating Alerts for All Mitre Engage Expose Goals in Wazuh Dashboard](#generating-alerts-for-all-mitre-engage-expose-goals-in-wazuh-dashboard)
- [Python Code to Automate Sending Alerts to Email](#python-code-to-automate-sending-alerts-to-email)
- [Findings and Analysis](#findings-and-analysis)
- [Acknowledgment](#acknowledgment)
   
## Internship Goals

The primary objectives of the internship were to explore, study, and implement actions defined under the MITRE Engage 'Expose' goal within the context of a Tpot CE Honeypot.

1. **Explore MITRE Engage White Papers:**
   - Reading and understanding the theoretical foundations and methodologies outlined in MITRE Engage white papers.

2. **Study 'Expose' Goal Actions:**
   - In-depth study of each action specified under the 'Expose' goal, with a focus on granular details and contextual relevance.

3. **Implement Chosen Actions:**
   - Implementation of four selected actions within an SSH honeypot using the Tpot honeypot framework.

## Introduction to MITRE Engage

MITRE Engage is a framework for discussing and planning adversary engagement, deception, and denial activities.The Mitre Engage Matrix is informed by adversary behavior observed in the real world and is intended to drive strategic cyber outcomes.Mitre Engage was created to help the private sector, government, and vendor communities to plan and execute the use of adversary engagement strategies and technologies.<br>

MITRE Engage combines several active defense types, including basic cyber defensive actions alongside adversary engagement and cyber deception operations. Together, these defenses enable organizations to counter attacks while also obtaining additional information about the adversary. This intelligence can help organizations better prepare for future attacks.<br>

To read more on Mitre engage [Click Here](https://github.com/sandxxax/IIPP-Internship/blob/main/Mitre%20Engage/README.md) 


## Tools Used

The following tools were employed during the internship:

- **Tpot Honeypot:** An all-in-one multi honeypot platform.
- **Suricata:** Open-source IDS/IPS and network security monitoring engine.
- **Sysmon:** System activity monitoring tool designed to capture and log detailed information about various events occurring within an operating environment.
- **VirusTotal:** Online platform for malware analysis and detection.
- **YARA Rules** YARA rules are created to identify and classify malware or other types of malicious activities based on specified patterns
- **Wazuh:** Open-source security information and event management (SIEM) tool.


## Introduction to Tpot CE Honeypot

### Honeypot:
A honeypot is a security mechanism that creates a virtual trap to lure attackers. An intentionally compromised computer system allows attackers to exploit vulnerabilities so that we can study them to improve our security policies. We can apply a honeypot to any computing resource from software and networks to file servers and routers.

Honeypots are a type of deception technology that allows us to understand attacker behavior patterns. Security teams can use honeypots to investigate cybersecurity breaches to collect intel on how cybercriminals operate. They also reduce the risk of false positives, when compared to traditional cybersecurity measures, because they are unlikely to attract legitimate activity.
Honeypots vary based on design and deployment models, but they are all decoys intended to look like legitimate, vulnerable systems to attract cybercriminals.<br>

To learn more on what honeypots are?  [Click Here](https://github.com/sandxxax/IIPP-Internship/tree/main/Honeypot#readme)

### Tpot Honeypot CE:
Tpot Honeypot is a versatile tool designed to simplify the deployment and management of honeypots.It is the all in one, optionally distributed, multiarch (amd64, arm64) honeypot plattform, supporting 20+ honeypots and countless visualization options using the Elastic Stack, along with animated live attack maps and lots of security tools to further improve the deception experience.

To harness the power of T-Pot, ensure our system meets the prerequisites, requiring a minimum of 8-16 GB RAM, 128 GB of free disk space, and a reliable internet connection for seamless installation. Operating on Debian 11 (Bullseye) Netinstaller, we leverage the efficiency of Docker and Docker Compose, enabling the concurrent execution of multiple tools. Our comprehensive platform boasts a diverse array of honeypots, integrates essential tools like CyberChef and Spiderfoot, and incorporates Network Security Monitoring (NSM) components such as Suricata for robust threat detection. Our technical architecture strategically combines Elastic Stack, Docker, and an array of security tools, enhancing the overall deception experience.

Dive into this documentation for in-depth insights into ***system requirements, installation and congiguration of T-pot CE honeypot*** in our environment  [Click Here](https://github.com/sandxxax/IIPP-Internship/tree/main/T-pot%20Honeypot%20CE#readme)

## Implementation of Mitre Engage Expose Goals

The 4 Mitre Engage Expose goals which I have implemented in my T-pot Honeypot includes:

#### 1. Network Monitoring
#### 2. System Activity Monitoring 
#### 3. Malware Detonation 
#### 4. Network Analysis 

Let's review each of them individually:

### 1. Network Monitoring (ID: EAC0002):
- Monitoring network traffic is a fundamental aspect of cybersecurity, involving the systematic observation and analysis of data exchanged within a network. The comprehensive practice encompasses the collection of server and firewall logs, which are then centralized for in-depth scrutiny. This centralized approach facilitates efficient and centralized analysis, allowing defenders to identify anomalous traffic patterns and activities that could signify the presence of adversaries. This process serves as a cornerstone for situational awareness, providing cybersecurity professionals with crucial insights into the dynamics of their network.

- Effective network monitoring requires meticulous pre-operational planning to ensure the comprehensive collection of critical network traffic. This planning is essential for creating a robust foundation that aids in the detection of unexpected outbound traffic and the identification of known adversary command and control (C2) protocols. By incorporating both automated tools and manual analysis, defenders can gain a nuanced understanding of network behavior, enabling them to discern normal activities from potentially malicious ones. This proactive approach to network monitoring not only enhances the ability to detect adversarial threats promptly but also strengthens the overall resilience of the cybersecurity infrastructure.

- To learn more on Network monitoring implementation in T-pot Honeypot [Click Here](https://github.com/sandxxax/IIPP-Internship/edit/main/Implementation%20of%20Mitre%20Engage%20Expose%20Goals/Network%20Monitoring)

### 2. System Activity Monitoring (ID: EAC0003):
- System Activity Monitoring is a pivotal cybersecurity measure that involves collecting comprehensive system activity logs, offering a detailed account of user logins, actions, and various events within an environment. This proactive approach provides defenders with invaluable insights into potential adversary activities and the tools employed, forming a crucial aspect of threat detection and response. Snort and it’s usage in system monitoring  helped me understand the overall importance of this activity.
  
- The captured logs, when centralized for in-depth analysis, become a powerful tool in understanding and mitigating potential security threats. However, the effectiveness of this monitoring strategy relies on meticulous planning to strike a balance between the depth of data collection and avoiding data overload, ensuring that defenders can focus on relevant information without being overwhelmed.
  
- These system activity logs play a crucial role in enhancing situational awareness and operational safety. They contribute to a comprehensive understanding of adversary tactics, guiding the strategic selection of logs to monitor. The careful pre-operational environment setup is paramount to the success of system activity monitoring, as it ensures that the collected data is not only relevant but also manageable for analysis. By incorporating this measure, organizations can significantly strengthen their security posture, enabling a proactive response to potential threats and reinforcing the resilience of their cybersecurity infrastructure.

- To learn more on System Activity monitoring implementation in T-pot Honeypot [Click Here](https://github.com/sandxxax/IIPP-Internship/edit/main/Implementation%20of%20Mitre%20Engage%20Expose%20Goals/System%20Activity%20Monitoring)

### 3. Malware Detonation (ID: EAC0013):
- Malware Detonation is a strategic cybersecurity practice that involves the deliberate execution of malware within a controlled environment to analyze its functionality.This controlled setting allows for a detailed examination of the malware's behavior, providing security professionals with critical insights into its operations. The execution takes place under carefully defined objectives and safety protocols to ensure that the analysis remains secure and does not pose a threat to the overall environment. This proactive approach is instrumental in understanding the intricacies of various types of malwares, from their attack vectors to the potential impact on a system.

- The execution environment for malware detonation can range from standard malware analysis tools to customized engagement setups, depending on the specific goals of the operation. The objectives of this process extend beyond mere analysis, as it can yield valuable new indicators of compromise (IOCs) that enhance threat intelligence. Additionally, it has the potential to reveal adversary tactics, providing defenders with actionable insights to fortify their security measures. In some cases, malware detonation can be leveraged as a disruptive measure, impeding the adversary's capabilities and thwarting their malicious activities.By incorporating malware detonation into their cybersecurity arsenal, organizations can bolster their defenses and stay ahead of emerging threats in an ever-evolving digital landscape.

-  To learn more on Malware Detonation implementation in T-pot Honeypot [Click Here](https://github.com/sandxxax/IIPP-Internship/edit/main/Implementation%20of%20Mitre%20Engage%20Expose%20Goals/Malware%20Detonation)

### 4. Network Analysis (ID: EAC0004):
- Network Analysis is a crucial component of cybersecurity that involves the thorough examination of network traffic to extract valuable intelligence on communications between systems. Malicious traffic analysis  is the critical aspect of this activity. The primary goal is to uncover potential adversary activities, such as command and control (C2) traffic or data exfiltration, which are indicative of malicious intent. This process requires capturing and scrutinizing network traffic, often necessitating the development of custom protocol decoder frameworks capable of handling complex encryption and proprietary protocols. While creating these decoders demands technical expertise, the insights gained from such efforts are invaluable in understanding and mitigating potential threats.
  
- The complexity of modern cybersecurity threats often requires advanced techniques for deciphering encrypted network data. Through network analysis, security professionals can employ custom decoders to decrypt network data, exposing adversary C2 actions or data exfiltration attempts. This level of insight not only aids in understanding communication channels used by adversaries but also enables defenders to manipulate data for strategic operational goals in the future. By investing in network analysis capabilities, organizations enhance their ability to detect, analyze, and respond to evolving cyber threats, fortifying their overall cybersecurity posture in an ever-changing digital landscape.

-  To learn more on Network Analysis implementation in T-pot Honeypot [Click Here](https://github.com/sandxxax/IIPP-Internship/tree/main/Implementation%20of%20Mitre%20Engage%20Expose%20Goals/Network%20Analysis)

## Introduction to Wazuh
Wazuh is an open-source security information and event management (SIEM) platform designed to enhance threat detection, intrusion detection, and response capabilities for organizations. Rooted in a robust combination of log analysis, intrusion detection, vulnerability detection, and security information management, Wazuh provides a comprehensive solution for monitoring and managing security events across an entire IT infrastructure. Originally developed as OSSEC-HIDS (Host-based Intrusion Detection System), Wazuh has evolved into a scalable and extensible platform that aids organizations in fortifying their cybersecurity posture.

The core functionality of Wazuh revolves around its ability to collect, analyze, and correlate data from diverse security-related sources, such as logs, events, and configurations. With a focus on real-time threat detection and response, Wazuh helps organizations proactively identify and mitigate potential security incidents. Its open-source nature fosters community collaboration, enabling users to leverage a wealth of security expertise and contribute to the continuous improvement of the platform. Wazuh's user-friendly interface, coupled with its flexibility and powerful features, makes it a valuable asset for organizations seeking a robust and customizable solution to bolster their cybersecurity defenses.

To learn more on Wazuh installation and configuration [Click Here](https://github.com/sandxxax/IIPP-Internship/blob/main/Wazuh/README.md)

## Deploying Wazuh as an Agent in Tpot Honeypot and Integrating with Kibana Dashboard

Deploying Wazuh as an agent in a T-Pot honeypot and integrating it with the Kibana dashboard enhances the overall security posture of the network. T-Pot, a powerful honeypot solution, simulates a variety of services and systems to attract potential attackers. By deploying Wazuh as an agent within the T-Pot environment, organizations can leverage its advanced threat detection capabilities to monitor and analyze activities within the honeypot. Wazuh provides real-time log analysis, intrusion detection, vulnerability detection, and more, allowing security teams to gain insights into potential threats and vulnerabilities exploited by malicious actors. Integrating Wazuh with the Kibana dashboard further facilitates visualization and analysis of the collected data, enabling security professionals to identify patterns, anomalies, and potential security incidents effectively.

The deployment process involves configuring Wazuh agents within the T-Pot honeypot environment, ensuring that they communicate seamlessly with the Wazuh manager. Once integrated, the data generated by Wazuh agents can be visualized through Kibana, providing a user-friendly interface for monitoring and analyzing security events. This integration allows security teams to centralize their threat intelligence and respond proactively to emerging threats. By combining the deception capabilities of T-Pot with the robust detection and analysis features of Wazuh, organizations can create a comprehensive defense strategy that not only identifies potential threats but also helps in understanding the tactics, techniques, and procedures employed by adversaries in simulated environments.

To learn more on how to do this deployment [Click Here](https://github.com/sandxxax/IIPP-Internship/blob/main/Wazuh/README.md)

## Integrating All Mitre Engage Expose Goals in Wazuh

The integration of Suricata logs into Wazuh enhances network security monitoring, incorporating Suricata's potent threat detection engine for real-time identification of malicious activities such as denial-of-service attacks and buffer overflows. Concurrently, the inclusion of Sysmon logs provides detailed insights into system-level activities, fostering seamless correlation between system and network events. This unified approach strengthens Wazuh's overall threat detection capabilities.

In a complementary move, the integration of VirusTotal into Wazuh significantly augments threat detection by leveraging comprehensive analysis from the VirusTotal API. Wazuh's File Integrity Monitoring (FIM) feature continuously monitors files and directories, triggering alerts for suspicious activity. By engaging VirusTotal, organizations can proactively respond to potential threats, with the integration providing detailed insights into potentially malicious content (Fig 8).

Moreover, the integration of network analysis through Suricata into Wazuh signifies a pivotal advancement in bolstering overall cybersecurity defenses. Suricata, functioning as both an Intrusion Detection System (IDS) and Intrusion Prevention System (IPS), offers real-time monitoring and analysis of network traffic. This collaboration enables Wazuh to leverage Suricata's rule-based language for detecting diverse malicious activities, fostering a more resilient and adaptive security posture.

To learn more how to integrate all goals in Wazuh [Click Here](https://github.com/sandxxax/IIPP-Internship/blob/main/Wazuh/README.md#integration-of-wazuh-unifying-all-goals-in-one-platform)

## Generating Alerts for All Mitre Engage Expose Goals in Wazuh Dashboard
Creating a robust security posture involves aligning monitoring efforts with the MITRE ATT&CK Engage and Expose goals within the Wazuh Dashboard. By configuring Wazuh to generate alerts based on MITRE ATT&CK techniques associated with these goals, organizations can effectively detect and respond to potential threats targeting their environment. This proactive approach ensures that the Wazuh Dashboard becomes a powerful tool for identifying adversary tactics and techniques related to engaging and exposing targets, allowing security teams to stay one step ahead of sophisticated cyber threats.

Through the integration of MITRE ATT&CK Engage and Expose goals into Wazuh, security professionals gain a consolidated view of potential adversarial behaviors. This alignment not only enhances the detection capabilities of the security infrastructure but also provides a comprehensive understanding of how adversaries might engage with and expose vulnerabilities in the organization's network. Leveraging the MITRE ATT&CK framework within the Wazuh Dashboard enables security teams to create targeted and effective response strategies, reinforcing the overall cybersecurity defenses against a spectrum of sophisticated threats.

To visualize the Alerts [Click Here](https://github.com/sandxxax/IIPP-Internship/blob/main/Wazuh/README.md#integration-of-wazuh-unifying-all-goals-in-one-platform)

## Python Code to Automate Sending Alerts to Email 
The provided Python script functions as an intrusion detection system by continuously monitoring the Suricata fast.log file for potential security threats. Upon detecting specific attack signatures, the script triggers real-time email alerts to notify the user of possible breaches. It uses regular expressions to identify attack codes within log entries, and if a match is found, an email is sent using the `send_email` function. The script is set to run automatically on system startup, ensuring continuous monitoring and timely alerts for improved cybersecurity.

For automated alerting, the Python script utilizes the smtplib library to establish a connection to the Gmail SMTP server, facilitating the seamless transmission of email notifications. The integration with Gmail is secured using an application password, enhancing the overall security of email communication. The script allows users to easily customize the list of attack signatures to monitor. The integration with the VPN and Suricata service restart in the crontab entry showcases a comprehensive approach to ensuring the system is in the desired state before initiating the monitoring script. This solution not only automates the process of detecting and alerting on potential intrusions but also provides insights into customization options for tailored security monitoring.

- To understand how it is done [Click here](https://github.com/sandxxax/IIPP-Internship/blob/main/Implementation%20of%20Mitre%20Engage%20Expose%20Goals/Network%20Monitoring/README.md#automation-of-e-mail-alerts)

- To go through the Python Code [Click Here](https://github.com/sandxxax/IIPP-Internship/blob/main/Python%20code)

## Findings and Analysis
The comprehensive implementation of the MITRE Engage 'Affect' goal activities within the Tpot CE Honeypot, coupled with real-world scenarios and proactive measures, yielded valuable insights into the behavior of potential adversaries. The findings and analysis encapsulate key observations, strategic outcomes, and the overall impact on the honeypot's security posture.

### A.  Network Monitoring: 
**Network Monitoring Using Suricata:** Real-time monitoring with Suricata in the T-pot Honeypot significantly boosted threat detection. The integration into Wazuh provided valuable insights into emerging threats, contributing to a more resilient cybersecurity posture. Key findings unveiled distinct patterns of malicious activities, facilitating a streamlined analysis of Suricata logs within Wazuh. These actionable insights empowered security teams to adapt their defense strategy effectively.

**Key Findings:** The key findings in network monitoring using Suricata emphasized the rule-based language's effectiveness in detecting diverse threats. The logs highlighted the importance of real-time monitoring in identifying emerging threats promptly. The seamless integration into Wazuh facilitated a streamlined analysis of Suricata logs, providing security teams with actionable insights to fortify network defenses against evolving cyber threats.

### B. System Activity Monitoring:
**System Activity Monitoring using Sysmon:** The integration of Sysmon logs into Wazuh enriched the platform's understanding of system-level activities. Detailed insights into process creation, file modifications, and network connections allowed for comprehensive correlation between system and network indicators. Key findings underscored the pivotal role of Sysmon logs in enhancing situational awareness and operational safety. The correlation of system activity with network-level events provided a holistic view for more effective threat detection.

**Key Findings:** Key findings in system activity monitoring using Sysmon emphasized the significance of detailed logs in enhancing cybersecurity. Sysmon's capabilities in logging critical events, such as process creation and file modifications, provided a granular view of potential threats. The integration into Wazuh streamlined the analysis process, allowing security teams to focus on relevant information. The findings highlighted Sysmon's role in strengthening the correlation between system and network-level indicators, facilitating a more comprehensive approach to threat detection.

### C.	Malware Detonation:
**Malware Detonation using VirusTotal and Yara Rules:** Strategic implementation of malware detonation using VirusTotal proved instrumental in analyzing the functionality of malicious software. The integration into Wazuh's File Integrity Monitoring (FIM) facilitated proactive monitoring of files and directories, ensuring a swift response to potential threats. Key findings underscored the collaborative and community-driven nature of VirusTotal, offering a more comprehensive understanding of emerging threats. The seamless integration enhanced Wazuh's threat detection capabilities, contributing to a more resilient cybersecurity posture.

**Key findings:** Key findings in malware detonation using VirusTotal highlighted the platform's ability to provide detailed insights into malicious software behavior. The collaborative nature of VirusTotal, leveraging multiple antivirus engines, contributed to a thorough analysis of potential threats. The integration into Wazuh's FIM feature enhanced the platform's proactive monitoring capabilities. The findings emphasized the role of malware detonation in strengthening threat intelligence and fortifying defenses against evolving cyber threats.

### D. Network Analysis:
**Incorporating Suricata into Wazuh for Network Analysis:** The pivotal integration of Suricata into Wazuh for network analysis provided a comprehensive view of the network security landscape. Real-time monitoring and analysis of network traffic, leveraging Suricata's IDS and IPS functionalities, strengthened overall threat intelligence. Key findings emphasized the rule-based language's effectiveness in detecting diverse malicious activities. The collaboration between Suricata and Wazuh empowered a proactive defense against evolving cyber threats, showcasing the platform's adaptability and robust cybersecurity capabilities.

**Key findings:** Key findings in incorporating Suricata into Wazuh highlighted the platform's ability to provide a unified defense against network-level threats. Suricata's versatility, combining IDS and IPS functionalities, enhanced real-time threat intelligence. The findings showcased the effectiveness of the rule-based language in detecting and responding to various malicious activities. The seamless integration into Wazuh allowed security professionals to correlate network-level events with broader security indicators, fostering a more resilient and adaptive security posture.

## Acknowledgment

I would like to express my gratitude to Prof. Ren-Hung Hwang, the ANT Lab, and NYCU AI College for the guidance and support throughout the internship. Special thanks to my lab members and seniors for their assistance.
