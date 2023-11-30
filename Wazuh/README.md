# Introduction to Wazuh
Wazuh is an open-source security information and event management (SIEM) platform designed to enhance threat detection, intrusion detection, and response capabilities for organizations. Rooted in a robust combination of log analysis, intrusion detection, vulnerability detection, and security information management, Wazuh provides a comprehensive solution for monitoring and managing security events across an entire IT infrastructure. Originally developed as OSSEC-HIDS (Host-based Intrusion Detection System), Wazuh has evolved into a scalable and extensible platform that aids organizations in fortifying their cybersecurity posture.

The core functionality of Wazuh revolves around its ability to collect, analyze, and correlate data from diverse security-related sources, such as logs, events, and configurations. With a focus on real-time threat detection and response, Wazuh helps organizations proactively identify and mitigate potential security incidents. Its open-source nature fosters community collaboration, enabling users to leverage a wealth of security expertise and contribute to the continuous improvement of the platform. Wazuh's user-friendly interface, coupled with its flexibility and powerful features, makes it a valuable asset for organizations seeking a robust and customizable solution to bolster their cybersecurity defenses.

# Installation
We can’t install Wazuh directly in Tpot , so I am building Wazuh in my t-pot as a Docker file.
Docker is an open platform for building, delivering, and running applications inside software containers. Docker containers package up software, including everything needed to run: code, runtime, system tools, system libraries, and settings. Docker enables separating applications from infrastructure. This guarantees that the application always runs the same, regardless of the environment the container is running on. Containers run in the cloud or on-premises.

We can deploy Wazuh as a single-node or multi-node stack.

- Single-node deployment: Deploys one Wazuh manager, indexer, and dashboard node.

- Multi-node deployment: Deploys two Wazuh manager nodes (one master and one worker), three Wazuh indexer nodes, and a Wazuh dashboard node.

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/1681e71d-3a14-438a-8c7d-98224b6ef239)

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/31086853-5101-49fb-92fd-3c2bbc92be9c)

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/ff23eab2-d443-4418-bc49-2dfe1da2dfb0)

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/c6e0b3ae-0546-483c-a317-1beb716a2f15)

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/0e440d8a-383c-4b95-b576-c85942e027b3)

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/3d80f1ed-dfd4-44ae-8c85-91477e05cc24)

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/0c293546-5b12-4a54-887a-5e7c2d6d45ea)

We require these ports for Wazuh to Run efficiently in our T-pot Honeypot

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/53d31f8e-7f6e-4689-b18a-1db7916e0758)

This is our Wazuh login page, we need to enter use credentials

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/1e0d48ad-0113-400d-9aba-dd02c3163f22)

This is our Wazuh Dashboard

Now let us add T-pot as in an agent in Wazuh

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/ac58fcb1-0884-4bbb-82b7-b5deede158a7)

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/28734470-d9c1-4915-86fa-efbadcd93e1b)

We are using these commands simultaneously to integrate T-pot as an agent in Wazuh

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/23aa514c-e557-4bfe-8d97-7cf85f8e4bca)

We can see that the T-pot agent is successfully created in Wazuh

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/52073ba4-e82f-4dde-add1-cd1557a062b6)

Refer [this](https://github.com/wazuh/wazuh#readme) for more detailed information on Wazuh

# Integration of Wazuh: Unifying All Goals in One Platform

## 1.	Integration of Suricata Logs in Wazuh: 
The integration of Suricata logs into the Wazuh platform enhances network security monitoring by incorporating the potent threat detection engine of Suricata. This dynamic analysis, utilizing a rule-based language for anomaly detection and signature analysis, broadens visibility into network-level events. Seamless assimilation into Wazuh enables timely detection of denial-of-service attacks, buffer overflows, and various malicious activities. This integration empowers security professionals with an expanded scope of threat intelligence, facilitating proactive identification and mitigation of potential network threats. The synergy between Suricata and Wazuh establishes a comprehensive approach to security, aligning with the evolving cybersecurity landscape and providing organizations with a consolidated view for more effective defense.

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/a5cbfcaa-8cdf-4afe-8570-fa546147ee34)

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/9b530e54-ebd6-420e-8300-e1de1e4c74ba)
Log alerts generated by suricata in Wazuh

Suricata Alets can be seen in Kibana Dashboard as well,as I have integrated Wazuh and Kibana [Click Here](https://wazuh.com/blog/detection-with-elastic-stack-integration/) to learn how to integrate.

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/22617941-75d1-4652-b754-eb1678099928)

## 2.	Incorporating Sysmon Logs into Wazuh: 
The incorporation of Sysmon logs into Wazuh provides a detailed insight into system-level activities, offering a comprehensive view of critical events like process creation, file modifications, and network connections. This integration enhances Wazuh's understanding of endpoint activities, facilitating seamless correlation between system-level events and network-level indicators. By leveraging Sysmon's granular data, security teams gain the ability to detect and investigate potential threats that encompass both network and endpoint components. This unified approach strengthens Wazuh's overall threat detection capabilities, empowering organizations to build a cohesive defense strategy against sophisticated cyber threats.

Go to Mangement and under Mangement, go to decoders

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/886906a9-cb69-44ec-a133-ff1c411e469e)

Go to custom decoders, as highlighted in the figure

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/8c93c3b4-c19c-4994-a98a-b7ac1754a7ed)

Modify the configuration file [Click Here](https://github.com/sandxxax/IIPP-Internship/blob/main/sysmon.xml) for configuration file

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/1a214bed-b88e-4332-a178-767e5a441b9b)

Test the Ruleset, to check if it works efficiently

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/008c558e-4cb3-4b34-a981-c57037d84696)

