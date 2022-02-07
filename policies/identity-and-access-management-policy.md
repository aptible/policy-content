# Access Authorization
Authorizations to access company information or information systems shall only be made by the Security Team or the asset owners of the relevant assets. This includes access to specific security-relevant functions and information.

Role-based access control is enforced and maps each user to one or more roles, and each role to one or more system functions.

All requests for access to a system shall be considered by the Security Team in conjunction with the asset owner for the particular system. Decision about whether to authorize a user to access a particular information system shall be made based strictly on business need.

The Security Team should not authorize access requests that have been initiated by the Security Team.

# Standard Access to Information and Information Systems

## Team Access
 
Our information and information systems must be controlled to ensure that only authorized users or groups of users are granted access rights. All access must comport with the Technology Acceptable Use Policy and applicable statutory, regulatory, and contractual compliance requirements.

Access and access controls must abide by the following principles:

-  **Deny by Default:** Controls must deny access by default, unless access is expressly configured.
-  **Need-To-Know:** Only users and processes that require access to information or information systems to perform authorized job functions may be permitted access.
-  **Least Privilege:** Users and processes must be granted the least level of permissions necessary to perform their intended function(s).
-  **Unique User Identification:** Systems that store or process Sensitive/Regulated Information must assign a unique identifier for tracking user or process activity.
-  **Shared accounts:** Shared accounts may be used for services that do not handle Sensitive/Regulated Information, but access must still be restricted to teams/groups based on business needs.

## Customer Access
 
Asset owners must ensure that prior to granting customers access to our information or information systems, all statutory, regulatory, and contractual compliance requirements are satisfied.

This may include, for example:

- having the customer accept our terms of service;
- executing a master services agreement; or
- executing regulatory contracts, such as HIPAA business associate agreements or GDPR data protection agreements, if needed.

Self-service or clickwrap agreements may be used. The Legal Team is responsible for tracking and enforcing any such requirements.

## Robot Users
 
Automated programs, scripts, and processes are permitted, but access must satisfy the same principles as human users. Each automated user must have an identifiable individual or team owner.

All robot users shall be logged as would human users.

# Privileged Access to Information and Information Systems

## General Requirements

Subject to the exceptions below, only the Management Team may grant privileged access rights to workforce members, including system administrator privileges and the right to execute privileged commands remotely. Privileged functions shall only be performed by users with privileged access rights.

Privileged access rights shall only be granted to users when privileged access is necessary for the functioning of their roles. Privileged access rights shall be reviewed during recurring access control reviews.

Where possible, users should not use their accounts used for normal use to perform operations that require privileged access; instead, they should perform those actions using an account that is only used to perform privileged operations.

## Privileged Utility Programs

The use of utility programs that can override system and application controls shall be strictly limited based on business need.

# Temporary Incident Response Access

The Security Officer may approve temporary access to information systems for members of the Incident Response Team in order to investigate and resolve incidents.

Access must be revoked immediately once the business need for access ends.

# Access Review

## Access Review Requirements

For the information systems that we are responsible for managing access controls, monthly access reviews shall be performed in order to verify the following:

- all users of each information system have a business need for access.
- user permissions are set appropriately based on business needs; and
- multi-factor authentication status is appropriate for relevant systems.

If a policy violation is identified during an access review, the reviewer shall immediately inform the Security Officer. The Security Officer shall investigate to determine if inappropriate access occurred.

## Cadence

The cadence at which access reviews must occur depends on the information stored or processed by the underlying assets. The Security Team shall ensure that access reviews occur for assets according to the following schedule:

- **Quarterly:** Assets that store, process, or transmit *Sensitive/Regulated Information* or *Restricted Information*.
- **Yearly:** Assets that store, process, or transmit *Confidential Information* and *Public Information*.
 
## Third-Party Access Reviews

If we grant third parties access to company information or information systems, the Security Officer shall assess and prioritize the risks we face due to that in order to minimize, monitor, and measure the potential for unauthorized or inappropriate access. If our current risk assessment does not sufficiently reflect the appropriate risks, the Security Officer shall update it. Compensating controls derived from our risk assessment must be implemented prior to granting access to third parties.

# Access Revocation and Modification
The Security Team shall verify the identity of a user prior to modifying its access to an information system.

Managers are responsible for timely de-provisioning (revoking or modifying) user access to company information and information systems based on changes in workforce member status (e.g., termination of employment or other business relationship, job change, or transfer). This may involve working with the asset owners of systems to which the user had access. Access to systems with Sensitive/Regulated Information must be de-provisioned within 24 hours of a change in status.

For instances of increased risk, access rights are immediately deactivated or modified following the user's termination, and allow for immediate escorting from the site, if applicable.

# Workforce Usage of Authenticators Policy
Workforce members must meet the following requirements when using authenticators to access our information or information systems.

## Unique User IDs

Workforce members shall ensure that information systems that process Sensitive/Regulated Information are accessed with unique user identifiers. Workforce members shall never share passwords for systems that handle Sensitive/Regulated Information.

## Password Selection

Workforce members shall use a password manager to securely generate and store passwords. When workforce members create accounts for new services, they must change the default password. Additionally, workforce members must temporary passwords the first them they log in with them.

If users are sent passwords they acknowledge receipt via telephone.

## No Knowledge-based Authentication

