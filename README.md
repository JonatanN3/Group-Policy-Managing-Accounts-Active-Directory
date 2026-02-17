# Group Policy Managing Accounts
This tutorial is to demonstrate account security enforcement using Group Policy in Windows Server.

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services (AD DS)
- Group Policy Management Console (GPMC)

<h2>Operating Systems Used </h2>

- Windows Server 2022 (Domain Controller)
- Windows 11 Pro

<h2>Group Policy & Managing Accounts</h2>

- Centralized management
- Security enforcement
- User account control
- Policy configuration

<h2>1. Group Policy Management Console Open</h2>

<p>
<img <img width="1345" height="822" alt="Screenshot (12)" src="https://github.com/user-attachments/assets/e7171572-1d22-4f87-8848-429c8908c2cd" />
</p>
<p>
Launched Group Policy Management Console (GPMC) to manage and configure domain-level security policies within the Active Directory environment. This console provides centralized control over user and computer policies across the domain.
</p>
<br />

<h2>2. Group Policy Management Editor (Before Config)</h2>

<p>
<img <img width="1536" height="1024" alt="Remote Desktop Connection 2_15_2026 1_07_42 AM" src="https://github.com/user-attachments/assets/64a2b080-5c17-4998-98a8-6966a060b19b" />
</p>
<p>
Observed that the Account Lockout Policy was not configured. The lockout threshold was set to 0 invalid logon attempts, meaning users could attempt unlimited failed logins. This represents the default security configuration and leaves the domain vulnerable to brute-force login attempts.
</p>
<br />

<h2>3.Group Policy Management Editor (After Config)</h2>

<p>
<img <img width="1536" height="1024" alt="20 220 32 169 - Remote Desktop Connection 2_15_2026 12_44_25 AM" src="https://github.com/user-attachments/assets/90b5f9f9-2929-4466-b08a-e52b7fa6fd27" />
</p>
<p>
Configured the Default Domain Policy to enforce an Account Lockout Policy across all domain users. The lockout threshold was set to 5 invalid logon attempts, with a lockout duration of 30 minutes and a reset counter of 10 minutes. Administrator account lockout was also enabled. This demonstrates implementation of centralized security controls to mitigate unauthorized access.
</p>
<br />

<h2>4. User Account Locked Out</h2>

<p>
<img <img width="1536" height="982" alt="Screenshot (11)" src="https://github.com/user-attachments/assets/4989b1a5-793e-4156-bd3f-ad9d8c91a4e8" />
</p>
<p>
Verified that the configured Group Policy was successfully applied by triggering multiple failed login attempts. The user account was locked as expected, confirming proper policy enforcement and centralized domain management.
