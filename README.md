# 🛠️ Enterprise Windows Server 2022 & Active Directory Home Lab

This repository serves as a comprehensive, hands-on technical portfolio demonstrating my capability to deploy, secure, and manage an enterprise-grade corporate IT network infrastructure using VMware Workstation.

Rather than showcasing static configurations, this project is documented through real-world IT Help Desk ticket simulations and system audits. This approach highlights my foundational understanding of Identity & Access Management (IAM), network troubleshooting, security policy compliance, and cross-platform virtualization.

## 🌐 Core Infrastructure Specifications
Before resolving client support tickets, the baseline environment metrics were thoroughly audited and structured:
*   **Internal Test Domain:** `KevCloud.local`
*   **Primary Domain Controller Hostname:** `WIN-HODGHS7M4EQ`
*   **Dedicated Windows 11 Client Node Hostname:** `KEV`

---

## 🚀 High-Priority Core Help Desk Competencies
*The following scenarios showcase the absolute most critical technical competencies required for standard Tier-1/Tier-2 Technical Support roles: User Onboarding (IAM), DNS Name Resolution, System Security Compliance, and Remote Endpoint Access Control.*

### 🎟️ Ticket #1141: Client Network Routing & Local DNS Triage (Critical)
**Ticket Description:** *The Windows 11 workstation client `KEV` is experiencing local name resolution failures and cannot authenticate against or connect to the `KevCloud.local` domain controller.*

*   **Administrative Action:** Diagnosed a local network adapter configuration error. Manually adjusted the workstation's IPv4 stack properties.
*   **Technical Verification:** Configured the workstation client with a static IP address of `192.168.22.66`. Crucially, pointed the **Preferred DNS Server** directly to the Domain Controller's IP address (`192.168.22.129`). This critical fix routes all local namespace queries directly to Active Directory, successfully restoring domain authentication paths.

![Client Network Adapter Properties](images/8.%20DNS%20and%20IP%20on%20windows%20.png)
*Figure 1: Resolving TCP/IPv4 adapter attributes to restore local Active Directory DNS name resolution paths (Ref: file "8. DNS and IP on windows .png").*

---

### 🎟️ Ticket #1024: Identity & Access Management (IAM) User Onboarding
**Ticket Description:** *HR has submitted an official employee onboarding request for a new standard user, "John Lim". The technician must provision a domain account matching standard corporate naming conventions.*

*   **Administrative Action:** Navigated the Active Directory Users and Computers (ADUC) graphical user interface to safely initialize a new employee user object.
*   **Technical Verification:** Target-routed the object creation path to the default corporate directory container, enforcing a standard User Principal Name (UPN) scheme of `John@KevCloud.local`.

![Active Directory User Creation](images/4.setting%20up%20user.png)
*Figure 2: Provisioning core corporate user properties utilizing the standard ADUC graphical console (Ref: file "4.setting up user.png").*

---

### 🎟️ Ticket #1288: Securing Corporate Workstations for Remote Assistance
**Ticket Description:** *Configure the deployment endpoint to accept secure, inbound Remote Desktop (RDP) connections from authorized Tier-1/Tier-2 Help Desk technicians responding to support tickets.*

*   **Administrative Action:** Modified Advanced System Settings properties directly inside the client operating system's configuration panel.
*   **Technical Verification:** Explicitly enabled inbound remote connections, ensuring that the **Network Level Authentication (NLA)** check guardrail is active. NLA forces credential validation at the network layer *before* a full terminal user session initializes, blocking unauthorized access attempts.

![Remote Desktop Control Configuration](images/10.allowing%20remote%20connection%20.png)
*Figure 3: Setting up inbound Remote Desktop parameters with active Network Level Authentication guidelines (Ref: file "10.allowing remote connection .png").*

---

### 🛡️ Scenario: Automated Platform Operations & Endpoint Verification
**Scenario Context:** *The InfoSec team requires real-time compliance status verification for active cloud-managed servers to ensure they are connected and securely transmitting system health metrics.*

*   **Administrative Action:** Generated an exportable compliance summary using a dedicated systems operation dashboard to analyze real-time patch and infrastructure reachability metrics.
*   **Technical Verification:** Audited endpoint analytics to verify that the active system node `WIN-HODGHS7M4EQ.KevCloud.local` running **Windows Server 2022** is safely flagged as `Connected`. Confirmed live agent status and recorded unique identification tokens (`agent_id: 56102ed0-e26a-4ffa-95a6-64c868ca1c2b`) inside the corporate configuration database.

