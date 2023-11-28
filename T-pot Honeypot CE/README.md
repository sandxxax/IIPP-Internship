# T-Pot CE Honeypot Overview
T-Pot is the all in one, optionally distributed, multiarch (amd64, arm64) honeypot plattform, supporting 20+ honeypots and countless visualization options using the Elastic Stack, animated live attack maps and lots of security tools to further improve the deception experience.

## Technical Concept
T-Pot is based on the Debian 11 (Bullseye) Netinstaller and utilizes docker and docker-compose to reach its goal of running as many tools as possible simultaneously and thus utilizing the host's hardware to its maximum.

### T-Pot offers docker images for the following honeypots ...

**adbhoney,
ciscoasa,
citrixhoneypot,
conpot,
cowrie,
ddospot,
dicompot,
dionaea,
elasticpot,
endlessh,
glutton,
heralding,
hellpot,
honeypots,
honeytrap,
ipphoney,
log4pot,
mailoney,
medpot,
redishoneypot,
sentrypeer,
snare,
tanner
... alongside the following tools ...**

**Cockpit** for a lightweight and secure WebManagement and WebTerminal.
**Cyberchef** a web app for encryption, encoding, compression and data analysis.
**Elastic Stack** to beautifully visualize all the events captured by T-Pot.
**Elasticvue** a web front end for browsing and interacting with an Elasticsearch cluster.
**Fatt** a pyshark based script for extracting network metadata and fingerprints from pcap files and live network traffic.
**T-Pot-Attack-Map** a beautifully animated attack map for T-Pot.
**P0f** is a tool for purely passive traffic fingerprinting.
**Spiderfoot** an open source intelligence automation tool.
**Suricata** a Network Security Monitoring engine.

## Technical Architecture

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/1eb6d50a-2667-4007-9ada-8c6806658732)

## Services
T-Pot offers a number of services which are basically divided into five groups:

### 1. System services provided by the OS
- SSH for secure remote access.
- Cockpit for web based remote access, management and web terminal.
### 2. Elastic Stack
- Elasticsearch for storing events.
- Logstash for ingesting, receiving and sending events to Elasticsearch.
- Kibana for displaying events on beautifully rendered dashboards.
### 3.Tools
- NGINX provides secure remote access (reverse proxy) to Kibana, CyberChef, Elasticvue, GeoIP AttackMap and Spiderfoot.
- CyberChef a web app for encryption, encoding, compression and data analysis.
- Elasticvue a web front end for browsing and interacting with an Elasticsearch cluster.
- T-Pot Attack Map a beautifully animated attack map for T-Pot.
- Spiderfoot an open source intelligence automation tool.
### 4.Honeypots
- A selection of the 22 available honeypots based on the selected edition and / or setup.
### 5.Network Security Monitoring (NSM)
- Fatt a pyshark based script for extracting network metadata and fingerprints from pcap files and live network traffic.
- P0f is a tool for purely passive traffic fingerprinting.
- Suricata a Network Security Monitoring engine.

## User Types
During the installation and during the usage of T-Pot there are two different types of accounts you will be working with. Make sure you know the differences of the different account types, since it is by far the most common reason for authentication errors and fail2ban lockouts.

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/6e0c77be-b6b3-4879-86dd-9033bdb81e11)

## System Requirements
Depending on the installation setup, edition, installing on real hardware, in a virtual machine or cloud there are different kind of requirements to be met regarding OS, RAM, storage and network for a successful installation of T-Pot (you can always adjust /opt/tpot/etc/tpot.yml to your needs to overcome these requirements).

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/91fcc54e-5fe8-456f-b73f-c2b100c99cbf)

All T-Pot installations will require,

- an IP address via DHCP
- a working, non-proxied, internet connection for an installation to succeed.

## Required Ports
Besides the ports generally needed by the OS, i.e. obtaining a DHCP lease, DNS, etc. T-Pot will require the following ports for incoming / outgoing connections. Review the [T-Pot Architecture](![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/1eb6d50a-2667-4007-9ada-8c6806658732)) for a visual representation. Also some ports will show up as duplicates, which is fine since used in different editions.

| Port          | Protocol | Direction | Description                                               |
|--------------|----------|------------|-----------------------------------------------------------|
| 80, 443      | tcp      | outgoing   | T-Pot Management: Install, Updates, Logs (Debian, GitHub, DockerHub, PyPi, Sicherheitstacho, etc.) |
| 64294        | tcp      | incoming   | T-Pot Management: Access to Cockpit                         |
| 64295        | tcp      | incoming   | T-Pot Management: Access to SSH                             |
| 64297        | tcp      | incoming   | T-Pot Management Access to NGINX reverse proxy             |
| 5555         | tcp      | incoming   | Honeypot: ADBHoney                                         |
| 5000         | udp      | incoming   | Honeypot: CiscoASA                                          |
| 8443         | tcp      | incoming   | Honeypot: CiscoASA                                          |
| 443          | tcp      | incoming   | Honeypot: CitrixHoneypot                                    |
| 80, 102, 502, 1025, 2404, 10001, 44818, 47808, 50100 | tcp | incoming | Honeypot: Conpot      |
| 161, 623     | udp      | incoming   | Honeypot: Conpot                                            |
| 22, 23       | tcp      | incoming   | Honeypot: Cowrie                                            |
| 19, 53, 123, 1900 | udp  | incoming   | Honeypot: Ddospot                                            |
| 11112        | tcp      | incoming   | Honeypot: Dicompot                                           |
| 21, 42, 135, 443, 445, 1433, 1723, 1883, 3306, 8081 | tcp | incoming | Honeypot: Dionaea  |
| 69           | udp      | incoming   | Honeypot: Dionaea                                            |
| 9200         | tcp      | incoming   | Honeypot: Elasticpot                                         |
| 22           | tcp      | incoming   | Honeypot: Endlessh                                           |
| 21, 22, 23, 25, 80, 110, 143, 443, 993, 995, 1080, 5432, 5900 | tcp | incoming | Honeypot: Heralding |
| 21, 22, 23, 25, 80, 110, 143, 389, 443, 445, 1080, 1433, 1521, 3306, 5432, 5900, 6379, 8080, 9200, 11211 | tcp | incoming | Honeypot: qHoneypots |
| 53, 123, 161  | udp      | incoming   | Honeypot: qHoneypots                                         |
| 631          | tcp      | incoming   | Honeypot: IPPHoney                                           |
| 80, 443, 8080, 9200, 25565 | tcp | incoming | Honeypot: Log4Pot  |
| 25           | tcp      | incoming   | Honeypot: Mailoney                                           |
| 2575         | tcp      | incoming   | Honeypot: Medpot                                             |
| 6379         | tcp      | incoming   | Honeypot: Redishoneypot                                      |
| 5060         | udp      | incoming   | Honeypot: SentryPeer                                         |
| 80           | tcp      | incoming   | Honeypot: Snare (Tanner)                                    |



































































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

