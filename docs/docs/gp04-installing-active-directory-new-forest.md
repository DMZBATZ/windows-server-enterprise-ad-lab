# Installing Active Directory Domain Services: New Forest Lab

## Overview

This lab documents the installation and validation of Active Directory Domain Services in a new Windows Server forest environment. The project focused on promoting the first domain controller, creating the forest root domain, validating core Active Directory services, configuring DNS and DHCP, creating administrative accounts, and joining a Windows client system to the domain.

## Lab Objective

The objective of this lab was to build the foundation of an enterprise-style Windows domain environment by deploying the first domain controller in a new Active Directory forest.

## Technologies Used

* Windows Server
* Active Directory Domain Services
* DNS
* DHCP
* Server Manager
* PowerShell
* Active Directory Users and Computers
* Active Directory Sites and Services
* Event Viewer
* DCDIAG
* Windows client domain join

## Environment

| Component         | Description    |
| ----------------- | -------------- |
| Domain Controller | CIS256-DC1     |
| Domain            | abscorp.com    |
| NetBIOS Name      | ABSCORP        |
| Client System     | CIS256-Client1 |
| Network           | 10.1.1.0/24    |
| DHCP Scope Range  | .10 to .240    |

## What I Configured

### 1. Promoted the Server to a Domain Controller

I used Server Manager to install and configure Active Directory Domain Services and promoted the server as the first domain controller in a new forest.

Key configuration items included:

* Created a new forest
* Configured the root domain name
* Enabled DNS during domain controller promotion
* Verified the NetBIOS domain name
* Reviewed database, log file, and SYSVOL paths
* Completed prerequisite checks
* Installed Active Directory Domain Services
* Rebooted the server after promotion

### 2. Verified Active Directory Installation

After the server rebooted, I verified the Active Directory installation by checking that the required administrative tools and services were available.

Validation steps included:

* Verified Active Directory Users and Computers was installed
* Verified Active Directory Sites and Services was installed
* Confirmed the SYSVOL share was created
* Confirmed the Active Directory database path
* Verified DNS service locator records
* Reviewed Event Viewer logs
* Ran DCDIAG to validate domain controller health

### 3. Created User and Administrative Accounts

I created both a standard user account and an administrative account to separate normal user access from privileged administrative access.

Configured accounts included:

* Standard unprivileged user account
* Administrative account for domain administration
* Added the administrative account to privileged Active Directory groups

### 4. Configured DNS Reverse Lookup

I configured an Active Directory-integrated reverse lookup zone for the local subnet.

DNS configuration included:

* Created a reverse lookup zone for the 10.1.1.0/24 network
* Updated pointer records
* Verified name resolution functionality

### 5. Installed and Configured DHCP

I installed and configured DHCP to support automatic IP address assignment for client systems on the local network.

DHCP configuration included:

* Installed DHCP role
* Created a DHCP scope for the local site
* Configured the IP range from .10 to .240
* Prepared the environment for domain-joined client systems

### 6. Joined a Windows Client to the Domain

I joined a Windows client virtual machine to the Active Directory domain and configured Remote Desktop access for domain users.

Client configuration included:

* Joined the client system to the domain
* Verified domain connectivity
* Added Domain Users to the local Remote Desktop Users group

## Validation Methods

The environment was validated using multiple administrative tools and commands:

* Active Directory Users and Computers
* Active Directory Sites and Services
* Event Viewer
* DNS management console
* DHCP management console
* DCDIAG
* PowerShell validation commands
* Domain join verification from the client system

## Skills Demonstrated

* Active Directory Domain Services deployment
* Domain controller promotion
* New forest creation
* DNS configuration and validation
* DHCP scope configuration
* User and administrative account creation
* Domain join troubleshooting
* Server role validation
* Windows Server administration
* Technical documentation

## Security Considerations

This lab reinforced the importance of separating standard user accounts from privileged administrative accounts. Administrative access was assigned only to accounts intended for elevated tasks, supporting the principle of least privilege.

## Screenshots

Screenshots will be added to show:

* Active Directory Domain Services installation
* Domain controller promotion
* Active Directory Users and Computers
* DNS reverse lookup zone
* DHCP scope configuration
* DCDIAG validation
* Successful client domain join

## Lessons Learned

This lab strengthened my understanding of how Active Directory provides centralized identity, authentication, DNS integration, DHCP support, and domain-based administration in an enterprise Windows environment. It also reinforced the importance of validation steps such as checking SYSVOL, DNS service records, Event Viewer, DCDIAG output, and client domain connectivity.