If a service requires the use of password hints, “security questions,” or other knowledge-based authentication, workforce members creating those authenticators shall follow the Password Selection requirements outlined here.

Workforce members shall not create authenticators that can be readily found on the Internet.

## Multi-Factor Authentication

The use of multi-factor authentication (including two-factor authentication) is preferred for all systems that store or process company information. Multi-factor authentication is required on systems that store or process Sensitive/Regulated Information.

## Electronic Signature

Electronic signatures that are not based upon biometrics shall use at least two distinct identification components that are administered and executed.

Identification codes used in conjunction with passwords for electronic signatures shall be protected.

## SSH Keys

Workforce members must securely generate SSH keys and ensure that a password is entered during the key-pair creation to encrypt the SSH key.
 
## TLS Certificates

Requirements for SSL/TLS certificate life cycle management, including generation and storage, are located in the Encryption and Key Management Policy.

# Remote Access
## Remote Connection Security

Prior to authorizing remote work, the physical security of the remote working site should be evaluated and any threats/issues. Any threats/issues identified should be logged in the risk assessment and given a risk response. Insurance policies should be designed to include the risks of remote work.

If applicable, workforce members' identities shall be verified in person by a manager / supervisor prior to receiving a hardware token.

The Security Team performs periodic monitoring to ensure that only authorized remote connections are allowed.  


### Remote Access Requirements

- using any form of remote access that is not managed by the company is prohibited including, but not limited to, virtual desktop sharing, or web conferencing solutions that permit user access to the network without proper remote access authentication; 
- active VPN connections to the network must force ingress and egress traffic to and from the device over the VPN tunnel or equivalent. A device that makes a remote access connection to the network must be connected only to the network. Split tunneling is prohibited;
- the user is responsible for the security of account information, including passwords, PINs, or other sensitive data. Account information may not be shared with anyone, including but not limited to other company personnel, family, or friends;
- all methods of remote access to the network must use at least a form of multi-factor authentication. 

### Encryption Requirements

Workforce members and contractors must always use secure, encrypted protocols (such as SSL/TLS and SSH) to connect to information systems, including both company systems and third-party systems.

### Remote Activation
The information system prohibits remote activation of collaborative computing mechanisms and provides an explicit indication of use to the local users.


## Remote Location Security

Workforce members must ensure that the physical environment used for remote access is appropriate for work performed by the workforce member. Considerations shall include the following:

- at all work sites, reasonable precautions must be taken to protect company information and information systems from theft, damage, and misuse; and
- all workforce members and contractors must promptly report to their manager and the Security Officer any damage to or loss of company information or information systems, including the loss of BYOD devices used for work.

# Boundary Protection

## DMZ

A DMZ shall be established with all database(s), servers, and other system components storing or processing covered information placed behind it to limit external network traffic to the internal network.

## DNS

To eliminate single points of failure and enhance redundancy company shall use at least two DNS servers that are:
- located on different subnets; 
- geographically separated;  and
- perform different roles (internal and external).

## Firewalls

The Security Officer shall ensure that all company-controlled networks are protected by appropriate firewalls, which are configured to control traffic to our information systems. Firewalls shall be from at least two different vendors that and employ stateful packet inspection (also known as dynamic packet filtering).The Security Team shall define firewall policies based on the specific risks that we face. These may include policies based on IP addresses or protocols, applications, user identities, or network activity. At a minimum firewalls shall:

- enforce security policies;
- filter traffic between domains;
- block unauthorized access;
- segregate between internal wired, internal wireless, and external network segments (e.g., the Internet), including DMZs; and,
- enforce access control policies for each of the domains.

Firewall configuration standards and configuration shall be reviewed every six months.

### Web Applications

For any public-facing web applications, application-level firewalls shall be implemented to control traffic.

For any public-facing applications that are not web-based, the company shall implement a network-based firewall specific to the application type.

If the traffic to the public-facing application is encrypted, the device shall either sits behind the encryption or be capable of decrypting the traffic prior to analysis.

### Remote Connections
Remote devices establishing a non-remote connection shall not communicate with external (remote) resources.

### Network Routing Control

Network routing control shall include positive source and destination checking mechanisms, such as firewall validation of source/destination addresses, and the hiding of internal directory services and IP addresses.

The company shall design and implement network perimeters so that all outgoing network traffic to the Internet passes through at least one application layer filtering proxy server. The proxy shall support:
- decrypting network traffic;
- logging individual TCP sessions;
- blocking specific URLs, domain names, and IP addresses to implement a blacklist;
- and applying whitelists of allowed sites that can be accessed through the proxy while blocking all other sites.

The company shall force outbound traffic to the Internet through an authenticated proxy server.

## Intrusion Detection and Prevention

Technical monitoring tools such as an IDS and/or IPS shall be implemented and operating on the network perimeter and other key points to identify vulnerabilities, monitor traffic, detect attack attempts and successful compromises, and mitigate threats. These tools are updated and reviewed at least annually.

## Change Management

All network connections and firewall, router, and switch configuration changes shall be tested prior to implementation. Any deviations from or updates to the standard configuration shall be documented and approved by the Security Officer. New configuration rules beyond a baseline-hardened configuration that allow traffic to flow through network security devices, such as firewalls and network-based IPS, shall be documented and recorded to include:
- specific business reason for each change;
- specific individual’s name responsible for that business need and;
- expected duration of the need