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
Step 1 – Expand the Active Directory Environment<br/><br/>
Begin expanding the existing Active Directory environment by configuring the additional domain resources required for the attack and defense scenarios: <br/>
<img src="STEP-1-SCREENSHOT-LINK" height="80%" width="80%" alt="Project Steps"/>
<br/>
