# Lab Infrastructure Project: SQL Server 2025 & Domain Integration

## Introduction
This laboratory project provides a detailed technical documentation of building a secure and scalable enterprise-like network environment from the ground up. The primary objective is to demonstrate the integration of IT infrastructure components, specifically focusing on four key technical domains:

1. **Network Foundation:** Establishing reliable connectivity through static IP addressing and robust DNS name resolution.
2. **Centralized Identity Management:** Integrating a client workstation into an Active Directory domain to enable secure authentication and centralized resource management.
3. **Database Server Provisioning:** Deploying a Microsoft SQL Server 2025 instance, including complex service account configuration and security policy hardening.
4. **Administrative Operations:** Finalizing the environment by deploying remote management tools (SSMS) and verifying operational readiness through successful database connectivity.

This project showcases the workflow required to bridge the gap between network-level connectivity and application-level database services in a Windows-based environment.

---

## 1. Network Configuration
* **Static IP & DNS Setup**
    * **What it does:** Assigns a fixed IP address ($192.168.1.11$) to the workstation and configures the DNS settings to point to the Domain Controller ($192.168.1.10$).
    * **Why it is necessary:** A static identity is required for consistent network communication, and proper DNS resolution is critical for the client to locate domain services.

![NSLookup Tool](nslookup.png)
![NSLookup Result](nslookupresult.png)

## 2. Active Directory Domain Integration
* **Workstation Domain Join**
    * **What it does:** Migrates the "James" workstation from a local workgroup environment into the `lab.local` Active Directory domain.
    * **Why it is necessary:** Domain membership allows for centralized authentication, group policy management, and resource access control.

![Connecting to Server](connectingwindowstoserver.png)
![Connection Process](connecting.png)
![Linking Windows](linkingwindowswithwindowsserver.png)

* **Troubleshooting Connectivity**
    * **What it does:** Diagnoses and resolves Active Directory communication constraints during the domain binding phase.
    * **Why it is necessary:** Ensuring a healthy trust relationship between the client and the controller is mandatory for secure network operation.

![Active Directory Error](activedirectorydomainerror.png)
![Successful Domain Connection](sucessfullconfiguration.png)

## 3. SQL Server 2025 Deployment
* **Initialization & Prerequisites**
    * **What it does:** Executes the installer to verify system compatibility and prepare the environment for database services.
    * **Why it is necessary:** Establishing the database engine foundation is the first step in enabling enterprise data management.

![Install Rules Error](image_a9d728.png)

**Clarification on Warnings:** You may notice yellow warning icons in `image_a9d728.png` regarding the "Computer domain controller" and "Windows Firewall." These are expected in this lab environment and are not critical errors. These warnings do not affect the functionality of this virtualized lab setup, and you can safely proceed with the installation.

![Feature Selection](sqlfeatureselection.png)

* **Service Account & Authentication Strategy**
    * **What it does:** Defines startup privileges for SQL services and enables "Mixed Mode" authentication.
    * **Why it is necessary:** Mixed Mode provides the flexibility to support both domain-joined Windows accounts and native SQL application logins.

![Server Configuration](sqlserverconfigurationpart.png)
![Configuration](configurationofmixedmodeandsauserpassword.png)

* **Installation Process**
    * **What it does:** Extracts and deploys the core SQL Server engine components.
    * **Why it is necessary:** Completes the transition from installation binaries to a fully functional database instance.

![Installing SQL](installingsqlserver.png)
![Installation Progress](installationinprogress.png)
![Installation Complete](SQLinstallationcomplete.png)

## 4. Administrative Management
* **Management Studio Installation**
    * **What it does:** Installs SQL Server Management Studio (SSMS) on the client workstation.
    * **Why it is necessary:** SSMS is the primary administrative interface required to perform database queries, server configuration, and monitoring.

![SSMS Installation](sqlmanagementtoolsinstallation.png)

* **Operational Verification**
    * **What it does:** Establishes a remote connection from the management utility to the SQL instance.
    * **Why it is necessary:** Final proof of system integrity, confirming the server is online, authenticating correctly, and ready for use.

![Successfully Connected](sucessfullyconnected.png)

---

## Conclusion
This project successfully demonstrates the systematic deployment of a functional SQL Server environment within a domain-controlled network. By following these steps—from network configuration and Active Directory integration to service deployment and remote management—we have created a robust foundation for database administration. This lab highlights the importance of precise configuration, troubleshooting connectivity issues, and implementing secure authentication methods, all of which are essential skills for professional IT system administration.
