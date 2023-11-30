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

- To learn more on Network monitoring implementation in T-pot Honeypot [Click Here]()

### 2. System Activity Monitoring (ID: EAC0003):
- System Activity Monitoring is a pivotal cybersecurity measure that involves collecting comprehensive system activity logs, offering a detailed account of user logins, actions, and various events within an environment. This proactive approach provides defenders with invaluable insights into potential adversary activities and the tools employed, forming a crucial aspect of threat detection and response. Snort and it’s usage in system monitoring  helped me understand the overall importance of this activity.
  
- The captured logs, when centralized for in-depth analysis, become a powerful tool in understanding and mitigating potential security threats. However, the effectiveness of this monitoring strategy relies on meticulous planning to strike a balance between the depth of data collection and avoiding data overload, ensuring that defenders can focus on relevant information without being overwhelmed.
  
- These system activity logs play a crucial role in enhancing situational awareness and operational safety. They contribute to a comprehensive understanding of adversary tactics, guiding the strategic selection of logs to monitor. The careful pre-operational environment setup is paramount to the success of system activity monitoring, as it ensures that the collected data is not only relevant but also manageable for analysis. By incorporating this measure, organizations can significantly strengthen their security posture, enabling a proactive response to potential threats and reinforcing the resilience of their cybersecurity infrastructure.

- To learn more on System Activity monitoring implementation in T-pot Honeypot [Click Here]()

### 3. Malware Detonation (ID: EAC0013):
- Malware Detonation is a strategic cybersecurity practice that involves the deliberate execution of malware within a controlled environment to analyze its functionality.This controlled setting allows for a detailed examination of the malware's behavior, providing security professionals with critical insights into its operations. The execution takes place under carefully defined objectives and safety protocols to ensure that the analysis remains secure and does not pose a threat to the overall environment. This proactive approach is instrumental in understanding the intricacies of various types of malwares, from their attack vectors to the potential impact on a system.

- The execution environment for malware detonation can range from standard malware analysis tools to customized engagement setups, depending on the specific goals of the operation. The objectives of this process extend beyond mere analysis, as it can yield valuable new indicators of compromise (IOCs) that enhance threat intelligence. Additionally, it has the potential to reveal adversary tactics, providing defenders with actionable insights to fortify their security measures. In some cases, malware detonation can be leveraged as a disruptive measure, impeding the adversary's capabilities and thwarting their malicious activities.By incorporating malware detonation into their cybersecurity arsenal, organizations can bolster their defenses and stay ahead of emerging threats in an ever-evolving digital landscape.

-  To learn more on Malware Detonation implementation in T-pot Honeypot [Click Here]()

### 4. Network Analysis (ID: EAC0004):
- Network Analysis is a crucial component of cybersecurity that involves the thorough examination of network traffic to extract valuable intelligence on communications between systems. Malicious traffic analysis  is the critical aspect of this activity. The primary goal is to uncover potential adversary activities, such as command and control (C2) traffic or data exfiltration, which are indicative of malicious intent. This process requires capturing and scrutinizing network traffic, often necessitating the development of custom protocol decoder frameworks capable of handling complex encryption and proprietary protocols. While creating these decoders demands technical expertise, the insights gained from such efforts are invaluable in understanding and mitigating potential threats.
  
- The complexity of modern cybersecurity threats often requires advanced techniques for deciphering encrypted network data. Through network analysis, security professionals can employ custom decoders to decrypt network data, exposing adversary C2 actions or data exfiltration attempts. This level of insight not only aids in understanding communication channels used by adversaries but also enables defenders to manipulate data for strategic operational goals in the future. By investing in network analysis capabilities, organizations enhance their ability to detect, analyze, and respond to evolving cyber threats, fortifying their overall cybersecurity posture in an ever-changing digital landscape.

-  To learn more on Network Analysis implementation in T-pot Honeypot [Click Here]()

## Introduction to Wazuh
Wazuh is an open-source security information and event management (SIEM) platform designed to enhance threat detection, intrusion detection, and response capabilities for organizations. Rooted in a robust combination of log analysis, intrusion detection, vulnerability detection, and security information management, Wazuh provides a comprehensive solution for monitoring and managing security events across an entire IT infrastructure. Originally developed as OSSEC-HIDS (Host-based Intrusion Detection System), Wazuh has evolved into a scalable and extensible platform that aids organizations in fortifying their cybersecurity posture.

The core functionality of Wazuh revolves around its ability to collect, analyze, and correlate data from diverse security-related sources, such as logs, events, and configurations. With a focus on real-time threat detection and response, Wazuh helps organizations proactively identify and mitigate potential security incidents. Its open-source nature fosters community collaboration, enabling users to leverage a wealth of security expertise and contribute to the continuous improvement of the platform. Wazuh's user-friendly interface, coupled with its flexibility and powerful features, makes it a valuable asset for organizations seeking a robust and customizable solution to bolster their cybersecurity defenses.

