<h1>Active Directory Environment & Security Configuration</h1>

<h2>Description</h2>

This phase documents the expansion and security configuration of an existing Active Directory environment using Windows Server 2022 and Windows 11 virtual machines. The goal of this phase is to prepare the domain environment for controlled Active Directory attack and defense scenarios.

<br />In this phase, the following topics will be covered:
- <b>Domain user creation</b>
- <b>Organizational Units (OUs)</b>
- <b>Security groups</b>
- <b>Service accounts</b>
- <b>Group Policy configuration</b>
- <b>User and group permissions</b>
- <b>Windows workstation configuration</b>
- <b>Network configuration</b>
- <b>Security and auditing configuration</b>

This phase establishes the Active Directory environment that will be used for the Kerberoasting and password spraying attack and defense scenarios in later phases.
<br />

<h2>Languages and Utilities Used</h2>

- <b>PowerShell</b>
- <b>Command Prompt (CMD)</b>
- <b>Active Directory Domain Services (AD DS)</b>
- <b>Windows Event Viewer</b>
- <b>Oracle VirtualBox</b>

<h2>Environments Used</h2>

- <b>Host Operating System: Windows 10 / Windows 11</b>
- <b>Virtualization Platform: Oracle VirtualBox</b>
- <b>Domain Controller: Windows Server 2022</b>
- <b>Domain Workstation: Windows 11</b>

<h2>Program walk-through:</h2>

<p align="center">
Step 1 – Review the Existing Active Directory Environment<br/><br/>
Opened Active Directory Users and Computers on the Windows Server 2022 domain controller to review the existing domain configuration before expanding the environment. The domain already contains existing users, groups, and Active Directory infrastructure from my labs that will serve as the foundation for the attack and defense scenarios performed throughout the project: <br/>
<img src="STEP-1-SCREENSHOT-LINK" height="80%" width="80%" alt="Project Steps"/>
<br/>
Step 2 – Create the Organizational Unit Structure<br/><br/>
Created Organizational Units (OUs) to organize the domain users, groups, service accounts, and computers that will be used throughout the Active Directory attack and defense environment: <br/>
<img src="Step%202.png?raw=true" height="80%" width="80%" alt="Project Steps"/>
<br/>
Step 3 – Create Domain User Accounts<br/><br/>
Created six domain user accounts within the Domain Users organizational unit to establish a more realistic Active Directory environment for later attack and defense scenarios. Several test accounts were intentionally configured with the same predictable password to support the controlled password spraying scenario performed later in the project: <br/>
<img src="Step%203.png?raw=true" height="80%" width="80%" alt="Project Steps"/>
<br/>
Step 4 – Create and Configure Security Groups<br/><br/>
Created Global security groups for IT, Finance, and Human Resources and assigned the domain users to groups based on their organizational roles. Using security groups allows access and permissions to be managed by role rather than individually for each user: <br/>
<img src="Step%204.png?raw=true" height="80%" width="80%" alt="Project Steps"/>
<br/>
Step 5 – Create and Configure Service Accounts<br/><br/>
Created a dedicated SQL service account within the Service Accounts organizational unit to support the controlled Kerberoasting scenario performed later in the project. The account was configured with a non-expiring password to simulate a traditional service account configuration that will later be evaluated and hardened: <br/>
<img src="Step%205.png?raw=true" height="80%" width="80%" alt="Project Steps"/>
<br/>
Step 6 – Configure Service Principal Name (SPN)<br/><br/>
Configured a Service Principal Name (SPN) for the SQL service account to associate the account with a Kerberos-enabled SQL service within the domain. Registered MSSQLSvc/CA-DC-01.Myforest.com:1433 to the svc_sql account and verified the configuration using the setspn command to prepare the account for the controlled Kerberoasting scenario performed later in the project: <br/>
<img src="Step%206.png?raw=true" height="80%" width="80%" alt="Project Steps"/>
<br/>
Step 7 – Configure and Test User and Group Permissions<br/><br/>
Created departmental shared folders for IT, Finance, and Human Resources and configured NTFS permissions using their corresponding Active Directory security groups. Disabled inherited permissions to restrict access to authorized departmental groups while retaining administrative and system access. Tested the configuration from the Windows 11 workstation using the bmiller account, verifying that a Finance user could create files within the Finance share while access to the IT share was denied: <br/>
<img src="Step%207.png?raw=true" height="80%" width="80%" alt="Project Steps"/>
<br/>
Step 8 – Review Domain Password and Account Lockout Policies<br/><br/>
Reviewed the existing domain Group Policy configuration to establish the security baseline for later attack and defense scenarios. Verified password requirements including a 12-character minimum length and password complexity requirements, along with an account lockout threshold of three invalid logon attempts, a 30-minute counter reset period, and a 360-minute lockout duration. These settings will be used as the baseline when evaluating password spraying activity later in the project: <br/>
<img src="Step%208.png?raw=true" height="80%" width="80%" alt="Project Steps"/>
<br/>
Step 9 – Configure Windows Security Auditing<br/><br/>
Configure Windows security auditing to generate the authentication, account, and Kerberos-related security events required to investigate activity performed during later attack simulations: <br/>
<img src="Step%209.png?raw=true" height="80%" width="80%" alt="Project Steps"/>
<br/>
Step 10 – Verify Domain Workstation and Network Configuration<br/><br/>
Verify that the Windows 11 workstation remains connected to the Active Directory domain and can communicate with the domain controller before beginning the attack simulations: <br/>
<img src="Step%2010.png?raw=true" height="80%" width="80%" alt="Project Steps"/>
<br/>
Step 11 – Verify the Completed Active Directory Security Environment<br/><br/>
Review the completed Active Directory configuration and verify that the users, groups, service accounts, policies, auditing settings, workstation, and network connectivity required for the upcoming attack and defense scenarios are functioning correctly: <br/>
<img src="Step%2011.png?raw=true" height="80%" width="80%" alt="Project Steps"/>
<br/>
