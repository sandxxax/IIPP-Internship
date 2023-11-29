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
tanner<br>
... alongside the following tools ...**

**Cockpit** for a lightweight and secure WebManagement and WebTerminal.<br>
**Cyberchef** a web app for encryption, encoding, compression and data analysis.<br>
**Elastic Stack** to beautifully visualize all the events captured by T-Pot.<br>
**Elasticvue** a web front end for browsing and interacting with an Elasticsearch cluster.<br>
**Fatt** a pyshark based script for extracting network metadata and fingerprints from pcap files and live network traffic.<br>
**T-Pot-Attack-Map** a beautifully animated attack map for T-Pot.<br>
**P0f** is a tool for purely passive traffic fingerprinting.<br>
**Spiderfoot** an open source intelligence automation tool.<br>
**Suricata** a Network Security Monitoring engine.<br>

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
- a working, non-proxied, internet connection for an installation to succeed.<br>

## Required Ports
Besides the ports generally needed by the OS, i.e. obtaining a DHCP lease, DNS, etc. T-Pot will require the following ports for incoming / outgoing connections. Review the [T-Pot Architecture](https://github.com/telekom-security/tpotce/blob/master/doc/architecture.png) for a visual representation. Also some ports will show up as duplicates, which is fine since used in different editions.

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

Ports and availability of SaaS services may vary based on your geographical location. Also during the first install outgoing ICMP / TRACEROUTE is required additionally to find the closest and fastest mirror to us.

For some honeypots to reach full functionality (i.e. Cowrie or Log4Pot) outgoing connections are necessary as well, in order for them to download the attackers malware.

# Installation
The T-Pot installation is offered in different variations. While the overall installation of T-Pot is straightforward it heavily depends on a working, non-proxied (unless you made modifications) up and running internet connection (also see required outgoing ports). If these conditions are not met the installation will fail! either during the execution of the Debian Installer, after the first reboot before the T-Pot Installer is starting up or while the T-Pot installer is trying to download all the necessary dependencies.

### ISO Based Installation

Installing T-Pot based on an ISO image follows the routine of any other ISO-based Linux distribution. You can either run it on hardware by copying the ISO file to a USB drive (e.g., with Etcher) or mount the ISO image as a virtual drive in one of the supported hypervisors.

#### Download ISO Image

On the [T-Pot release page](https://github.com/telekom-security/tpotce/releases), we will find two prebuilt ISO images for download: `tpot_amd64.iso` and `tpot_arm64.iso`. Both are based on Debian 11 for x64 / arm64 based hardware.

#### Creating our own ISO Image

If we want to modify T-Pot for your environment or take control of the process, you can use the ISO Creator to build your own ISO image.

**Requirements to create the ISO image:**
- Debian 11 as the host system (others may work but remain untested)
- 4GB of free RAM
- 32GB of free storage
- A working internet connection

**Steps to create the ISO image:**
1. Clone the repository and enter it.
   ```bash
   git clone https://github.com/telekom-security/tpotce
   cd tpotce
   ```
2. Run `makeiso.sh` to build the ISO image. The script will download and install dependencies necessary to build the image. It will further download the Debian Netiso installer image (~50-150MB) on which T-Pot is based.
   ```bash
   sudo ./makeiso.sh
   ```
3. After a successful build, you will find the ISO image `tpot_[amd64,arm64].iso` along with a SHA256 checksum `tpot_[amd64,arm64].sha256` based on your architecture choice in your folder.

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/2238aaea-3fec-4d57-b2db-52a83651ca17)

## Post Install

In some cases, it is necessary to install T-Pot after you installed Debian. For example, your provider does not offer an ISO-based installation, you need special drivers for your hardware, or you want to experiment with ARM64 hardware not supported by the ISO image. In that case, you can clone the T-Pot repository on your own. Make sure you understand the different user types before setting up your OS.

### Download Debian Netinstall Image

Since T-Pot is based on the Debian Netinstall Image (amd64, arm64), it is heavily recommended you use this image if possible. It is very lightweight and only offers to install core services.

### Post Install User Method

The post-install method must be executed by the root (sudo su -, su -). Follow these steps:

```bash
git clone https://github.com/telekom-security/tpotce
cd tpotce/iso/installer/
./install.sh --type=user
```

The installation will start, and you can proceed to the T-Pot Installer section.

### Post-Install Auto Method

You can also let the installer run automatically if you provide your own `tpot.conf`. An example is available in `tpotce/iso/installer/tpot.conf.dist`. This should make things easier if you want to automate the installation, for example, with Ansible.

Follow these steps while adjusting `tpot.conf` to your needs:

```bash
git clone https://github.com/telekom-security/tpotce
cd tpotce/iso/installer/
cp tpot.conf.dist tpot.conf
./install.sh --type=auto --conf=tpot.conf
```
Adjust the configuration to suit the needs. The installer will run automatically.

- The individual Dockerfile and configuration files of cowrie honeypot is located in [this folder](https://github.com/sandxxax/IIPP-Internship/tree/main/T-pot%20Honeypot%20CE/cowrie).
 
- Refer this [docker folder](https://github.com/telekom-security/tpotce/tree/02098f9b769dc7d6c8ac3c61538b969fa539016c/docker) for configuration files of all the honeypots in T-pot CE.

## First Start
Once the T-Pot Installer successfully finishes, the system will automatically reboot and you will be presented with the T-Pot login screen. Logins are according to the User Types:

- user: [tsec or <os_username>]
- pass: [password]
You can login from your browser and access Cockpit: https://<your.ip>:64294 or via SSH to access the command line: ssh -l [tsec,<os_username>] -p 64295 <your.ip>:

- user: [tsec or <os_username>]
- pass: [password]
You can also login from your browser and access the Nginx (T-Pot Web UI and tools): https://<your.ip>:64297

- user: [<web_user>]
- pass: [password]

  ![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/60bc755d-d4cc-4441-b5c2-2bd6e8ee4568)

  ![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/e5135781-82f7-472f-b4e5-c81796e6cc05)

## Attack Map
On the T-Pot Landing Page just click on Attack Map and you will be forwarded to the Attack Map.

Since the Attack Map utilizes web sockets we need to re-enter the  <web_user> credentials.
 
![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/52d9f843-ba72-4510-af74-5dfc41d920b8)

## SSH and Cockpit
According to the User Types you can login from your browser and access Cockpit: https://<your.ip>:64294 or via SSH to access the command line: ssh -l [tsec,<os_username>] -p 64295 <your.ip>:

user: [tsec or <os_username>]
pass: [password]
Especially if you do not have a SSH client at hand and still want to access the machine with a command line option you can do so by accessing Cockpit. You can also add two factor authentication to Cockpit just by running 2fa.sh on the command line.

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/6b1eb9d1-1f7c-4bdf-a0f4-1f197bfac921)

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/ea8f4eac-562d-4b32-86d7-b03065edf7bb)

## Kibana Dashboard
On the T-Pot Landing Page just click on Kibana and you will be forwarded to Kibana. You can select from a large variety of dashboards and visualizations all tailored to the T-Pot supported honeypots.

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/b5e1f601-0e16-4284-a9d6-189bb52f27c7)

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/f39c9f43-2210-4608-b09a-04f6cb70e600)

