# SOC-home-lab
Hands-on SOC homelab project documenting the deployment of an OPNsense multi-zone network, Wazuh SIEM on RHEL 10, Active Directory, and adversary simulation with Kali Linux.

Executive Summary 
-------------------------------
A multi-zone Security Operations Center (SOC) homelab built using VMware Workstation. The purpose of this project is to simulate an enterprise network environment, implement defensive network segmentation, centralize security logging with Wazuh SIEM, and practice real-world adversary simulation and threat hunting.

Network Topology & Architecture
-------------------------------
                                              [ VMnet8: WAN / External ]
                                                          | 
                                                          |
                                                [ Kali Linux Attacker ]
                                                          |
                                                          v
                                              +-------------------------+
                                              |    OPNsense Firewall    |
                                              +-------------------------+
                                                /                     \
                                               /                       \
                                [ VMnet3: SOC Management ]    [ VMnet2: Corporate LAN ]
                                             |                             |
                                 [ RHEL 10 + Wazuh SIEM ]        +-------------------+
                                                                 | Win Server 2019   |
                                                                 | Windows 10 Host   |
                                                                 +-------------------+


Phases
-------------------------------
Phase 1: Environment Setup & Network Isolation (Completed) Configured virtual adapters, deployed OPNsense with 3 interface zones, initialized RHEL 10, Windows Server 2019, Windows 10, and Kali Linux. Established routing rules to enforce isolation.

Phase 2: Telemetry Ingestion & Agent Deployment (In Progress) Deploying Wazuh Agents across Windows domain hosts, configuring Sysmon and PowerShell audit logging policies, and establishing log shipping to RHEL 10 over port 1514.

Phase 3: Attack Simulation & Detection Engineering (Planned) Executing brute-force attacks, privilege escalation, and credential dumping from Kali Linux to create and fine-tune custom detection rules in Wazuh.
