# System Development

The only software and systems that shall be created or purchased are those that are designed, developed, deployed, and tested in accordance with leading industry standards (e.g., OWASP for web applications) and that adhere to our statutory, regulatory, and industry compliance obligations.

To ensure that we only create or purchase software and systems that meet these requirements, we have adopted the following five-phase system-development life cycle ("SDLC"):

1. Planning
2. Design
3. Development
4. Deployment
5. Maintenance

## 1. Secure System Planning

The risk management process is integrated with the Secure System Development Life Cycle of the organization.

The Management Team will define and apply a process for an information security risk assessment in accordance with the Risk Assessment and Treatment Policy. The process will:
- Establish and maintain a security risk acceptance criteria; 
- Establish and maintain a criteria for performing risk assessments; 
- Ensure risk assessments produce consistent, valid and comparable results; and
- Identify, analyze and evaluate the information security risks.

The Management Team shall ensure that secure development environments are used for system development and integration efforts throughout the entire system development life cycle. This includes, but are not limited to the application of automated and manual controls such as access controls, device hardening, vulnerability management, network segmentation, and password protection.

The Management Team must authorize the development or acquisition of new applications, infrastructure, networks, or system components. Members of the Engineering Team must get approval from their manager before acquiring any resource, or deploying new resources outside a sandbox environment.

## 2. Secure System Design

### General Design Requirements

During the design phase, the Engineering Team must identify and document business and security requirements for the systems, including the functions, ports, protocols, and services intended for organizational use. Systems must protect the confidentiality, integrity, and availability of information and other information systems across multiple system interfaces, jurisdictions, and business functions to prevent improper disclosure, alteration, or destruction. Operational systems must only hold approved programs and executable code.

Relevant considerations should include:

- **authentication:** define how users will verify their identity;
- **access controls:** identify security, contractual, and regulatory requirements for customer access;
- **audit logging:** identify how applications will record activity and make it available for examination;
- **session management**;
- **transmission security**;
- **data protection:** identify whether any privacy laws or regulations should be taken into account in building or buying the system;
- **data integrity and validation**; and
- **any other applicable legal, statutory, or regulatory compliance obligations**.

The Engineering Team should review the current risk assessment to determine if the contemplated project will significantly alter or change the risk model, and conduct a new risk assessment if so.

### Specific Design Requirements

#### Authenticator Requirements

##### Password Requirements

Authentication services that we build or configure passwords should enforce the following:

