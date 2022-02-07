# Overview
The Service Reliability Team shall respond to all disruptions in the uptime of company information systems (or other information systems that store or process company information or our customers' information) in accordance with our Business Continuity Playbooks (if available) and the Business Continuity Plan. Copies of these plans and playbooks should be made available to all team members who are involved. Business Continuity Plans and Policies should stored and made available from a remote location.

Emergency procedures, manual "fallback" procedures, and resumption plans are the responsibility of the owner of the business resources or processes involved; and fallback arrangements for alternative technical services, such as information processing and communications facilities, are the responsibility of the service providers. To prepare for this, each business unit shall create at a minimum one business continuity plan.

The Service Reliability Team shall: 

- respond to all disruptions in the uptime of company information systems (or other information systems that store or process company information or our customers' information) in accordance with our Business Continuity Playbooks (if available) and the Business Continuity Plan.

- maintain the Business Continuity Plan and ensure that it includes a business impact analysis that identifies which information assets are involved in critical business processes and that it assigns responsibilities for responding to disruptions to our information systems.

- ensure that our annual risk assessment includes risks related to disruptions to our information systems.

When new requirements are identified, any existing business continuity plans and emergency procedures (e.g., evacuation plans or fallback arrangements) shall be reviewed for any updates.

# Training and Testing
In order to ensure that we are prepared to respond to disruptions in the uptime of our information systems, the Service Reliability Team shall be trained on our Business Continuity Plan at least annually.

Additionally, the Service Reliability Team shall complete the following business continuity exercises at least annually:

- **tabletop exercises**, the output of which consists of Business Continuity Playbooks that can be used to respond to potential future disruptions; and
- **functional exercises**, which involve testing our ability to respond to and recover from disruptions.

# Data Backups
In order to maintain the availability of our information, asset owners must ensure that databases and data stores that we manage that have a business criticality impact rating of "high" are backed up on a regular basis. Backup intervals must comply with all of our legal, regulatory, contractual, and operational requirements.

## Backup Security

Backup systems are subject to the same security requirements as all databases, and are subject to the following requirements:

- backups must be protected by appropriate physical and environmental controls;
- backups that contain Sensitive/Regulated Information must be protected by appropriate technical controls, such as encryption;
- backups must be redundant such that maintenance or system outages do not interfere with them;
- three generations of backups are stored
- asset owners must define the level of backups required for each asset, including backup frequency, location, and retention period; and
- the procedures for restoring backups are maintained and tested in accordance with the Business Continuity Plan and policies.

## Backup Storage

The Service Reliability Team shall:
- ensure that accurate and complete records of backups are kept in remote locations and shall document restoration procedures in Business Continuity Playbooks;
- inventory records for the backup copies, including content and current location. Where possible, automated tools should be used to create and track backups;
- Store three generations of backups (full plus all related incremental or differential backups) are stored off-site, and logged with name, date, time and action;
- ensure that a current, retrievable copy of covered information is available before movement of servers; and
- test backup information following each backup to verify media reliability and information integrity, and at least annually thereafter.

# Business Continuity Plan

## Concept of Operations

This plan is designed to structure our investigation and resolution of disruptions to our information systems using a three-phase approach. We shall follow this Business Continuity Plan, or a specific Business Continuity Playbook, in responding to all disruptions in asset uptime.

## Business Continuity Planning

We shall plan our response to disruptions in asset uptime by developing this Business Continuity Plan, developing the Business Continuity Playbooks (as described in the Business Continuity Training and Testing Policy), and applying security controls for critical information systems.

## Business Impact Analysis

In general, the Service Reliability Team shall prioritize its responses to disruptions based on:

- the criticality of the affected assets; and
- the current or potential adverse effects.

Business impact criticality, maximum tolerable downtime, recovery point objectives, recovery time objectives, and security impact classifications are tracked in the Asset Inventory.

## On-Call and Alerting

Each member of the Service Reliability Team is responsible for the 24/7 response to disruptions generated through alerting for 1 week at a time, on a rotating basis.

Alerting shall be configured such that the on-call member of the Service Reliability Team is notified immediately when there is a disruption in the uptime of one of our information systems. If the on-call member of the Service Reliability Team does not acknowledge the disruption within 5 minutes, the Service Reliability Lead should be notified.

## Monitoring and Metrics

Asset owners or the Service Reliability Team shall monitor as appropriate the resource use of all in-scope systems to ensure required system performance, capacity, and availability are achieved.

## Business Continuity Phases

### Phase 1: Activation and Notification

#### Activation Criteria

When a disruption or outage appears reasonably likely to trigger the need for recovery activities, the Business Continuity Plan shall become active. The Business Continuity Plan also shall be activated when an automated monitoring tool indicates that there is an outage or disruption or when one of our workforce members manually indicates the same.

#### Notification Procedures

Specific procedures for alerts, notifications, and communication around business continuity events shall be documented in the Business Continuity Playbooks. By default, the on-call member of the Service Reliability Team should notify the rest of the Service Reliability Team of the disruption as soon as possible.

#### Outage Assessment and Escalation

The Service Reliability Team shall determine:

- the cause of the outage or disruption;
- the potential for additional disruptions or damage;
- the status of infrastructure, if applicable; and
- the estimated time to restore normal services.

The Service Reliability Lead should be notified immediately, in all cases, for incidents with the potential to cause severe impacts to us or our customers.

### Phase 2: Recovery

#### Recovery Procedures

During the recovery phase, the Service Reliability Team shall attempt to restore the affected information systems, repair any damage incurred, and resume business operations.

Specific recovery procedures for a variety of issues are maintained in the Business Continuity Playbooks.

### Phase 3: Reconstitution

#### Overview

During this phase, the Service Reliability Team shall:

- test and validate that the capability and functionality of the affected information systems have been restored;
- deactivate the Business Continuity Plan; and
- conduct any post-mortem investigations.

#### Validation

Validation of recovery should include both data testing and functionality testing:

Data testing is the process of testing and validating recovered data to ensure that data files or databases have been recovered completely and are current to the last available backup. Functionality testing is a process for verifying that all system functionality has been tested, and the system is ready to return to normal operations.

#### Plan Deactivation

Once the individual leading recovery efforts has determined that recovery is complete, the Service Reliability Team shall:

- conduct any follow-up notifications, via a status page or to customers directly;
- clean up any extra resources provisioned during the response; and
- assign post-mortem responsibilities.

#### Post-Mortem Reports

Post-mortem reports may be for internal purposes, for customers, or for both. If the individual leading the recovery efforts determines a post-mortem report is needed, the report should address:

- what happened;
- the root cause;
- the response timeline;
- the causes and effects of any notable events;
- findings by the Service Reliability Team;
- recommended actions to take by the customer; and
- follow-on actions to ensure the event will not occur again or mitigate its severity.

Internal post-mortems should also:

- address documentation gaps;
- address training gaps;
- identify any additional resources needed; and
- incorporate lessons learned into Business Continuity Plan updates.

The Service Reliability Team shall store these reports in the ticket for the disruption event.
