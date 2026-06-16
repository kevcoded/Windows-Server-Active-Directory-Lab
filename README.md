# 🛠️ Enterprise Windows Server 2022 & Active Directory Home Lab

This repository serves as a comprehensive, hands-on technical portfolio demonstrating my capability to deploy, secure, and manage an enterprise-grade corporate IT network infrastructure using VMware Workstation.

Rather than showcasing static configurations, this project is documented through real-world IT Help Desk ticket simulations and system audits. This approach highlights my foundational understanding of Identity & Access Management (IAM), network troubleshooting, security policy compliance, patch management, and cross-platform virtualization.

## 🌐 Core Infrastructure Specifications
Before resolving client support tickets, the baseline environment metrics were thoroughly audited and structured:
*   **Internal Test Domain:** `KevCloud.local`
*   **Primary Domain Controller Hostname:** `WIN-HODGHS7M4EQ`
*   **Dedicated Windows 11 Client Node Hostname:** `KEV`

---

## 🚀 High-Priority Core Help Desk Competencies
*The following scenarios showcase the absolute most critical technical competencies required for standard Tier-1/Tier-2 Technical Support roles: User Onboarding, Passwords, Domain Name Resolution, and Security Group Policy Compliance.*

### 🎟️ Ticket #1024: Identity & Access Management (IAM) User Onboarding
**Ticket Description:** *HR has submitted an official employee onboarding request for a new standard user, "John Lim". The technician must provision a domain account matching standard corporate naming conventions.*

*   **Administrative Action:** Navigated the Active Directory Users and Computers (ADUC) graphical user interface to safely initialise a new employee user object.
*   **Technical Verification:** Target-routed the object creation path to the default corporate directory container, enforcing a standard User Principal Name (UPN) scheme of `John@KevCloud.local`.

![Active Directory User Creation](images/Active%20Directory%20New%20User%20Creation.png)
*Figure 1: Provisioning core corporate user properties utilizing the standard ADUC graphical console (Ref: file "Active Directory New User Creation.png").*

---

### 🎟️ Ticket #1025: Standard User Password Reset Workflow
**Ticket Description:** *Standard domain user "John" is locked out or requires a controlled password reset following security baseline changes. Ensure the account remains secure during triage.*

*   **Administrative Action:** Targeted the user object in the ADUC directory hierarchy, opened the context actions menu, and initiated the reset wizard.
*   **Technical Verification:** Applied a temporary secure password and explicitly toggled the security guardrail **"User must change password at next logon"**. This ensures zero-knowledge security compliance, forcing the end user to establish an exclusive, private credential pair the moment they log back into their workstation.

![Password Reset Wizard](images/Password%20Reset.png)
*Figure 2: Forcing a user password reset and enabling next-logon credential complexity via the ADUC console (Ref: file "Password Reset.png").*

---

### 🎟️ Ticket #1141: Workstation Network Routing & Local DNS Triage
**Ticket Description:** *The Windows 11 workstation client `KEV` is experiencing local name resolution failures and cannot authenticate against or connect to the `KevCloud.local` domain controller.*

*   **Administrative Action:** Diagnosed an environmental routing issue where the client node's network adapter parameters were misaligned. Manually configured the workstation's static TCP/IPv4 stack.
*   **Technical Verification:** Bound the workstation client to IP address `192.168.22.66`. Crucially, pointed the **Preferred DNS Server** directly to the primary Domain Controller's IP footprint (`192.168.22.129`). This local adjustment immediately restored active directory communication and authentication paths.

![Client Network Adapter Properties](images/8.%20DNS%20and%20IP%20on%20windows%20_2.png)
*Figure 3: Adjusting TCP/IPv4 adapter attributes to restore local Active Directory DNS name resolution paths (Ref: file "8. DNS and IP on windows _2.png").*

---

### 🛡️ Scenario: Account Baseline Lockout & Password Security Auditing (Group Policy Validation)
**Scenario Context:** *Audit the domain's global credential configuration vectors to prevent brute-force attacks and confirm that Active Directory Group Policies are successfully maintaining infrastructure compliance.*

*   **Administrative Action:** Executed `net accounts` via the command line interface on the Primary Domain Controller to read active policy definitions.
*   **Technical Verification:** Checked baseline configuration values to confirm the maximum password lifespan is locked at 42 days, password history length tracks 24 changes to block password recycling, and account lockouts default to a safe 30-minute cooling window.

![Domain Password Security Audit](images/Domain%20Password%20%26%20Account%20Lockout%20Policy.png)
*Figure 4: Evaluating global credential constraints and lockout rules on the local domain (Ref: file "Domain Password & Account Lockout Policy.png").*

---

## ⚙️ Standard Infrastructure Operations & Maintenance

### 🔍 Scenario: Command Line Infrastructure Architecture Audit
**Scenario Context:** *Confirm hardware baselines, kernel versions, hotfixes, and operating system role parameters on the newly provisioned host system.*

