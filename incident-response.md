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



## Incident Scopes
### SLA: definitions 
- In contracts / ensure standard language
    - impact times
    - contact info during incident (us & them)
    - All contracts / SF records ideally to be updated
- Account annotation for modification from standard
    - Zak put this in Salesforce for BD/PS already
- Ops-driven Dashboards / ‘pager’ alerts
- Runbooks for each impact-level (amber, red)
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

