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

To read more on Mitre engage [Click Here](https://github.com/sandxxax/IIPP-Internship/blob/main/Mitre%20Engage/README.md) 



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

