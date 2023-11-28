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

#### My internship goal is to work on Expose component of the Mitre Engage matrix

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/d184cc15-469a-455d-9cb5-635478096459)

**Mitre Engage Expose component (ID: EGO0001)** is about discovering previously undetected adversaries engaging in one of two behaviors. First, the adversary may be attempting to gain access to the networks. Second, the adversary may be currently operating on the networks. Both categories of adversary behavior contain vulnerabilities that can be advantageous for a defender seeking to expose the adversary.

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