*   **Administrative Action:** Executed `systeminfo.exe` via an elevated command prompt on the target device.
*   **Technical Verification:** Captured internal metrics identifying the hostname as `WIN-HODGHS7M4EQ`, the operating system as `Microsoft Windows Server 2022 Standard Evaluation`, and confirmed its active deployment configuration state as a **Primary Domain Controller**.

![System Information Auditing](images/Infrastructure%20Audit%20%28systeminfo.exe%29.png)
*Figure 5: Reviewing server operating system architectures and domain definitions using the command line interface (Ref: file "Infrastructure Audit (systeminfo.exe).png").*

---

### 🎟️ Ticket #1026: Directory Identity Metadata & Directory Triage
**Ticket Description:** *Verify that the newly provisioned employee account "John" has been restricted properly to standard security groups and has active password policy timelines applied over the domain.*

*   **Administrative Action:** Executed the administrative query utility `net user John /domain` within the Command Prompt terminal to extract active directory structural properties.
*   **Technical Verification:** Confirmed account status is set to active (`Account active: Yes`), audited upcoming mandatory password rotation dates, and verified absolute isolation strictly to standard global `*Domain Users`.

![CLI User Account Audit](images/CLI%20Account%20Metadata%20Audit%20%28net user%29.png)
*Figure 6: Auditing security user parameters and credential expiration tags using the command line (Ref: file "CLI Account Metadata Audit (net user).png").*

---

### 🎟️ Ticket #1102: Active Directory Asset Inventory & Organization
**Ticket Description:** *Verify that the desktop workstation asset has successfully registered within the central domain network structure and that regional folders are organized.*

*   **Administrative Action:** Opened the ADUC administration hierarchy tree to audit active structural elements.
*   **Technical Verification:** Confirmed that the client computer object **`KEV`** has successfully bound to the directory and rests properly within the default `Computers` system folder. Verified the presence of custom Organizational Units (OUs) mapped to handle distinct divisions for **Asia** and **Australia**.

![Active Directory Asset Verification](images/Active%20Directory%20Computer.png)
*Figure 7: Verifying machine endpoint addition and organizational unit tracking inside active directories (Ref: file "Active Directory Computer.png").*

---

### 🎟️ Ticket #1140: Domain Controller Interface Verification
**Ticket Description:** *Confirm the structural static IP mapping bound to the primary server interface to ensure network resolution paths remain static.*

*   **Administrative Action:** Triggered basic command prompt routing diagnostics on the main server console.
*   **Technical Verification:** Executed `ipconfig` to analyze `Ethernet adapter Ethernet0`. Confirmed a stable static IPv4 footprint of `192.168.22.129` paired with a standard Class-C mask (`255.255.255.0`) and default gateway routing via `192.168.22.2`.

![Server IP Configuration](images/Domain%20Controller%20Network%20Interface%20Configuration.png)
*Figure 8: Verifying server connection parameters and default gateway addresses using CLI tools (Ref: file "Domain Controller Network Interface Configuration.png").*

---

### 🎟️ Ticket #1201: Cross-Platform File Systems Integration
**Ticket Description:** *Establish a reliable path to pass tools, setup configurations, and document records securely across the virtual host-guest isolation layers.*

*   **Administrative Action:** Enabled automated Shared Folder mappings inside the VMware hypervisor platform properties menu.
*   **Technical Verification:** Bound host pathway `C:\Users\kevin\Desktop\helpdesklab` to map cleanly across the network stack, confirming that files render seamlessly within the guest file manager under network shared folders.

![VMware Storage Sharing Integration](images/VMware%20Cross-Platform%20Directory%20Sharing.png)
*Figure 9: Utilizing hypervisor platform tools to route secure file systems access across separated environments (Ref: file "VMware Cross-Platform Directory Sharing.png").*

---

## 🔒 Advanced Operations: Remote Access Hardening & Enterprise Patch Automation

### 🎟️ Ticket #1288: Remote Desktop Access Control & Endpoint Hardening
**Ticket Description:** *Configure the system to accept secure remote connections from Tier-1/Tier-2 Technical Support teams, ensuring the environment is protected against unauthenticated credential-harvesting exploits.*

*   **Administrative Action:** Modified Advanced System Settings under the `Remote` tab within the Windows environment. Explicitly configured the host system to accept inbound connections.
*   **Technical Verification:** Enforced the critical security guardrail **"Allow connections only from computers running Remote Desktop with Network Level Authentication (recommended)"**[cite: 2]. This ensures that RDP connections require absolute credential validation at the network level *before* initializing a full terminal interface session[cite: 2]. Tested inbound routing stability by initializing remote terminal sessions directly to target workstation client `192.168.22.66`[cite: 2].

