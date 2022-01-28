# Background

This Risk Management Framework describes how we think about risk and how we implement a risk assessment and treatment program.

# Scope

By default, the scope of our risk management program is the scope of the ISMS. If an interim risk assessment is performed, the Security Team may restrict the scope of that assessment to just the new or changed ISMS components.

# Risk Assessment Goals

We shall implement a risk model that meets the following objectives:

- **Comparable assessments:** New risk assessments should be in a format that allows them to be compared with prior risk assessments.
- **Reliability within assessments:** Given the same inputs, separate assessors should be able to arrive at similar conclusions using the risk model.
- **Simplicity:** The risk model should be simple and clear, with a bias towards action.
- **Reduced bias:** Before forecasts are made, biases should be reduced or eliminated with calibration training.
- **Continuous improvement:** The results of prior assessments should allow us to improve our assessments over time.

We shall consider the context, scope, and needs of stakeholders to determine the risks and opportunities that need to be addressed to:

- ensure the ISMS can achieve its objectives;
- prevent or reduce undesired effects; and
- achieve continual improvement.

We shall rely on the Risk Management Framework to plan:

- actions to address those risks and opportunities;
- how to integrate those actions into the ISMS; and
- how to evaluate the effectiveness of those actions.

# Threat Model

To identify the risks we face, we shall use a threat model that includes looking at every type of information-security threat we could face, including opportunist hackers, customers, competitors, insiders, accidents, and natural disasters. Additionally, we include threats related to all parts of the ISMS, including our in-scope systems. We don’t yet have evidence to indicate we’re targeted by advanced persistent threats (APTs), but that may change in the near future as we grow.

In determining which threats we are subject to (and thus, should estimate risk for), we start with a number of assumptions, including:

- **Communications security**
  - Over the internet, we assume that an attacker can control the entire network (for example, on many LANs, any machine can read all traffic on the network)
  - We assume that adversaries can control any machine that is connected to a network that the attacker has control over
  - Authentication requirements are disabled by default (which can result in IP spoofing and forged packets). Attackers can replay packets or try to insert new malicious packets.
- **Systems security**
  - Web apps and architecture we deploy (first party)
    - We might write vulnerabilities
    - We might rely on bad dependencies and OSS
    - Threats may come from customers and users (mostly involving unauthorized access to data)
    - Secure storage and retrieval
  - Web services we use (third party)
    - Unauthorized use
  - Laptops and devices
    - Unauthorized access is possible as a result of keystrokes and phishing
- **Operations security**
  - Changes in organizational structure
- **Accidents happen**

The following are not within the scope of our threat model:

- **Local networks**
- **Wireless networks**
- **Printers and copiers**
- **Data centers, hypervisors, and VM security** (but OS patches are in scope; e.g., Meltdown/Spectre)
- **The app layer of our vendors** (e.g., if the AWS console has an XSS vulnerability).

# Risk Model

One of our goals for our risk assessment is simplicity, as a simple risk model helps us formulate a clear understanding of risks and communicate those risks better. Thus, to assess risk, we identify our risk tolerance and compare that to the overall Risk Values of the threats we face. If any risk exceeds our tolerance, we treat it.

# Risk Model Components

## Risk Acceptance Criteria

During each risk assessment, the Security Team shall work with the Management Team to approve a risk-tolerance level, defined as the overall Risk Value that no risk should meet or exceed (for example, High). We shall use this tolerance value to determine when we need to mitigate risks and when we can accept risks: If a risk’s Overall Value is at or exceeds the tolerance value, then we need to implement more risk mitigations.

## Forecasting Impact

To estimate the impact a risk will have on our organization, we assign each risk one of the following values: 

