# Incident Response Topics

## Semantics

### Types of Incidents
* Data leak
* Breach / penetration
* Leak/Breach from Partner
* DDOS
* Fraud
* Platform SLA
* Partner-specific SLA

### Timeline elements for Reporting
* incident start
* incident end
* investigation stage
  * system scope
  * product / LOB scope
  * user scope
  * partner scope
  * client scope
* escalation/decisions/changes stage 
* Customer impact area(s). Evidences.
* First client comms
* each ongoing client comm
* client followup comms

### Breach Announcement
As with all matters related to data breach, research should be kept confidential and shared only with senior leadership involved in the announcing the breach.

#### Time periods
* Of downstream breach
* Of overlap

#### Totals

##### People
* those with PII leaks
* in each class of data

##### Types of data revealed
* particularly high-status data
  * PII, PCI, PHI
  * specific fields

Accounts, passwords, SSN, address. I think this is probably the data classes that we recently defined in the RFC for data classes.

* Financials, if money stolen.
* Scope of financial burden for remediation.
* Special topic.  Not always needed.

* Partners that were involved
  * Follow executive guidance on Partner types / classification.

#### Degree of certainty 
about any of these figures, particularly the number of people impacted. 

* No more that
* between X-Y
* was exactly
* likely was less



## Incident Scopes

### Priority Kinds
#### Priority #1 - Emergency/Urgent:  
An Incident has caused a complete and immediate work stoppage affecting at least one primary business process or a broad group of End Users. No workaround is available.
#### Priority #2 - High:  
An Incident has affected a business process in such a way that business functions (operations) are severely degraded, multiple End Users are impacted or key external customer is affected.  A workaround may be available, but it is not easily sustainable.
#### Priority #3 - Medium:  
An Incident has affected a business process in such a way that certain business functions are not available to End Users or external customers, or a system or service is degraded.  A workaround may be available.
#### Priority #4 - Low:  
An Incident has little or no effect on business processes or operations and can be handled on a scheduled basis (e.g., preventive maintenance).  A workaround is available.  

Incident will then continue with containment, eradication and post incident analysis. Bi-Yearly tabletops are held to test the program  

### SLA: definitions 
- In contracts / ensure standard language
    - impact times
    - contact info during incident (us & them)
    - All contracts / SF records ideally to be updated
- Account annotation for modification from standard
    - Zak put this in Salesforce for BD/PS already
- Ops-driven Dashboards / ‘pager’ alerts
- Runbooks for each impact-level (amber, red)
    - error codes, (for app colophons)
    - Comms templates, internal
    - Comms templates, client (perhaps: major, vs. minor)
    - Escalation triggers
    - Logging

### Data breach, internal
- Contract language for data breach contact
- Ops-driven Dashboards / ‘pager’ alerts
    - IDS (intrusion)
    - PII / PHI / PCI movement
- Runbooks 
    - Forensics / log preservation (may need training)
    - Retained cyber analyst, vector analysis
    - Warroom
    - Impact scope
    - Comms templates, affected partners (supply & demand)
    - Comms templates, unaffected partners (supply & demand)
    - Comms templates, press
        - include Common elements
    - Comms templates, board/investor

### Data breach, partner
- Same as internal, plus:
- establish contact with partner sec team, co-warroom
- Timeline analysis pinpoint Even exposure window
- Analyze scope (specific fields of PII, PCI, PHI)
- Comms templates, internal
- Comms templates, unaffected partners (supply & demand)
- Comms templates, press
    - include Common elements
- Comms templates, board/investor

### DDOS
- Runbook for extortion / threat-comms
    - capability assessment 
    - cyberSec / DDOS contractor retained
    - comms control
        - Warroom 
        - Negotiation / delay
    - FBI escalation threshold
- Runbook for live attack
    - Activate static and API caching
    - Global traffic response / readiness 
    - Comms template: partner, SLA/SLO notification bluff
    - Comms template: partner transparency

Timetable for (minimum) yearly exercises.
- Needs to be in corp cal
- Retro / minutes from each exercise
- New/old staff

### Fraud
- Same as internal, plus:
- legal review of related insurance policies
  - operationalize following guidance to enable claims
- if needed, establish contact with related partners
- Comms templates, board/investor

## Per-incident occurrence
- Incident ‘war room’ 
    - Generally private, to protect forensic discussion in a data breach
    - Probably use the same warroom (slack channel) for all incidents.
    - At bigger corps, potentially diff channels for each potential incident, for forensic trail/logs
- Post-mortems
    - Produce tickets for action items
    - Minutes
    - Breaches needs SECCOM ticket with label `review-security`


### Involvements
* What communications template(s) were used?
* What medium were the comms sent through? (social media channels, a service desk, a status page, email, etc)
* Who sent each out?
* Contact address for where each affected party?

### Post mortems

#### Timeline
* If we did not communicate early and often with customers, why not?

#### Involvements
* What path did we send customers down when they reached the error page? 
* Is this a typical flow for customers when there is an error?
* What atypical solutions were used or developed with customers?
* How did we determine who would communicate out to customers?
* Did we communicate to the right customers? How do we know?

#### CX
* How would you have felt as a customer if you encountered a similar issue?
* Did the comms we sent out reduce the need for customers to contact our support team?
* Were the mediums/channels used easily accessible/visible for customers? How did they know where to find it?
* What do our customers now know about this incident solely from the comms we sent out during/after the incident?

 

## Notes

For audits, most of these things will need some kind of screenshot, for proofs

Have identified press / journals, and alternatives 

