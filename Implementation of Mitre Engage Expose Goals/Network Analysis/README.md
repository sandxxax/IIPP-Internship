# Network Analysis (ID: EAC0004):
- Network Analysis is a crucial component of cybersecurity that involves the thorough examination of network traffic to extract valuable intelligence on communications between systems. Malicious traffic analysis  is the critical aspect of this activity. The primary goal is to uncover potential adversary activities, such as command and control (C2) traffic or data exfiltration, which are indicative of malicious intent. This process requires capturing and scrutinizing network traffic, often necessitating the development of custom protocol decoder frameworks capable of handling complex encryption and proprietary protocols. While creating these decoders demands technical expertise, the insights gained from such efforts are invaluable in understanding and mitigating potential threats.
  
- The complexity of modern cybersecurity threats often requires advanced techniques for deciphering encrypted network data. Through network analysis, security professionals can employ custom decoders to decrypt network data, exposing adversary C2 actions or data exfiltration attempts. This level of insight not only aids in understanding communication channels used by adversaries but also enables defenders to manipulate data for strategic operational goals in the future. By investing in network analysis capabilities, organizations enhance their ability to detect, analyze, and respond to evolving cyber threats, fortifying their overall cybersecurity posture in an ever-changing digital landscape.

## Network Analysis using Suricata:
- Suricata, as a versatile and open-source threat detection engine, plays a pivotal role in network analysis by combining Intrusion Detection System (IDS), Intrusion Prevention System (IPS), and network security monitoring capabilities. Network analysis using Suricata involves scrutinizing network traffic in real-time, making it a powerful tool for identifying and mitigating potential security threats. The engine utilizes a rule-based language that employs anomaly detection, protocol analysis, and signature inspection methods to detect a wide range of malicious activities within network traffic.

- One of Suricata's key strengths lies in its ability to operate as both an IDS and IPS, allowing organizations to actively monitor and prevent security incidents. Suricata can spot and alert administrators to various network-based attacks, including denial-of-service (DoS) attacks, distributed DoS (DDoS) attacks, Common Gateway Interface (CGI) attacks, buffer overflows, and stealth port scans. Its rule-based approach enables the definition of specific criteria for identifying malicious network activities, ensuring a tailored and adaptive defense against evolving threats. Additionally, Suricata supports multiple modes, such as packet sniffer for real-time traffic display, packet logger for network traffic debugging, and network intrusion detection to match network traffic against predefined signatures and take specified actions, providing organizations with a comprehensive solution for proactive network security analysis.

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/4840dac5-b70c-4507-aca8-16d2e6097e94)

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/4877b4c6-3071-477e-b69a-3987d5ba9d0c)

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/3e45d264-5a13-4fe0-8eaa-070eed430c00)

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/52e286af-d1aa-4dfa-8ee4-033210dfadae)

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/83d64016-ed4b-4cc9-ac31-35c1eddf9d4f)

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/dcf710fc-6e9f-416d-9e2d-c5d3b57631af)

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/635e7a86-114e-49fa-ae76-6680dfaf1c1a)

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/c63a30c2-9b2b-4f9b-92e7-6414ec47ab8a)

## Integration of Suricata Logs in Wazuh:
The integration of Suricata logs into the Wazuh platform enhances network security monitoring by incorporating the potent threat detection engine of Suricata. This dynamic analysis, utilizing a rule-based language for anomaly detection and signature analysis, broadens visibility into network-level events. Seamless assimilation into Wazuh enables timely detection of denial-of-service attacks, buffer overflows, and various malicious activities. This integration empowers security professionals with an expanded scope of threat intelligence, facilitating proactive identification and mitigation of potential network threats. The synergy between Suricata and Wazuh establishes a comprehensive approach to security, aligning with the evolving cybersecurity landscape and providing organizations with a consolidated view for more effective defense.

Alert generated in Wazuh:
![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/dc6b4039-7f34-413e-8b29-d1f6276c48cd)

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/128e941d-2199-4d4a-b237-a1c8247d8d40)

We can do network analysis of each packet:

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/cc6d99c9-940a-401c-a1b3-7b248e2a47d4)

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/208ff8ba-0f74-4131-89b5-4c75fb9ee5fb)

## Automation of E-mail Alerts:

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/ca399148-8a43-4d21-9d21-542ca43c9e36)

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/76ef4175-a271-4e4b-b82e-8efbbeb08315)

Executing Python code in T-pot Terminal:

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/136f9f23-0bd1-4371-8c2b-1655cad68a51)

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/161ebc99-ca10-4e81-9371-c55e12183856)

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/477db8e8-a4bf-4477-9bef-942af083e6e8)

We can see that the emails are sent:

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/de37b4df-492a-45ea-9cd5-58aa251b393a)

We can see the email alerts generated:

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/b9100e35-a68b-4cf8-a669-aba54b930632)

