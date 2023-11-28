# IIPP-Internship Documentation
## Overview

This repository serves as the documentation and code repository for the International Internship Pilot Program conducted at the National Yang Ming Chiao Tung University. The internship focused on exploring and implementing actions under the MITRE Engage 'Expose' goal, utilizing the Tpot CE Honeypot framework.

### Internship Institution: National Yang Ming Chiao Tung University
### PI/Professor: Prof. Ren-Hung Hwang

## Table of Contents

- [Internship Goals](#internship-goals)
- [Introduction to MITRE Engage](#introduction-to-mitre-engage)
- [Tools Used](#tools-used)
- [Installation and Configuration of Tpot Honeypot](#installation-and-configuration-of-tpot-honeypot)
- [Implementation and Mitre Engage Expose Goals](#implementation-and-mitre-engage-expose-goals)
  - [1. Network Monitoring (ID: EAC0002) using Suricata](#1-network-monitoring-id-eac0002-using-suricata)
  - [2. System Activity Monitoring (ID: EAC0003) using Sysmon](#2-system-activity-monitoring-id-eac0003-using-sysmon)
  - [3. Malware Detonation (ID: EAC0013) using VirusTotal](#3-malware-detonation-id-eac0013-using-virustotal)
  - [4. Network Analysis (ID: EAC0004) using Suricata](#4-network-analysis-id-eac0004-using-suricata)
- [Introduction to Wazuh](#introduction-to-wazuh)
- [Deploying Wazuh as an Agent in Tpot Honeypot and Integrating with Kibana Dashboard](#deploying-wazuh-as-an-agent-in-tpot-honeypot-and-integrating-with-kibana-dashboard)
- [Integrating All Mitre Engage Expose Goals in Wazuh](#integrating-all-mitre-engage-expose-goals-in-wazuh)
- [Generating Alerts for All Mitre Engage Expose Goals in Wazuh Dashboard](#generating-alerts-for-all-mitre-engage-expose-goals-in-wazuh-dashboard)
- [Python Code to Automate Sending Alerts to Email](#python-code-to-automate-sending-alerts-to-email)
- [Acknowledgment](#acknowledgment)
- 
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

## The MITRE Engage Matrix

The MITRE Engage matrix serves as a visual representation of the relationship between techniques and tactics:

- **Tactics**: It represents the objectives of defenders (illustrated in the columns below).
- **Techniques**:It outlines how each defense can contribute to achieving one or multiple tactics (illustrated in the individual cells).
  
![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/36eceec7-e1a1-4550-a71b-661910082969)

### Techniques and Procedures

MITRE Engage techniques delineate active defense actions, allowing defenders to attain predefined tactical objectives through specific actions. For instance, adding decoy credentials to an adversary engagement system enables defenders to assess whether adversaries attempt to exploit these credentials to gain access to other systems within the engagement network.

MITRE Engage techniques encompass a broad range of actions, including:

- **Basic Foundational Techniques**: Applicable across a wide scope of organizations and can be layered on top of advanced techniques. Examples include network monitoring, system activity monitoring, and backup and recovery.

- **Advanced Techniques**: Deployed for the manipulation of software and networks. Typically utilized by deception vendors or organizations engaged in in-depth adversary study.

MITRE Engage procedures provide detailed instructions on implementing a technique.

### Linking Tactics and Techniques

MITRE Engage associates active defense tactics with relevant techniques, a crucial aspect of any active defense operation. Techniques play a pivotal role in building the systems and controls within an operational environment.

In the linkage between tactics and techniques, a single technique can support multiple tactics, and vice versa. For instance, tightening security controls can disrupt adversary activities, while loosening certain controls can facilitate further engagement.

My internship goal is to work on Expose component of the Mitre Engage matrix

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/d184cc15-469a-455d-9cb5-635478096459)

Mitre Engage Expose component (ID: EGO0001) is about discovering previously undetected adversaries engaging in one of two behaviors. First, the adversary may be attempting to gain access to the networks. Second, the adversary may be currently operating on the networks. Both categories of adversary behavior contain vulnerabilities that can be advantageous for a defender seeking to expose the adversary.

As an example of such a vulnerability, when an adversary interacts with network or system resources, they are vulnerable to trigger tripwires. The defender can make and leak fake credentials both inside and outside of the network. The defender can then monitor for the use of these credentials. Then, when an adversary uses a fake credential, the defender will receive a high-fidelity alert. In addition, if the credentials are unique, a defender may be able to detect how and when an adversary collected the credentials. Whenever a defender seeks to engage with an adversary, operational safety is paramount. To maintain this safety, it is a best practice to monitor adversaries as they operate in an engagement environment. Additionally, the defender must be able to observe the adversary. Therefore, collection and detection activities can often be utilized even when a defender may have other strategic goals in mind.

Engage defines two approaches to make progress towards the Expose goal:<br>

**1. COLLECT**: Gather adversary tools, observe tactics, and collect other raw intelligence about the adversary’s activity.<br>

**2. DETECT**: Establish or maintain awareness regarding adversary activity. Detection activities focus on the defender’s ability to monitor adversary activity throughout an environment, often by creating high-fidelity detections.<br>

**Lets go through each adversary activity under collect and detect components respectively:**

**1. API MONITORING (ID: EAC0001)**: Monitor local APIs that might be used by adversary tools and activity.
 API monitoring entails recording internal OS function usage, including arguments and outcomes. Analyzing this data offers deeper insights into adversary activity beyond standard system monitoring, enabling high-fidelity threat detection.

**2. NETWORK MONITORING (ID: EAC0002)**: Monitor network traffic in order to detect adversary activity.
Network monitoring involves capturing network activity data, including server and firewall logs, which is sent to a centralized location for analysis. This analysis, whether automated or manual, helps defenders identify unusual traffic patterns and activities that may indicate adversary presence. It's crucial for situational awareness and requires careful pre-operational planning to ensure all critical network traffic is collected, aiding in detecting unexpected outbound traffic and known adversary C2 protocols.

**3. SOFTWARE MANIPULATION (ID: EAC0014)**: Make changes to a system’s software properties and functions to achieve a desired effect.
Software Manipulation empowers defenders to modify OS, file system, or software elements, impacting outputs and hindering functionality. For instance, defenders can alter outputs of discovery commands to obscure legitimate systems and reveal deceptive ones. They may also tweak password policy descriptions to mislead adversaries  
attempting brute-force attacks. This manipulation can divert adversary resources. To reduce software effectiveness, algorithms can be weakened to expose data. In extreme cases, software failures may be induced to thwart data deletion or artifact hiding. Such changes can treat adversary and user actions differently, allowing legitimate access while restricting adversaries.

**4. SYSTEM ACTIVITY MONITORING (ID: EAC0003)**: Collect system activity logs that can reveal adversary activity.
System log capture reveals logins, user actions, and events, providing defenders with valuable insights into adversary behavior and tools. These logs can be centrally collected for in-depth analysis, but careful planning is essential to determine what to collect without overwhelming with excess data. Understanding adversary tactics guides log selection. System activity monitoring is crucial for situational awareness and operational safety, requiring thoughtful pre-operational environment setup.

**5. INTRODUCED VULNERABILITIES (ID: EAC0023)**: Intentionally introduce vulnerabilities into the environment for the adversary to exploit. Deliberately introducing vulnerabilities allows defenders to influence adversary actions, motivating them to target specific resources or reveal preferences and capabilities. The objectives behind introducing vulnerabilities depend on operational goals, guiding the defender's strategy and decisions.

**6. LURES (ID: EAC0005)**: Deceptive systems and artifacts intended to serve as decoys, breadcrumbs, or bait to elicit a specific response from the adversary. Lures are used to provoke specific responses from adversaries, such as enabling or blocking their actions, or encouraging or discouraging particular behaviors. These baiting techniques come in various forms, such as credentials, files, system processes, and more. Regardless of the type, lures offer defenders opportunities to steer adversary actions in line with their operational objectives.

**7. MALWARE DETONATION (ID: EAC0013)**: Execute malware under controlled conditions to analyze its functionality. Malware can be safely activated in a controlled environment, but it requires clear objectives and safety protocols. The execution environment can vary from a standard malware analysis tool to a customized engagement setup. Depending on goals, this operation can yield new indicators of compromise (IOCs), reveal adversary tactics, or disrupt the adversary and their activities.

**8. NETWORK ANALYSIS (ID: EAC0004)**: Analyze network traffic to gain intelligence on communications between systems.
Network analysis, whether automated or manual, aims to uncover adversary activity like command and control (C2) traffic or data exfiltration. This involves capturing and examining network traffic, often requiring custom protocol decoder frameworks for complex encryption and custom protocols. Creating these decoders demands technical expertise but offers invaluable insights. For instance, decoders can decrypt network data, revealing adversary C2 or exfiltration actions, providing intelligence on communication channels, and enabling data manipulation to achieve operational goals in the future.





## Tools Used

...

## Installation and Configuration of Tpot Honeypot

Tpot Honeypot is a versatile tool designed to simplify the deployment and management of honeypots. Below are the steps to install and configure Tpot Honeypot:

1. **Clone Tpot Repository:**
   ```bash
   git clone https://github.com/telekom-security/tpotce.git
   ```

2. **Navigate to Tpot Directory:**
   ```bash
   cd tpotce
   ```

3. **Run Install Script:**
   ```bash
   ./install.sh
   ```

4. **Follow On-screen Instructions:**
   The installation script will guide you through the configuration process. Ensure to provide the necessary information when prompted.

5. **Start Tpot:**
   ```bash
   ./start.sh

Now, Tpot Honeypot is installed and running. You can access the Tpot web interface to monitor and analyze the honeypot's activities.

## Implementation and Mitre Engage Expose Goals

### 1. Network Monitoring (ID: EAC0002) using Suricata

...

### 2. System Activity Monitoring (ID: EAC0003) using Sysmon

...

### 3. Malware Detonation (ID: EAC0013) using VirusTotal

...

### 4. Network Analysis (ID: EAC0004) using Suricata

...

## Introduction to Wazuh

...

## Deploying Wazuh as an Agent in Tpot Honeypot and Integrating with Kibana Dashboard

...

## Integrating All Mitre Engage Expose Goals in Wazuh

...

## Generating Alerts for All Mitre Engage Expose Goals in Wazuh Dashboard

...

## Python Code to Automate Sending Alerts to Email 

...

## Findings and Analysis

...

## Acknowledgment

...

You can find the code related to this project [here](/code).

- [Project Structure](#project-structure)
- [Goals](#goals)
- [Tools Used](#tools-used)
- [Implementation Details](#implementation-details)
  - [1. Network Monitoring (ID: EAC0002) using Suricata](#1-network-monitoring-id-eac0002-using-suricata)
  - [2. System Activity Monitoring (ID: EAC0003) using Sysmon](#2-system-activity-monitoring-id-eac0003-using-sysmon)
  - [3. Malware Detonation (ID: EAC0013) using VirusTotal](#3-malware-detonation-id-eac0013-using-virustotal)
  - [4. Network Analysis (ID: EAC0004) using Suricata](#4-network-analysis-id-eac0004-using-suricata)
- [Findings and Analysis](#findings-and-analysis)
- [Acknowledgments](#acknowledgments)
- [License](#license)

## Project Structure

The repository is organized as follows:

- **docs/**: Contains the detailed report in markdown format.
- **code/**: Includes the code implementations and configurations.
- **figures/**: Stores visual aids and screenshots used in the report.

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