- users should select their own passwords, to avoid ever storing a password in cleartext;
- password requirements should prevent weak passwords from being selected, either through dictionary exclusions (e.g. by preventing passwords that appear on up-to-date weak-passwords blacklists) or complexity requirements;
- 
- password requirements should enforce a minimum length of at least 8 characters;
- passwords should have a long maximum length, no fewer than 64 characters;
- the authentication mechanism should rate limit when possible;
- by default, passwords should not be displayed when entered (though it's permitted to include an option to display the password);
- temporary passwords are unique and not guessable;
- passwords should be referenced against a list commonly-used, expected, or compromised passwords (password blacklist) , and blocked from use if on the list
- the password blacklist should and updated at least every 180 days and when organizational passwords are suspected to have been compromised (either directly or indirectly);
-  passwords should allow spaces and all printable characters;
- passwords should never be sent in plain text; and
- users are informed that they should keep passwords confidential.

The password system should employ automated tools to assist the user in selecting strong passwords and authenticators, and verify, when users create or update passwords, that the passwords are not found on the organization-defined list of commonly-used, expected, or compromised passwords.

Where possible, we shall give users the option of using one password to access all services we provide.

Passwords should not be included in automated log-on processes.

Should temporary passwords need to be set they should be uniquely generated and not easily guessable.

##### Encryption of Authenticators

Authenticators, including passwords, must be encrypted in transit using a secure protocol (including, for example, TLS).

Authenticators, including passwords, must be stored in ways that mitigate offline attacks (including, for example, by use of secure salting and hashing). They should never be stored in cleartext.

Encryption standards must comply with our Encryption and Key Management policies.

##### Expiration

Authentication services:

 - must expire sessions for services that process Sensitive/Regulated Information either through an inactivity idle timeout or through an absolute lifetime; and
 - should not force the expiration of passwords (e.g. forcing users to rotate passwords every n days).

##### Revocation and Renewal

Authentication services:

- should permit users to change their own passwords and other authenticators; and
- should allow users or workforce members to revoke sessions, in case of account compromise.


##### User Functionality

User functionality (including user interface services and web services) should be separated from information system management (e.g., database management systems) functionality.

#### Network Security Requirements

##### General Network Requirements

The Engineering Team and the Service Reliability Team shall design and manage in-scope networks and network devices to achieve the following:

- networks should be isolated from each other as appropriate to achieve business and security goals, or comply with legal requirements;
- data flow across each network should follow defined, enforceable paths;
- networks should be segmented internally to isolate services that process Sensitive/Regulated Information;
- external connectivity to the Internet should be by whitelist, and follow least-necessary principles;
- Bluetooth and peer-to-peer networking protocols within the information system determined to be unnecessary or non-secure are disabled;
- network entry points should be documented;
- all external connections (VPNs, SSL/TLS endpoints, VPC peering, etc.) should be approved by the Service Reliability Team; and
- network administration activities shall be logged and monitored.

##### Network Segmentation

Networks must be designed such that they segment tenant/customer access from other tenants/customers as appropriate, based on the following considerations:

- the ISMS;
- isolation of business critical assets and/or sensitive user data, and sessions that mandate stronger internal controls and high levels of assurance; and
- compliance with legal, statutory, and regulatory compliance obligations.

##### Network Diagrams

Network-architecture diagrams shall be created that clearly identify high-risk environments and data flows that may have legal compliance impacts. Network diagrams shall include wireless networks. The network diagram is updated whenever there are network changes and no less than every six months.

### Terms and Conditions

The Engineering Team shall determine whether new systems should include banners or links to documentation sources that describe the terms and conditions that apply to the use of our systems.

### Outsourcing

If production development is outsourced, security requirements that meet or exceed internal company policies should be included in the contract(s). Outsourced development work is required to track and disclose security flaws, remediation, and findings to the Security Officer.

### End of Life Software
If systems or system components in production are no longer supported by the developer, vendor, or manufacturer, the company shall obtain evidence of a formal migration plan approved by leadership to replace the system or system components.

## 3. Secure System Development

### Secure Engineering Principles

The Engineering Team shall maintain standards for engineering secure systems. These principles and procedures shall be reviewed and updated at least annually.

### Source Code Access Control
	
We use GitHub for source code version control. Source code must be stored in private repositories. Code should be treated as Restricted Information, and access to it by workforce members should be restricted based on business need.

### Code Reviews

All substantive changes to source code for in-scope applications must be reviewed before merging and deployment to production. Maintainers who are specified on a per-repository basis in each repository's documentation may approve changes. Change approvals must be documented in a GitHub pull request comment.

When reviewing a code change, a team member should check each of the following areas:

- Does the code change alter the application’s dependencies? Does it introduce any nonstandard libraries?
- Are all new functions introduced in the change covered adequately by unit and integration tests?
- Is the new code readable and will it be easily maintainable by future developers?
- If the code change fixes a bug discovered in the application, has a regression test been added that would have detected the bug?

If the code change touches any of the following functions specifically related to the security of the application, the reviewer should pay special attention and should document in their review what they reviewed, and how they determined that no unsafe changes were introduced, per the Secure System Design:

- authentication or password requirements;
- access controls;
- audit logging;
- session management, or password expiration;
- transmission security; or
- data integrity and validation.

In addition, a team member checks the validity of syntax and semantics as a function of application scanning validation for the following type of information system inputs to verify that inputs match specified definitions for format and content and to ensure accurate and correct inputs that can prevent attacks such as cross-site scripting and SQL injection:

- character set
- length
- numerical range
- acceptable values

Once a change record is approved, updates must not be made to the change record with the exception of additional supporting information and implementation status and outcome.

The company's external business partners must adhere to the same policies for change management, release, and testing as internal developers within the organization.

### No Default Accounts

Diagnostic functions and test accounts must be disabled prior to shipping code to production. When possible, this functionality should be removed entirely, otherwise it should be disabled with a flag or configuration change. All default passwords must be changed.

### Security Test Coverage

The Engineering Team shall write unit tests for critical security functions. Static testing (such as linters) should be used when possible. Tests should validate data input, output, and technical interoperability. Code review should include evaluating whether test coverage is sufficient.

Media containing diagnostic and test programs should be checked for malicious code prior to use.

### Test Data

Test data shall be carefully selected to exercise all potential code paths. Test data shall not contain Sensitive/Regulated Information.

### Production Data Restrictions

Production data must not be replicated or used in non-production environments. Any use of customer data in non-production environments requires explicit, documented approval from all customers whose data is affected, and must comply with all legal and regulatory requirements for scrubbing of sensitive data elements.

### Data Inventory and Data Flows

The Engineering Team must inventory, document, and maintain data flow information for data processed by the information systems.

Data flow diagrams or other schematics should describe:

- where data comes into the system;
- where and how it is processed;
- where it is stored; and
- when and under what conditions it leaves the system.

This information may be contained in the README or other documentation for applications or systems. Any specific potential legal (contractual, regulatory) requirements should be noted in the documentation.

### Use Standard Libraries

Whenever possible, the Engineering Team should prefer libraries, frameworks, and other software components that are widely used, well-tested, and well-understood. Custom modifications to software packages are discouraged, and should be strictly limited to necessary changes, and any such changes must be documented in source code version control.

### Specific Design Requirements

We may require that specific functions or features are included in systems.

## 4. Secure System Deployment

### Continuous Integration

Code tests should be run automatically using continuous integration ("CI"). CI robot user access privileges must abide by the ISMS Access.

### Staging Environments

Changes to in-scope applications, operating systems, and other components shall be deployed to a staging environment and tested for acceptance prior to production deployment.

Independent acceptance testing proportional to the importance and nature of the system is performed both for in-house and for outsourced development to ensure the system works as expected and only as expected.

### Production Changes

Production deploys should be coordinated across the Engineering Team and the Service Reliability Team, especially when multiple systems or database migrations are involved.

All in-scope code changes must be committed to source code version control. Users should also document:

- intended and side-effects of the change;
- rollback procedures, if applicable;
- evidence that testing occurred, consistent with this policy; and
- any added dependencies or other third-party software introduced by the change.

Change records must be retained.

All changes to company production services must be approved according to the following rules, depending on the type and criticality of the change:

- **Pre-approved** changes include edits to documentation and other non-functional changes. Pre-approved changes do not require code review.
- **Standard** changes are approved via GitHub’s approval process by code-repository maintainers.
- **Emergency** changes may be approved via Slack, phone, SMS, or any other method.

Named approvers must be documented in associated change records marked as approved by the Engineering Team or the Service Reliability Team.

### Fallback

If deployment or changes are unsuccessful, resulting in loss of functionality or downtime, the team lead shall abort the deployment and revert back to the prior build/version.

## 5. Secure System Maintenance

During the maintenance phase, the company shall perform maintenance activities on our information systems, as deemed necessary by the relevant asset owners or the Engineering Team. This includes a review of the information system within every three hundred and sixty- five (365) days to identify and disable unnecessary and non-secure functions, ports, protocols, and/or services.

Maintenance performed on systems shall only be performed when authorized by the asset owners of the relevant assets (as defined in the Asset Inventory) or by the Security Officer.

Once a system has completed maintenance, the company shall ensure that the asset meets the design requirements that applied to it when it was originally developed and deployed.

Asset owners shall log all maintenance activities that have occurred in the Asset Inventory.

# Logging

# Logged Events

## App Audit Logging Events

For every in-scope application for which we control logging, the application's owner (as identified in the Asset Inventory) shall ensure the following events are logged, if applicable:

- creation and deletion of user accounts;
- creation and deletion of customer admin accounts;
- creation and deletion of admin accounts;
- session creation/log in;
- session creation failures (e.g. invalid access credentials);
- session deletion/log out;
- user elevation of privileges;
- user access control changes;
- user impersonation;
- user access to production systems and data, including by workforce members, contractors, and vendors; and
- user access to audit log files.

## Host Audit Logging Events

For every in-scope host where we control logging, the host's owner (as identified in the Asset Inventory) shall ensure the following events are logged, if applicable:

- system administrator activities;
- failed access attempts (failed SSH, etc.);
- initialization of audit logging systems;
- stopping or pausing of audit logging systems;
- changes to baseline configurations; and
- detection of suspicious or malicious activity, such as from an intrusion detection system, antivirus system, or antispyware system.

# Log Content and Format

Each audit log event must include the following information:

- identification of the user;
- the type of event;
- the data, component, or resource affected by the event; and
- the time of the event.

When possible, each audit log event must include:

- the outcome (status or response); and
- the origin of the event (such as IP address).

# Log Retention Policy

Audit logs shall be retained in compliance with all applicable statutory, regulatory, contractual, and compliance requirements.

Logging-system owners shall specify retention requirements for logs and archival/deletion strategies in the Asset Inventory.

Audit logs for assets that store or process Sensitive/Regulated Information (including HIPAA PHI) must be retained for 6 years.

Audit records are retained for 90 days and older audit records are archived for one year.


# Log Protection Policy

Logging-system owners must protect logging destinations and log information against tampering and unauthorized access in the following ways:

- logs must be transmitted over encrypted channels;
- editing and deletion of logs shall be restricted: Logging-system owners shall enable audit controls and alerts for edit/deletion actions if those controls are available;
- access to logs shall be on a need-to-know basis only; and
- logging-system owners shall configure alerts and notifications to prevent storage capacity of the logging destination from being exceeded, resulting in overwritten or lost logs.

# Log Review and Alerting Policy

## Log Configurations

At least annually, the Security Team shall work with the Engineering and Service Reliability Teams to review the list of events that are logged for each asset, as well as the list of alerts that are configured. The teams shall update the events being logged (or alerted on) if determined to be necessary.

## Alerts

Logging-system owners, in conjunction with the Security Officer, shall determine which events generate alerts, alerting criteria (rules for triggering the alert), and dependent alerting systems. Alerts shall be investigated as potential security incidents, and shall be reviewed, investigated, and reported on in accordance with the Incident Response Plan.

Audit logs should be reviewed via automated means whenever possible to support audit reduction and report generation.

## Log Rationale Validation

The company shall provide rationale that auditable events are deemed adequate to support after the fact investigations of security incidents and which events require auditing on a continuous basis in response to specific situations. The listing of what is logged and audited, along with their supporting rational, are reviewed and updated on an annual basis.

# Host Hardening

System clocks shall be synchronized for hosts we control to a single reference time source. Access to system clocks shall be restricted, in accordance with the Access Management Policy.

The Security Team shall ensure that hosts that we operate are hardened based on the Center for Internet Security’s [Security Configuration Benchmarks](https://www.cisecurity.org/cis-benchmarks/). Hardening logic is applied to hosts when they are launched via Chef recipes. The following hardening measures are applied on every host that we operate:

- operating systems are installed on hosts only from bare images, and only via automated configuration management (services installed can be enumerated upon request);
- host password logins are disabled and SSH root keys are not permitted;
- swap is disabled to avoid writing in-memory secrets to unencrypted volumes;
- command history for shell sessions is disabled;
- non-default SSH ports are used;
- no password-based services are installed automatically—password-based services (such as PostgreSQL) are provisioned only with unique, per-resource passphrases. No default passwords are permitted;
- host security updates are automated; and
- all host ports are opened only via whitelist.

Time data is protected and controlled from unauthorized access.