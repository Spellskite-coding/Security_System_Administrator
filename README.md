# Security & Systems Administration

A collection of hands-on lab guides and production procedures covering **network engineering** (Cisco IOS / CCNA-level) and **secure systems administration** (Linux/FreeBSD hardening, SIEM deployment, SOC automation).

Each guide documents a real lab or homelab deployment end-to-end: architecture, full CLI/configuration listings, validation steps, and — where relevant — an incident log of the errors actually hit during the build and how they were fixed. Nothing here is theoretical fluff; every command was run against a real topology (Cisco Packet Tracer / physical Raspberry Pi / FreeBSD jail) before being written up.

All guides are provided as **standalone PDFs** — download the one(s) you're interested in and read them offline; no need to clone the whole repository.

## 🌐 `network-administration/`

Cisco IOS network engineering labs — VLANs, inter-VLAN routing, EtherChannel, ACLs, NAT/PAT, IPv6, and OSPFv3 — aligned with the CCNA 200-301 syllabus. Each guide includes the full topology diagram, an IP addressing matrix, complete CLI configuration listings for every device, a validation/test plan, and a troubleshooting log of the real errors encountered during the build.

| Guide | Topics |
|---|---|
| [`01-enterprise-multilayer-network-security.pdf`](./network-administration/01-enterprise-multilayer-network-security.pdf) | Multi-layer switching (SVIs), routed ports, PAT/NAT overload, and DHCP relay across a segmented enterprise topology (access switches, a Layer 3 core switch, an edge router, and a simulated ISP) |
| [`02-extended-acl-nat-pat-security.pdf`](./network-administration/02-extended-acl-nat-pat-security.pdf) | Perimeter security using Extended ACLs (Layer 3/4 filtering) combined with dynamic NAT/PAT overload for private-to-public address translation |
| [`03-intervlan-routing-etherchannel.pdf`](./network-administration/03-intervlan-routing-etherchannel.pdf) | Router-on-a-Stick inter-VLAN routing, LACP EtherChannel link aggregation for redundancy, and baseline device access security (enable secret, console password) |
| [`04-ipv6-intervlan-routing-ospfv3.pdf`](./network-administration/04-ipv6-intervlan-routing-ospfv3.pdf) | Pure IPv6 architecture: Router-on-a-Stick over IPv6, dynamic routing with OSPFv3, and the NDP-vs-ARP behavioral differences to expect on IPv6 |

**Toolchain:** Cisco Packet Tracer · Cisco IOS CLI

## 🛡️ `system-administration/`

Secure systems administration guides built on a real Raspberry Pi homeserver and a FreeBSD SOC lab: homelab hardening, native SIEM deployment, SOC-to-ITSM automation, and intrusion-detection/honeypot setups. Every procedure was run against a real machine (Raspberry Pi 4/8GB running Debian, or FreeBSD 14.3) rather than a purely theoretical writeup, and includes the practical errors hit along the way.

| Guide | Topics |
|---|---|
| [`01-raspberry-pi-homeserver-administration.pdf`](./system-administration/01-raspberry-pi-homeserver-administration.pdf) | Full homeserver build: network setup, Samba file sharing, Docker, UFW firewall, SSH hardening, automatic updates, self-hosted services (Minecraft, GLPI), automated backups — followed by a dedicated hardening pass (non-root Docker containers, SSH key auth, SSH 2FA) |
| [`02-wazuh-siem-deployment-raspberry-pi.pdf`](./system-administration/02-wazuh-siem-deployment-raspberry-pi.pdf) | Native (non-containerized) deployment of the full Wazuh stack — Indexer, Manager, Dashboard, Filebeat — on ARM64/Debian, including the OpenSearch credential hardening and the Filebeat pipeline fixes required to get alerts flowing end-to-end |
| [`03-wazuh-glpi-soc-automation.pdf`](./system-administration/03-wazuh-glpi-soc-automation.pdf) | Turns critical Wazuh SIEM alerts into qualified GLPI ITSM tickets automatically, cutting SOC mean-time-to-respond (MTTR) |
| [`04-samba-fim-clamav-active-response.pdf`](./system-administration/04-samba-fim-clamav-active-response.pdf) | Couples Wazuh's real-time File Integrity Monitoring (FIM/Syscheck) with a ClamAV daemon to automatically scan every file dropped on a Samba share and log/alert on detections — validated with an EICAR test file |
| [`05-freebsd-soc-suricata-cowrie-honeypot.pdf`](./system-administration/05-freebsd-soc-suricata-cowrie-honeypot.pdf) | A lightweight mini-SOC on FreeBSD 14.3 combining a Suricata IDS/IPS with a Cowrie SSH/Telnet honeypot, isolated inside a FreeBSD jail |

**Toolchain:** Debian (ARM64) · FreeBSD 14.3 · Docker · Wazuh · GLPI · ClamAV · Samba · Suricata · Cowrie · UFW · systemd

## About

Written and maintained by **Enzo Demaretz** — Security Engineer / CTI & DFIR Analyst, currently on a purple team.

Certifications: Blue Team Level 1 · Security Analyst Level 1 · Certified CyberDefender Level 1 · Security+ · Network+ · M2i Certified Pentester · Security 101 · TOSA DigComp · FormIP Network Administrator · Permis d'OSINT (Oscar Zulu Crew)

## License

Feel free to reuse and adapt these guides for your own learning or homelab. Attribution appreciated but not required.