| ![System Properties RDP Panel](images/Secure%20Remote%20Desktop%20%28RDP%29%20%26%20NLA%20Settings.png) | ![Active RDP Connection Verification](images/Remote%20Desktop%20%26%20NLA.png) |
| :---: | :---: |
| *Figure 10: Enforcing strict Network Level Authentication parameters in System Properties (Ref: "Secure Remote Desktop (RDP) & NLA Settings.png")[cite: 2].* | *Figure 11: Launching an active connection check targeting endpoint 192.168.22.66 (Ref: "Remote Desktop & NLA.png")[cite: 2].* |

---

### 🎟️ Ticket #1350: Enterprise Patch Automation & Cloud Fleet Management
**Ticket Description:** *Integrate modern, cloud-based Unified Endpoint Management (UEM) to control vulnerabilities, override standard Windows Update behavior, and maintain continuous infrastructure patch compliance.*

*   **Administrative Action:** Deployed the **Action1 Platform** management agent to take complete control of system updating operations across the network fleet[cite: 2, 3]. 
*   **Technical Verification:** Confirmed full platform override control by selecting the global toggle **"Deactivate updates in Windows settings"**[cite: 2]. This configuration rule ensures Action1 completely commands the software deployment lifecycle, preventing Windows from randomly triggering unapproved updates or forcing unexpected reboots outside configured enterprise maintenance windows[cite: 2].

![Enterprise Action1 Patching Interface](images/13.%20updates%20and%20patches.png)
*Figure 12: Structuring a centralized patch sequence deployment pipeline within Action1 (Ref: file "13. updates and patches.png")[cite: 2].*

---

### 📊 Comprehensive SysAdmin Fleet Telemetry & Asset Audit
The following technical metrics were extracted directly from the centralized Action1 automation logs, demonstrating rigorous cloud fleet visibility and real-time environment auditing capabilities:

#### 1. Live Endpoint Operational Metrics[cite: 3]
*   **Target Machine Name:** `WIN-HODGHS7M4EQ.KevCloud.local`[cite: 2, 3]
*   **Operating System Status:** `Windows Server 2022`[cite: 2, 3]
*   **Central Agent Unique Token ID:** `56102ed0-e26a-4ffa-95a6-64c868ca1c2b`[cite: 3]
*   **Assigned Fleet Group:** `New Endpoints`[cite: 2, 3]
*   **Real-Time Connection State:** `Connected (Live Response Type)`[cite: 3]

#### 2. Host Physical & Hypervisor Component Profile[cite: 3]
*   **Underlying Processor (CPU):** AMD Ryzen 5 7600X 6-Core Processor (Allocated: 2x4.7 GHz, 1/1 Cores, x64-based PC)[cite: 3]
*   **Assigned Memory Block (RAM):** 2Gb Synchronous DRAM (DIMM x 1)[cite: 3]
*   **Active Virtual Hardware Stack:** VMware, Inc. System Model 20,1 running over a 440BX Desktop Reference Platform motherboard profile[cite: 3]
*   **Storage Framework:** 30Gb Solid State Drive (SSD) boot drive allocation[cite: 3]
*   **Network Interface Controller (NIC):** Intel(R) 82574L Gigabit Network Connection[cite: 3]

#### 3. Vulnerability Status & Pending Enterprise Security Patches[cite: 2]
The system scan successfully flagged **5 critical vulnerabilities / 100 non-critical vulnerabilities** along with **2 critical / 3 non-critical missing system updates**[cite: 2]. The following updates were staged for targeted remediation[cite: 2]:
*   `2026-06 Cumulative Update for Microsoft server operating system version 21H2 for x64-based Systems (KB5094128)` (Addresses Critical Exploits: **CVE-2026-33828, CVE-2026-34335, CVE-2026-40404**)[cite: 2]
*   `2026-05 Cumulative Update for .NET Framework 3.5, 4.8 and 4.8.1 for Microsoft server operating system version 21H2 for x64 (KB5088862)` (Security Update / Severity: **Critical**)[cite: 2]
*   `Windows Malicious Software Removal Tool x64 - v5.142 (KB890830)` (Update Rollup)[cite: 2]
*   `Microsoft Visual C++ 2015-2022 Redistributable (14.51.36247.0)` (Regular Update)[cite: 2]
*   `2022-02 Cumulative Update Preview for .NET Framework 3.5 and 4.8 for Microsoft server operating system version 21H2 for x64 (KB5010475)` (Regular Update)[cite: 2]

![Action1 Endpoint Management Portal](images/Enterprise%20Cloud%20Patching%20%26%20Endpoint%20Automation%20%28%20Action1%20Platform%29.png)
*Figure 13: Central tracking grid highlighting real-time CVE vulnerabilities and pending missing updates on the domain controller (Ref: "Enterprise Cloud Patching & Endpoint Automation ( Action1 Platform).png")[cite: 2].*
