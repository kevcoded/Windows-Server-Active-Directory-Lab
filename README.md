# 🛠️ Enterprise Windows Server 2022 & Active Directory Home Lab

## 📋 Project Overview
This repository serves as a comprehensive, hands-on technical portfolio demonstrating my capability to deploy, secure, and manage an enterprise-grade corporate IT network infrastructure using **VMware Workstation**. 

Rather than showcasing static configurations, this project is documented through **real-world IT Help Desk ticket simulations and system audits**. This approach highlights my foundational understanding of Identity & Access Management (IAM), network troubleshooting, security policy compliance, and cross-platform virtualization.

---

## 🌐 Core Infrastructure Specifications
Before resolving client support tickets, the baseline environment metrics were thoroughly audited and structured:

*   **Internal Test Domain:** `KevCloud.local`
*   **Primary Domain Controller Hostname:** `WIN-HODGHS7M4EQ`
*   **Dedicated Windows 11 Client Node Hostname:** `KEV`

---

## 🎟️ Help Desk Scenarios, Audits & Ticket Resolutions

### 🔍 Scenario 1: Infrastructure Compliance & OS Architecture Audit
**Scenario Context:** *The IT Infrastructure Lead requires a detailed configuration audit of the newly provisioned corporate server to verify operating system alignments, kernel metrics, and basic patch compliance.*

*   **Administrative Action:** Executed `systeminfo.exe` via an elevated command prompt on the host terminal. 
*   **Technical Verification:** Audited system diagnostics to confirm the operating system as **Windows Server 2022 Standard Evaluation**, validated its active deployment as the **Primary Domain Controller** for the `KevCloud.local` tree, and inventoried structural hardware properties.

![System Information Auditing](images/2.png)
*Figure 1: Running system architecture diagnostics via Command Prompt (Ref: file "2.png").*

---

### 🎟️ Ticket #1024: Corporate User Onboarding & IAM Provisioning
**Ticket Description:** *HR has submitted an onboarding request for a new standard employee, "John Doe". The user requires a domain account matching the standard corporate naming conventions.*

*   **Administrative Action:** Leveraged the Active Directory Users and Computers (ADUC) graphical user interface to provision a new employee object.
*   **Technical Verification:** Configured the User Principal Name (UPN) to target the default directory container securely, outputting the login address as `John@KevCloud.local`.

![Active Directory User Creation](images/4.setting%20up%20user.png)
*Figure 2: Provisioning corporate employee account parameters via the ADUC GUI (Ref: file "4.setting up user.png").*

---

### 🎟️ Ticket #1025: Security Metadata & Lifecycle Audit
**Ticket Description:** *The cybersecurity team requested an immediate audit of the newly provisioned user account "John" to verify security group isolation and confirm that password change constraints are active.*

*   **Administrative Action:** Ran a localized administrative query directly on the domain database via Command Prompt.
*   **Technical Verification:** Executed `net user John /domain` to pull account attributes. Confirmed that the account is flagged as active, restricted properly to the standard `*Domain Users` global group, and verified the upcoming password expiration timeline parameters.

![CLI User Account Audit](images/6.%20user%20password%20info.png)
*Figure 3: Auditing directory metadata and user lifecycle states using the command line interface (Ref: file "6. user password info.png").*

---

### 🛡️ Scenario 2: Global Domain Security Policy Verification
**Scenario Context:** *Review the active domain-wide account lockout thresholds and password complexity matrices to ensure full alignment with internal corporate security baselines.*

*   **Administrative Action:** Queried the domain policy engine directly from the command line interface.
*   **Technical Verification:** Executed `net accounts` to audit baseline criteria. Confirmed that global password history length tracks 24 changes to prevent credential reuse, maximum password age is capped at 42 days, and account lockout windows are set to 30 minutes to mitigate brute-force vector risks.

![Domain Password Security Audit](images/1.png)
*Figure 4: Evaluating global password complexity rules and lockout guidelines via the CLI (Ref: file "1.png").*

---