To learn more on Wazuh installation and configuration [Click Here](https://github.com/sandxxax/IIPP-Internship/blob/main/Wazuh/README.md)

## Deploying Wazuh as an Agent in Tpot Honeypot and Integrating with Kibana Dashboard

To learn more on Wazuh installation and configuration [Click Here](https://github.com/sandxxax/IIPP-Internship/blob/main/Wazuh/README.md)


## Integrating All Mitre Engage Expose Goals in Wazuh


## Generating Alerts for All Mitre Engage Expose Goals in Wazuh Dashboard

...

## Python Code to Automate Sending Alerts to Email 

...

## Findings and Analysis

...

## Acknowledgment


## Tools Used

The following tools were employed during the internship:

- **Tpot Honeypot:** An all-in-one multi honeypot platform.
- **Suricata:** Open-source IDS/IPS and network security monitoring engine.
- **Sysmon:** System activity monitoring tool for detailed Windows and Linux system insights.
- **VirusTotal:** Online platform for malware analysis and detection.
- **Wazuh:** Open-source security information and event management (SIEM) tool.

## Implementation Details

### 1. Network Monitoring (ID: EAC0002) using Suricata

#### Overview
Real-time monitoring of network traffic using Suricata, an open-source IDS/IPS and network security monitoring engine.

#### Steps Taken
1. **Installation:**
   - Suricata was installed on the honeypot environment, providing the capability to analyze and detect potential threats in real-time.

2. **Configuration:**
   - Custom configurations were applied to Suricata to tailor its functionality to the specific requirements of the 'Expose' goal.

3. **Integration with Wazuh:**
   - Suricata logs were integrated into Wazuh for centralized security monitoring, enabling more effective threat detection and response.

4. **Results and Observations:**
   - The integration provided valuable insights into emerging threats, allowing for a proactive defense strategy.

#### Code Snippets
Code snippets related to Suricata configuration and integration with Wazuh can be found in the [code/](./code/) directory.

### 2. System Activity Monitoring (ID: EAC0003) using Sysmon

#### Overview
Logging detailed information about process creation, file modifications, and network connections using Sysmon.

#### Steps Taken
1. **Sysmon Installation:**
   - Sysmon was deployed on both Windows and Linux-based systems in the honeypot environment to capture detailed system activities.

2. **Custom Logging Configuration:**
   - Specific logging configurations were applied to Sysmon to ensure the capture of relevant information for threat detection.

3. **Integration with Wazuh:**
   - Sysmon logs were seamlessly integrated into Wazuh for correlation with network-level indicators, enhancing overall threat intelligence.

4. **Results and Observations:**
   - The correlation between system and network-level events provided a holistic view for more effective threat detection.

#### Code Snippets
Code snippets related to Sysmon installation, custom configurations, and integration with Wazuh can be found in the [code/](./code/) directory.

### 3. Malware Detonation (ID: EAC0013) using VirusTotal

#### Overview
Analysis of malicious software behavior in a controlled environment using VirusTotal.

#### Steps Taken
1. **Platform Utilization:**
   - VirusTotal was employed as an online platform to aggregate multiple antivirus engines and perform dynamic analysis on suspicious files.

2. **Integration with Wazuh:**
   - Results from VirusTotal analyses were integrated into Wazuh's File Integrity Monitoring (FIM) feature for proactive threat detection.

3. **Results and Observations:**
   - The collaborative and community-driven nature of VirusTotal contributed to a more comprehensive understanding of emerging threats.

#### Code Snippets
Code snippets related to the utilization of VirusTotal and its integration with Wazuh can be found in the [code/](./code/) directory.

### 4. Network Analysis (ID: EAC0004) using Suricata

#### Overview
Thorough examination of network traffic to extract intelligence on communications between systems using Suricata.

#### Steps Taken
1. **Rule-based Analysis:**
   - Suricata was configured to perform rule-based analysis, employing anomaly detection, protocol analysis, and signature inspection methods.

2. **

Correlation with Wazuh:**
   - Suricata logs were correlated with Wazuh to provide a unified view of network and system-level threats.

3. **Results and Observations:**
   - The combination of rule-based analysis and correlation with Wazuh facilitated the identification of malicious patterns and behaviors.

#### Code Snippets
Code snippets related to Suricata rule configuration and integration with Wazuh can be found in the [code/](./code/) directory.

## Acknowledgments

I would like to express my gratitude to Prof. Ren-Hung Hwang, the ANT Lab, and NYCU AI College for the guidance and support throughout the internship. Special thanks to my lab members and seniors for their assistance.

