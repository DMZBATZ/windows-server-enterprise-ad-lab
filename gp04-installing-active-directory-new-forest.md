# Installing Active Directory Domain Services: New Forest Lab

## Overview

This project documents the deployment of the first domain controller in a new Active Directory forest. The lab focused on installing Active Directory Domain Services, creating the forest root domain, validating core domain services, configuring DNS and DHCP, creating administrative accounts, and joining a Windows client system to the domain.

## Business Scenario

A new enterprise Windows domain environment needed to be created for the ABS Corporation. The first domain controller was deployed to establish the forest root domain and provide centralized authentication, name resolution, IP address assignment, and administrative control for domain-joined systems.

## Lab Objectives

* Install Active Directory Domain Services on the first domain controller
* Create a new Active Directory forest
* Configure the forest root domain
* Validate Active Directory installation
* Configure DNS reverse lookup
* Install and configure DHCP
* Create standard and administrative user accounts
* Join a Windows client system to the domain
* Validate domain controller health and domain services

## Technologies Used

* Windows Server
* Active Directory Domain Services
* DNS
* DHCP
* Server Manager
* Active Directory Users and Computers
* Active Directory Sites and Services
* Event Viewer
* PowerShell
* DCDIAG
* Windows client domain join
* Remote Desktop Users group

## Lab Environment

| Component           | Configuration                                |
| ------------------- | -------------------------------------------- |
| Domain Controller   | CIS256-DC1                                   |
| Forest Root Domain  | abscorp.com                                  |
| NetBIOS Domain Name | ABSCORP                                      |
| Client System       | CIS256-Client1                               |
| Network             | 10.1.1.0/24                                  |
| DHCP Scope Range    | .10 to .240                                  |
| DNS Role            | Installed during domain controller promotion |
| DHCP Role           | Installed after AD DS deployment             |

## Implementation Summary

### 1. Promoted the Server to a Domain Controller

The server was promoted as the first domain controller in a new Active Directory forest using Server Manager and the Active Directory Domain Services Configuration Wizard.

Key configuration steps included:

* Selected **Add a new forest**
* Created the root domain `abscorp.com`
* Confirmed the NetBIOS name `ABSCORP`
* Enabled DNS during domain controller promotion
* Reviewed database, log file, and SYSVOL paths
* Completed prerequisite checks
* Installed Active Directory Domain Services
* Rebooted the server after promotion

### 2. Validated Active Directory Installation

After the server rebooted, the Active Directory installation was validated using Windows administrative tools and command-line checks.

Validation included:

* Confirmed Active Directory Users and Computers was available
* Confirmed Active Directory Sites and Services was available
* Verified the SYSVOL share was created
* Confirmed the Active Directory database path
* Verified DNS service locator records
* Reviewed Event Viewer logs for relevant errors
* Ran `dcdiag` to validate domain controller health

### 3. Created Standard and Administrative Accounts

Separate user accounts were created to support proper administrative practice.

Configured accounts included:

* A standard unprivileged user account
* An administrative account named `ABSAdmin`
* Added `ABSAdmin` to privileged administrative groups

This supported separation between normal user activity and elevated administrative tasks.

### 4. Configured DNS Reverse Lookup

A primary Active Directory-integrated reverse lookup zone was created for the local network.

DNS configuration included:

* Reverse lookup zone for `10.1.1.0/24`
* Pointer record updates
* DNS validation for domain services

### 5. Installed and Configured DHCP

DHCP was installed and configured to provide automatic IP address assignment for local clients.

DHCP configuration included:

* Installed the DHCP Server role
* Created a DHCP scope for the local subnet
* Configured the address range from `.10` to `.240`
* Prepared the environment for domain-joined client systems

### 6. Joined a Windows Client to the Domain

A Windows client virtual machine was joined to the `ABSCorp.com` domain.

Client configuration included:

* Joined `CIS256-Client1` to the domain
* Verified domain connectivity
* Added the `Domain Users` group to the local `Remote Desktop Users` group

## Validation and Testing

The environment was validated using:

* Active Directory Users and Computers
* Active Directory Sites and Services
* DNS Manager
* DHCP Manager
* Event Viewer
* `dcdiag`
* PowerShell
* Client domain join verification

## Skills Demonstrated

* Windows Server administration
* Active Directory Domain Services deployment
* Domain controller promotion
* New forest creation
* DNS configuration and validation
* DHCP scope configuration
* User and administrative account management
* Domain join configuration
* Remote Desktop group configuration
* Infrastructure validation and troubleshooting
* Technical documentation

## Security Considerations

This lab reinforced the importance of separating standard user accounts from privileged administrative accounts. Administrative privileges were assigned only to the dedicated administrative account, supporting least privilege and reducing risk during routine user activity.

## Screenshots

Screenshots will be added after the lab documentation is created.

Recommended screenshots:

* Active Directory Domain Services installation
* Domain controller promotion summary
* Active Directory Users and Computers
* DNS reverse lookup zone
* DHCP scope configuration
* `dcdiag` validation output
* Client joined to the domain

## Lessons Learned

This lab strengthened my understanding of how Windows Server infrastructure supports centralized identity, authentication, DNS integration, DHCP services, access control, and domain-based administration. It also reinforced the importance of validating domain controller health after installation using administrative tools, Event Viewer, DNS records, SYSVOL verification, and `dcdiag`.