- *Negligible:* The threat event could be expected to have a negligible adverse effect on organizational operations, organizational assets, individuals other organizations, or the Nation.
- *Minor:* The threat event could be expected to have a limited adverse effect on your organization, its operations, its assets, individuals, and/or other organizations. A limited adverse effect means that, for example, the threat event might: (i) cause a degradation in mission capability to an extent and duration that the organization is able to perform its primary functions, but the effectiveness of the functions is noticeably reduced; (ii) result in minor damage to organizational assets; (iii) result in minor financial loss; or (iv) result in minor harm to individuals.
- *Moderate:* The threat event could be expected to have a serious adverse effect on your organization, its operations, its assets, individuals, and/or other organizations. A serious adverse effect means that, for example, the threat event might: (i) cause a significant degradation in mission capability to an extent and duration that the organization is able to perform its primary functions, but the effectiveness of the functions is significantly reduced; (ii) result in significant damage to organizational assets; (iii) result in significant financial loss; or (iv) result in significant harm to individuals that does not involve loss of life or serious life-threatening injuries.
- *Significant:* The threat event could be expected to have a severe or catastrophic adverse effect on your organization, its operations, its assets, individuals, and/or other organizations. A severe or catastrophic adverse effect means that, for example, the threat event might: (i) cause a severe degradation in or loss of mission capability to an extent and duration that the organization is not able to perform one or more of its primary functions; (ii) result in major damage to organizational assets; (iii) result in major financial loss; or (iv) result in severe or catastrophic harm to individuals involving loss of life or serious life-threatening injuries.
- *Severe:* The threat event could be expected to have multiple severe or catastrophic adverse effects on organizational operations, organizational assets, individuals, other organizations, or the Nation.

 (These categories are taken directly from NIST SP 800-30 rev. 1, Guide for Conducting Risk Assessments, available [here](https://nvlpubs.nist.gov/nistpubs/Legacy/SP/nistspecialpublication800-30r1.pdf).)

These impact estimates are used in calculating, assessing, and comparing each risk.

## Forecasting Likelihood

In addition to estimating the impact of each risk, the Security Team will also estimate the likelihood of a risk occurring. The Security Team estimates the likelihood of a risk by predicting the percentage chance that each risk will occur in the next twelve months. These are grouped as follows:

- Very Unlikely (there’s between a 0% and 20% chance that this event occurs in the next twelve months);
- Unlikely (20%–40%);
- Possible (40%–60%);
- Likely (60%–80%); or
- Very Likely (80%–100%).

## Risk Calculation

To come calculate an overall Risk Value for each risk, we rely on the lookup table documented in NIST SP 800-30 rev. 1 (even though we use slightly different language to categorize impacts and likelihoods). Thus, a risk with a likelihood of Possible and an impact of Severe would result in an overall Risk Value of High.

## Risk Response 

For each risk, we shall choose to either Accept the risk (by not acting), or Mitigate the risk (by creating a new internal control/safeguard or updating a preexisting one in order to reduce the impact or likelihood of a risk).

# Vulnerability Management

In order to ensure that we identify and quickly respond to vulnerabilities in our systems, we have implemented this policy. The Security Officer shall coordinate all vulnerability-management activities.


## Vulnerability Identification

The security team shall update the list of information system vulnerabilities scanned every thirty (30) days or when new vulnerabilities are identified and reported.

We shall use a number of different mechanisms to make ourselves aware of vulnerabilities, including the following.

### Vulnerability Scans

The following vulnerability scans shall be run on a quarterly basis in order to identify vulnerabilities present in our code and information systems:

- web-service vulnerability scans on all applications listed in the Asset Inventory;
- network-vulnerability scans on all of our networks; and
- host-vulnerability scans on all of our hosts.

If as a result of the vulnerability scanning we discover vulnerabilities, the Security Team shall respond to them in accordance with the response requirements below.

### Penetration Testing

We shall perform penetration testing at least annually in order to identify vulnerabilities in our systems. The Security Team shall coordinate with other teams as needed (including the Engineering Team and the Management Team) to schedule and complete penetration testing such that it does not disrupt other business operations.

If as a result of the penetration testing we discover vulnerabilities, the Security Team shall respond to them in accordance with the response requirements below.

### Responsible Disclosure Program

In order to encourage outside parties to responsibly report vulnerabilities, we have created a responsible-disclosure program, under which actual or suspected vulnerabilities identified by outside parties should be reported to the Security Team.

If as a result of the responsible-disclosure program we discover vulnerabilities, the Security Team shall respond to them in accordance with the response requirements below.

### News Sources

In order to identify new security vulnerabilities, the Security Team shall actively monitor the following sources.

- The [National Cyber Awareness System](https://www.us-cert.gov/ncas)
- The [Openwall oss-security mailing list](http://www.openwall.com/lists/oss-security/)
- News sources, such as Hacker News and Krebs on Security
- Vendor security announcements (including AWS, NGiNX, OpenSSL, PostgreSQL, Ruby)

If we learn of new vulnerabilities that we are subject to from a news source, the Security Team shall respond to them in accordance with the response requirements below.

## Vulnerability Assessment and Response

Whenever we are made aware of a vulnerability, we shall classify it, track it, and take some action as to it (either remediate it or determine that we don't need to remediate it).

In addition, we shall review historic audit logs in order to determine if critical or high vulnerabilities have been previously exploited.

All identified vulnerabilities shall be classified—and responded to—based on the following severity levels:

- **Within 24 hours: Critical-severity vulnerabilities.** This includes vulnerabilities that allow an attacker to easily gain control of numerous systems; to compromise one or more systems containing Sensitive/Regulated Information; or to cause widespread service interruption.
- **Within 7 days: High-severity vulnerabilities.** This includes vulnerabilities that allow an attacker to gain control of one or more systems. The attack may be more difficult than a Critical vulnerability, or require additional pathways, to exploit.
- **Within 30 days: Medium-severity vulnerabilities.** This includes vulnerabilities that allow an attacker to gain access to sensitive or unintentionally disclosed information on a host.
- **Within 90 days: Low-severity vulnerabilities.** This includes vulnerabilities that pose no immediate threat to our information systems.

Patches and security fixes must be applied consistent with our Secure System Development Life Cycle requirements. When possible:

- remediation actions should be tested on a non-production environment first;
- patchers should verify that the fix remediates the vulnerability in production, post-deployment; and
- the Service Reliability Team should use tools to automate the consistent installation of patches.