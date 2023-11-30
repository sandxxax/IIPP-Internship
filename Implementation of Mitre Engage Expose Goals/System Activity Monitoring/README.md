# System Activity Monitoring (ID: EAC0003):
- System Activity Monitoring is a pivotal cybersecurity measure that involves collecting comprehensive system activity logs, offering a detailed account of user logins, actions, and various events within an environment. This proactive approach provides defenders with invaluable insights into potential adversary activities and the tools employed, forming a crucial aspect of threat detection and response. Snort and it’s usage in system monitoring  helped me understand the overall importance of this activity. The captured logs, when centralized for in-depth analysis, become a powerful tool in understanding and mitigating potential security threats. However, the effectiveness of this monitoring strategy relies on meticulous planning to strike a balance between the depth of data collection and avoiding data overload, ensuring that defenders can focus on relevant information without being overwhelmed.
  
- These system activity logs play a crucial role in enhancing situational awareness and operational safety. They contribute to a comprehensive understanding of adversary tactics, guiding the strategic selection of logs to monitor. The careful pre-operational environment setup is paramount to the success of system activity monitoring, as it ensures that the collected data is not only relevant but also manageable for analysis. By incorporating this measure, organizations can significantly strengthen their security posture, enabling a proactive response to potential threats and reinforcing the resilience of their cybersecurity infrastructure.

## System Activity Monitoring using Sysmon:
Sysmon, a powerful system monitoring tool, plays a crucial role in delivering comprehensive insights into the activities of both Windows and Linux systems. Its primary strength lies in its capability to log intricate details related to process creation, including comprehensive command lines for both the current and parent processes. This feature provides security professionals with a granular understanding of system activities. Sysmon further enhances its forensic capabilities by recording hash information, utilizing algorithms like SHA1, MD5, SHA256, or IMPHASH. This hashing mechanism facilitates precise identification and verification of file integrity, contributing significantly to robust security measures.

Beyond process-related information, Sysmon extends its logging capabilities to encompass critical events such as driver or DLL loading, capturing essential details like signatures and hashes. The tool also excels in logging network connections, offering a wealth of information such as source process, IP addresses, port numbers, hostnames, and port names. Sysmon's adeptness in detecting changes in file creation time adds an additional layer of security, making it effective in uncovering potential malware activities attempting to manipulate timestamps. With features like automatic configuration reloading, dynamic rule filtering, and early event generation during the boot process, Sysmon emerges as a versatile solution for security professionals. Its capacity to monitor and analyze activities spans from process execution to network connections, providing a comprehensive and proactive approach to cybersecurity.

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/19dda17a-5112-4875-9856-e93811617eeb)

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/3c40ab73-8e01-48b4-aaed-639fddecdad9)

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/94448819-6f2a-48a8-9615-71d46e382c60)

## Installing and configuring Sysmon in T-pot CE honeypot:

The installation and configuration of Sysmon within the T-Pot CE honeypot environment involve a series of steps to bolster the system's monitoring and logging capabilities. Sysmon, a robust system monitoring tool, is instrumental in providing detailed insights into system activities. To integrate Sysmon into T-Pot CE, security practitioners can follow a systematic approach. The process typically begins with downloading the Sysmon binary and extracting it within the T-Pot CE environment. Subsequently, security professionals can execute the Sysmon installation command, configuring the tool to log pertinent information such as process creation, file integrity hashes, and network connections. The configuration process may include specifying hash algorithms, defining logging rules, and tailoring Sysmon settings to align with the honeypot's security objectives.

Once Sysmon is successfully installed and configured, security practitioners can initiate its execution to commence real-time monitoring of system activities within the T-Pot CE environment. The tool's ability to log detailed information about process execution, loaded DLLs, and network connections enhances the honeypot's visibility into potential threats. The integration of Sysmon in T-Pot CE contributes to a more comprehensive and proactive security posture, allowing security teams to detect and analyze malicious activities effectively. Additionally, the Sysmon logs can be integrated into centralized logging solutions, providing security professionals with a centralized and streamlined view of the honeypot's security landscape. Overall, the deployment of Sysmon in the T-Pot CE honeypot environment is a strategic measure to fortify the system against potential threats and augment the capabilities of security practitioners in monitoring and analyzing adversarial activities.
To understand in a detail way, [Click here](https://github.com/Sysinternals/SysmonForLinux/blob/main/INSTALL.md)

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/7764f78a-3513-4367-896c-9c02be329ce5)

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/517405a6-dd79-4aa0-a1d0-47c7b05248e1)

Sysmon Logs generated in T-pot Honeypot:

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/4f3c811e-86a8-4150-85f7-375fd8feaa6d)

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/33879500-08aa-4591-8bc6-e2f3de411a7c)

We are modifying Sysmon logs to display in user friendly manner:

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/a9c9f9f0-41c5-4d87-9acb-b17019d39902)

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/a3af2ad4-e51c-4b02-957d-f2582fc56a84)

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/62316010-297d-4521-b425-b6693d5f17b0)

In T-pot dashboard, under logs we can monitor Sysmon logs:

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/77c02e7d-22a3-4513-829c-cec2d5d834ac)

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/b6902463-5479-4157-9bae-76f253333b24)

We can click on logs to analyse them in detail.

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/994f9cba-620d-43af-8901-05ee0dfdc881)

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/4eb8c4c2-b35f-4ce2-a9df-41a639a4f92f)

## Incorporating Sysmon Logs into Wazuh: 
The incorporation of Sysmon logs into Wazuh provides a detailed insight into system-level activities, offering a comprehensive view of critical events like process creation, file modifications, and network connections. This integration enhances Wazuh's understanding of endpoint activities, facilitating seamless correlation between system-level events and network-level indicators. By leveraging Sysmon's granular data, security teams gain the ability to detect and investigate potential threats that encompass both network and endpoint components. This unified approach strengthens Wazuh's overall threat detection capabilities, empowering organizations to build a cohesive defense strategy against sophisticated cyber threats.

Go to Mangement and under Mangement, go to decoders

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/886906a9-cb69-44ec-a133-ff1c411e469e)

Go to custom decoders, as highlighted in the figure

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/8c93c3b4-c19c-4994-a98a-b7ac1754a7ed)

- Modify the configuration file [Click Here](https://github.com/sandxxax/IIPP-Internship/blob/main/sysmon.xml) for configuration file

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/1a214bed-b88e-4332-a178-767e5a441b9b)

Test the Ruleset, to check if it works efficiently

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/008c558e-4cb3-4b34-a981-c57037d84696)

We can see that it works efficiently in monitoring sysmon Logs

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/5b9a8862-ac48-4a9a-a707-afe99a0677c8)

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/09cb03a4-5040-425b-81de-968b15b61c86)
Sysmon Alerts will be generated in Wazuh
