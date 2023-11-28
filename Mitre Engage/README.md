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

## Engage Goals

The Engage actions are further subdivided into Goals, Approaches, and Activities. Across the top of the Matrix are the Engage Goals. Goals are the high-level outcomes we would like our operation to accomplish. The Engage Goals can be adapted to fit a spectrum of use cases and objectives based on needs, resources, and authorities. For example, the deception opportunities available to a corporate defender will differ greatly than those available to a U.S. Cyber Command operator. However, in either case, there are opportunities within each goal to operate safely and legally within the bounds of the user’s authorities.

### The Prepare and Understand goals focus on the inputs and outputs of an operation. 

While the Matrix is linear, it is essential to understand that within and across operations, this process is cyclical. For each operation, we will be continuously iterating and improving as the operation progresses. This iterative cycle will demand that you constantly think about how to Prepare for the next set of operational actions and how to Understand operational outcomes in the context of your larger cyber strategy. This process ensures that we are constantly aligning and realigning your actions to drive progress towards our Engagement Goals.

### The Engagement Goals are Expose, Affect, and Elicit.

These Goals focus on actions taken against your adversary. Let’s explore each of these Goals in more detail.

1. **Expose:** We can expose adversaries on the network by using deceptive activities to provide high fidelity alerts when adversaries are active in the engagement environment. There is often overlap between practices that are considered good cyber hygiene and techniques used to expose adversaries on the network.

    - Example: If a defender places decoy credentials on the network and monitors the system logs for the use of those credentials elsewhere in the network, that is an example of using Lures and System Monitoring to expose the adversary using adversary engagement activities.

2. **Affect:** We can affect adversaries by having a negative impact on their operations. Affect activities are ultimately about changing the cost-value proposition in cyber operations for the adversary.

    - Example: The defender may want to increase the adversary’s cost to operate or drive down the value they derive from their operations. For instance, the defender can negatively impact the adversary’s on-network operations to drive up the resource cost of doing operations by slowing down or selectively resetting connections to impact exfiltration.

3. **Elicit:** We can elicit information about the adversary to learn about their tactics, techniques, and procedures (TTPs). By creating an engagement environment that is uniquely tailored to engage with specific adversaries, the defenders can encourage the adversary to reveal additional or more advanced capabilities.

    - Example: Observing an adversary as they operate can provide actionable cyber threat intelligence (CTI) data to inform the defender’s other defenses

For a given operation, we will define one or more operational objectives. These objectives are the specific, measurable actions that will enable you to accomplish our organization’s larger adversary engagement goals. For example, our goal may be to fill in a known gap in your knowledge of a specific APT. Over the course of one or more adversary engagement operations, we can make progress towards this goal by setting operational objectives such as “Identify at least X many new indicators” or “engage the adversary to obtain a second stage malware file.” Goals set direction; objectives take steps in that direction.

It is also important to remember that, while we identify three high-level Engagement Goals, where adversary engagement fits into our organization’s cyber strategy may mean we have organizational goals that fall on a spectrum or build on one another. For example, an operation might allow the adversary to engage freely for a time to elicit new TTPs, before identifying an opportunity to influence or control an adversary’s actions to meet a larger strategic goal for your organization. When using the Engage Matrix to plan an operation, remember that these categories are intended to provide a language through which our goals can be clearly articulated and not to limit or box in your use of adversary engagement operations.

### 2.1.3 Engage Approaches

The next row contains the Engage Approaches. Approaches lets us make progress towards our selected goal.

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/2734e399-6ac0-4ce5-9d42-95000cb79236)

**Strategic Approaches** helps us to focus on the steps we must complete before, during, and after an operation to ensure that your activities are aligned with our overall strategy. Strategic Approaches help ensure that our operations of today inform our operations of tomorrow.

**Engagement Approaches** helps us to identify what actions we would like to take against your adversary and help you to drive progress towards that impact. As seen in the Engage matrix, there are nine approaches to drive progress towards various goals:

1. **Plan:** Identify and align an operation with a desired end-state.

2. **Collect:** Gather adversary tools, observe tactics, and collect other raw intelligence about the adversary's activity.

3. **Detect:** Establish or maintain awareness of adversary activity.

4. **Prevent:** Stop all or part of the adversary's ability to conduct their operation as intended.

5. **Direct:** Encourage or discourage the adversary from conducting their operation as intended.

6. **Disrupt:** Impair the adversary's ability to conduct their operation as intended.

7. **Reassure:** Add authenticity to deceptive components to convince an adversary that an environment is real.

8. **Motivate:** Encourage the adversary to conduct part or all of their mission.

9. **Analyze:** Retrospective review of information gained from an operation.

These Engage Approaches provide a structured way to plan and execute your adversary engagement strategies. Whether we are looking to gather intelligence, prevent adversary operations, or influence their behavior, the Engage Matrix offers a comprehensive framework for achieving strategic cyber outcomes.

### My internship goal is to work on Expose component of the Mitre Engage matrix

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