We can even see the brute force passwords which have been tried to gain unauthorised access.

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/8d715bda-ac3b-4401-8ab6-8e5115a68a59)

Let's do Nmap Scan to see how our honeypot looks to the attacker when he does N-map scan!!

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/acb5a09c-c2bf-4a45-9152-7c3533513398)

We can see that the attacker finds so many open ports, so he will be alerted that it is a honeypot!!!<br>

So what can we do to make it look like a actual system?

Lets modify the configuration file and comment the honeypot which we feel not necessary so the we can reduce the number of ports that are open.

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/6f9d38b9-d238-49cd-9ad6-367de6f296f8)

Let us keep Cowrie honeypot as it is needed to implement our Mitre Enagage goals.

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/cd7adc11-63b0-4ea7-b68e-b49072dd7633)

We can see adversaries trying to attack our cowrie honeypot through port 23 which is used for telnet:

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/b1a368f7-cfc3-464e-aa58-e97dfba63fb0)

We can go to networking in our T-pot cockpit to analyse the ports and interfaces used by various honeypots
Here we can see that our cowrie is using:
- 172.18.0.1/16 as ip address and
-  br-8b045e5dO8eb as interface

![image](https://github.com/sandxxax/IIPP-Internship/assets/122590982/0530d244-8dc0-4c18-83e4-b9ed018c4014)

We have successfully installed and configured our T-pot honeypot!!<br>

Now we can implement our Mitre engage goals in our T-pot Honeypot, To continue reading on implementation of Mitre enage goals [Click Here](https://github.com/sandxxax/IIPP-Internship/blob/main/README.md#implementation-of-mitre-engage-expose-goals)