### 🎟️ Ticket #1102: Workstation Endpoint Integration & Asset Inventory
**Ticket Description:** *A new physical workstation needs deployment. It must be assigned to the appropriate organizational structure and successfully joined to the corporate domain.*

*   **Administrative Action:** Completed a network domain handshake on the client node to join it to the infrastructure.
*   **Technical Verification:** Authenticated the system into `KevCloud.local`. Opened the ADUC console tree to verify that the workstation object **`KEV`** successfully registered within the default `Computers` system container alongside geographic Organizational Units (OUs) structured for **Asia** and **Australia**.

![Active Directory Asset Verification](images/9.computer%20kev%20.png)
*Figure 5: Verifying client asset registration inside Active Directory Users and Computers (Ref: file "9.computer kev .png").*

---

### 🎟️ Ticket #1140: Domain Controller Static Network Interface Mapping
**Ticket Description:** *The core network operations team requires physical verification of the Primary Domain Controller's network adapter binding to ensure it matches the static class-C routing layout.*

*   **Administrative Action:** Checked active network adapter properties via the command line interface.
*   **Technical Verification:** Ran `ipconfig` on the server terminal. Confirmed that interface `Ethernet0` is statically bound to IPv4 address `192.168.22.129` with a standard `/24` subnet mask to maintain persistent routing reliability across the lab.

![Server IP Configuration](images/7.%20windows%20server%20ipconfig.png)
*Figure 6: Validating server interface parameters via command prompt routing diagnostics (Ref: file "7. windows server ipconfig.png").*

---

### 🎟️ Ticket #1141: Client IP Routing & Local DNS Name Resolution
**Ticket Description:** *The Windows 11 workstation client cannot communicate with the domain controller. Troubleshoot and resolve local name resolution or network layer failures.*

*   **Administrative Action:** Diagnosed localized network adapter conflicts and manually reconfigured the workstation's IPv4 stack properties.
*   **Technical Verification:** Bound the client to a static IP address of `192.168.22.66` on the matching subnet and pointed the **Preferred DNS Server** directly to the Domain Controller's IP (`192.168.22.129`). This critical fix allows the client to successfully look up local domain queries and authenticate against Active Directory.

![Client Network Adapter Properties](images/8.%20DNS%20and%20IP%20on%20windows%20.png)
*Figure 7: Adjusting TCP/IPv4 adapter settings to restore proper local DNS name resolution paths (Ref: file "8. DNS and IP on windows .png").*

---

### 🎟️ Ticket #1201: Cross-Platform Virtual Directory Storage Sharing
**Ticket Description:** *The support team needs an isolation-aware internal file exchange path to easily share documentation, tool deployments, and files across the host-guest hypervisor layer.*

*   **Administrative Action:** Implemented host-to-guest virtualization pathways via VMware's engine properties to map local host directories to the virtual server.
*   **Technical Verification:** Enabled persistent directory isolation sharing for directory `C:\Users\kevin\Desktop\helpdesklab`. Verified that the server can cleanly read and process shared assets over SMB storage paths (e.g., *Kevin lim's Resume.pdf*).

![VMware Storage Sharing Integration](images/3%20-%20shared%20folders%20.png)
*Figure 8: Mapping shared storage pathways across host hypervisors and virtual server guests (Ref: file "3 - shared folders .png").*

---

### 🎟️ Ticket #1288: Securing Remote Endpoints for Desktop Support
**Ticket Description:** *Configure the client machine to safely accept incoming Remote Desktop connections from Tier 1 Help Desk agents handling technical support calls.*

*   **Administrative Action:** Modified Advanced System Settings directly inside the Windows 11 client control panel interface.
*   **Technical Verification:** Enabled inbound Remote Desktop capabilities, explicitly enforcing the **Network Level Authentication (NLA)** security guardrail to validate agent credentials before a terminal session initializes.

![Remote Desktop Control Configuration](images/10.allowing%20remote%20connection%20.png)
*Figure 9: Setting up inbound Remote Desktop parameters with active NLA guidelines on standard nodes (Ref: file "10.allowing remote connection .png").*