We can see that it works efficiently in monitoring sysmon Logs

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/5b9a8862-ac48-4a9a-a707-afe99a0677c8)

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/09cb03a4-5040-425b-81de-968b15b61c86)
Sysmon Alerts will be generated in Wazuh

## 3.	Integration of virus total in wazuh:
The integration of VirusTotal into Wazuh significantly strengthens the platform's threat detection capabilities by harnessing the comprehensive analysis provided by the VirusTotal API. Wazuh's File Integrity Monitoring (FIM) feature continuously monitors files and directories for changes, triggering alerts when suspicious activity is detected. This integration ensures a proactive response to potential threats by seamlessly engaging VirusTotal. When a change occurs, the integration extracts file hashes from the alert and initiates an HTTP POST request to compare them with the VirusTotal database. The resulting JSON response is then utilized to trigger alerts within the Wazuh environment, providing security teams with detailed insights into potentially malicious content and bolstering overall cybersecurity defenses.

By combining Wazuh's proactive monitoring capabilities with the extensive analysis capabilities of VirusTotal, this integration empowers organizations to swiftly identify and respond to emerging threats, contributing to a more resilient and secure cybersecurity posture. This comprehensive approach enables security teams to make informed decisions and prioritize responses based on a deeper understanding of the detected activity.

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/7504846b-b294-46eb-893e-ce42e2f16894)

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/393fa6ae-9ccf-46b1-a7fd-11bbe106d878)

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/beaa37b5-3503-4a9a-a3ec-dcbb1e6bb346)

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/2cc074dd-c79e-4242-a2bc-22eabee4723d)
Link to access this Python code is [Here]()

Add the python code in T-pot honeypot terminal 
![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/28fb2281-f9ab-444d-899f-6032be6b3808)

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/a836050d-9361-4c24-bc2b-a2a1cdc16bf9)

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/c45a9835-f7bf-475d-b9c3-7a6a6149e7bd)

Now Iam adding this code to my Ubuntu server, where I have locally set up my Wazuh Server

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/c4445e89-506c-4a15-b061-f446f91deb82)

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/d97c5e11-4745-42ae-b99d-824f3c9bdf56)

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/76af56c9-3c9d-4010-a2bc-373b787edef4)

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/448001b7-6e5d-40b5-9039-ca2026f627ab)

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/46f254ad-39f5-4690-9151-4ea0c6fe7111)

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/65c854e7-c56e-443f-aee5-7ea11080b79c)

In settings of Wazuh we need to turn on The Virus total 

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/1eccef3a-3800-47e4-ac31-c95afe55131d)

To Test Lets download an Anti-malware test file:

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/e05a4db2-ed71-4022-815e-e2727f50cd3f)

We can see that the wazuh alerts are generated:

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/d84def42-3efc-43d2-b7b1-77b68388628e)

We can see that the malicious files are deleted as well using the Pyhton code:

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/beb0558e-9eeb-4e45-987a-0fb43acd5fdd)

We can click on the link provided and analyse the malicious file

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/f50a913f-6304-4758-839c-a474d594dea0)

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/fd781446-59a8-4d2a-920e-0f8e0d28d1fc)

## Integration of Yara Rules in Wazuh for Malware Detonation:

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/99b57eb6-0ac0-4814-bb7f-7d583f39a45e)

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/e85c4b50-d928-4587-b7bd-a0c7483ec778)

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/3f740256-8b3b-4a39-b7e6-08d4440fc557)

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/1cc3b8d6-6fc8-4989-b342-a1621b4ef6f0)

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/3ae2938d-14e4-4ba6-9681-f65a56d0dcaa)

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/60d55e62-e481-4aa4-91c4-ea24283fab0b)

Link for the code is [here]()

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/632f0853-7434-4b0a-9398-683066372144)

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/a6729ca5-f132-48e9-9752-bcaa802841fe)

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/8f09a6b1-98d8-42de-b0cf-4ea3b5de0d6c)

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/f00eba66-616f-448a-aef9-4a4cfde1f7fa)

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/46db6a76-bbfd-42cd-9420-63bc7973a7e4)

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/dedb5b8b-695a-46dd-95f7-510c50d88542)

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/58f4aad7-0ae0-4a18-94b9-0c6eaea17d00)

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/d9e66ab2-66ee-4b55-9998-5028ac19e079)

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/f2b1c12d-390c-4e24-9247-63e5bf736c80)

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/3fbce9cf-4631-4769-9d0a-af584a6156fb)

Visualize the Alertsss!!!!


## 4.	Incorporating Suricata into Wazuh for Network Analysis:
The integration of network analysis through Suricata into the Wazuh platform signifies a pivotal advancement in bolstering overall cybersecurity defenses. Suricata, renowned for its prowess as both an Intrusion Detection System (IDS) and Intrusion Prevention System (IPS), offers real-time monitoring and analysis of network traffic. By seamlessly incorporating Suricata logs into Wazuh, organizations gain a comprehensive view of their network's security landscape, empowering them to identify and respond to potential threats swiftly. This integration enables Wazuh to leverage Suricata's rule-based language, combining anomaly, protocol, and signature inspection methods for the detection of diverse malicious activities, including denial-of-service attacks, buffer overflows, and various other network-level threats. The enriched threat intelligence from Suricata enhances Wazuh's capabilities, allowing security professionals to proactively defend against sophisticated cyber threats by correlating network-level events with broader security indicators, ultimately fostering a more resilient and adaptive security posture. Network Packets and logs can be analyzed in detail for more information about the attacker.

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/a6c6d7ac-aeb6-4631-b1b1-566be66fcaad)

We can click on any packet to analyze them in detail in Wazuh

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/eb11c4cc-a413-4a9a-8ff0-521d76d2a2a1)


