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
 SSH for secure remote access.
 Cockpit for web based remote access, management and web terminal.
### 2. Elastic Stack
 Elasticsearch for storing events.
 Logstash for ingesting, receiving and sending events to Elasticsearch.
 Kibana for displaying events on beautifully rendered dashboards.
### 3.Tools
 NGINX provides secure remote access (reverse proxy) to Kibana, CyberChef, Elasticvue, GeoIP AttackMap and Spiderfoot.
 CyberChef a web app for encryption, encoding, compression and data analysis.
 Elasticvue a web front end for browsing and interacting with an Elasticsearch cluster.
 T-Pot Attack Map a beautifully animated attack map for T-Pot.
 Spiderfoot an open source intelligence automation tool.
### 4.Honeypots
 A selection of the 22 available honeypots based on the selected edition and / or setup.
### 5.Network Security Monitoring (NSM)
 Fatt a pyshark based script for extracting network metadata and fingerprints from pcap files and live network traffic.
 P0f is a tool for purely passive traffic fingerprinting.
 Suricata a Network Security Monitoring engine.























































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

