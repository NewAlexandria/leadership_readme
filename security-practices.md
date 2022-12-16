# Security and InfoSec

## Topics for a Governance Framework

* Policy maintenance and alignment
* Incident management
* BIA / DR
* **Risk modeling and profiling**
* **Data Classifications**
* **Ongoing monitoring**
* Onboarding
* Practices training
* **Hardware operation**
* **Configuration and access controls**
* **Site(s) security**
* Audits fulfillment
* Vendor Management


### Meta-Model

1. Burden of practicing
1. Burden of regularity
1. Personal practice consistency
1. Facilities practice coordination
1. Partner/Vendor audit relations
1. Executive approval and Delivery
1. Cross-team planning and ownership


## Reportable Systems

The point of this section is to give a sense for what kind of things could be audited, and why. It is not a complete list of what is in an InfoSec policy.  Rather, It is meant to be a frame of reference, for practices excepted by policies and InfoSec processes.

* applications, systems, databases, platforms, and other technology that receives, Stores, processes, handles, or has access to PII,
* all locations where Supplier receives, Stores, processes, handles, or enables access to Fidelity Confidential Information in physical form,
* all categories of physical computing and software assets
* uniquely identify each individual that has access to PII, whether in electronic or physical form
* grant access to PII only to authorized individuals based on the principle of least privileges
* follow the Security Requirements when Storing, accessing, handling, and processing PII


## Docs & Records

#### General Practices

1. Audits
    1. Automation / integration design
2. Analysis for sec. topics / scope:
    1. New Strat plan
    2. Policies
    3. vendor management (Sec-related)
3. Onboarding
    1. Hardware
    2. Trainings
    3. Exercises (BC/DR)
4. Governance
    1. Classifications
    2. Infosec
    3. x-team practices planning/review

##### Meta: Access scope

perm: 

* email
* wiki
  * plans / specs
* ticketing
* drive/docs
  * policies
  * SOPs
  * plans / specs
* logging
  * audits
  * ops risk models

task-specific:

* entitlements records / configs
* data classification configs
* cloud(s) security configs
* SaaS security configs
* vendor comms, engagement


### hardware operation

* hardware assignment inventory
* Antivirus profiles

### practices training

* encrypted chat / shared secrets.
* new-hire email(s)
* new hire confirmation(s)
* security slide deck

### configuration and access controls

* dashboard of work in PM tool (Jira)
* Entitlements and Services sheet.
* Overarching list of infosec processes
  * Cadence: ongoing logging; rate of human checking; ad-hoc
  * Schedule show last times checks were made
  * 3rd Party audited (Y/N)
* Our AWS-specific audit
* Overarching Security Posture

##### Scheduling 

Many different things sec/audit things need regular check-up, and also that auditors want to see confirmation of a max-interval when each was performed.  A calendar, e.g. in google cal, called Audits, can act as the central dashboard for all of these.

Each cal item would be named after the control that drives it, with name/category/links/etc in the body of the cal item.  This will also make them searchable.  A new column can go in the audit sheet(s), for whether there is a calendar item set for that control;  maybe a link to the event.

### audits fulfillment

* Partner/client-facing doc, listing our infosec process & posture
* Security folder in Drive: sec audit deliverables
* Partners and Clients that audited us, and mapping to our master infosec process

### vendor audits

* Our auditing of vendors

### ongoing monitoring

Security monitoring should be treated as a form of QA.  It will live outside of the Product QA organization, or any line of business (LOB).

* Pen testing.
  * yearly
  * with releases
* Entitlements Monitoring sheet.
* Tempo of audit logs across infosec topics.
* Alerting triggers/

### incident management

* Team Runbooks
  * Convenient docs to hand-off to non-eng non-sec teams, for client and partner comms.
  * Streamline new or custom requests that need Eng Sec involvement.
  * Data breach response, and SLA (maybe the same as our Incidence Response)
  * adding new infosec practices.

[Atlassian put together a nice collection of pages for the  tech-ops aspects of incident management](https://www.atlassian.com/incident-management).  Many of them can inspire generalizations

### site security

* entry and access
* sensors and recording systems
* smart building systems
* flow control
* training
* spot checks
* vendor services management

## Practice Guidance

### Policy maintenance and alignment

* Review existing policy docs to confirm accuracy.
  * Business Continuity and Disaster Recovery policies (BC / DR)
* Yearly review and sign-off

### hardware operation

* Setup of newly-bought hardware in a timely manner
* Reformatting of transferred hardware (upgrade, departure, repairs)

### practices training

* HR needs to be the recipient of most training confirmations, for legal reasons.  EY and similar auditors demand historic validation of this.
* DR recovery exercises, records, and evidence
* BC exercises
* Incident response exercises

### configuration and access controls

* AWS best practices by industry-standard
* changes within timesframe committed by contract
* setup and disabling of account access (any tool) in a ticketed manner
* access changes by request, also ticketed. (e.g. eng-support)

### audits fulfillment

* Developing and Maintaining practices mappings.
* Ability to speak to specifics and justifications, in an audit.  Our partners keep detailed records of everything we discuss with them, the timing, and our stated rationale. 
* Keep well-organized files in the Drive.  Don't store things in email, where they can be lost.  Not saving-to-drive should be an exception.
* Make copies of files / folders sent to partners in an audit.  As we change our practices, we would be linking to files that are not what they partner saw. 

### vendor audits

* A multi-faceted process that involves more than just engineering. 
* Staged, and sets of questions incorporated organically into bizdev and other client relations, in an ongoing fashion.
* Types / definitions, or properties / labels
* When to have practice symmetry vs. not.

Changes can require team-time, or vendorized support, which can drag out without the team having available headroom.  Usually auditors set multi-month timelines for remediation, which do not block the launch of new business.

### ongoing monitoring

* cross-team metrics
* per-team metrics
* key systems
* edges (networks, machines, etc)
* acceptable ranges, and health definition bands
* logs + exception summarization (secondary reporting)

### incident management

* runbooks
* trigger definitions (via monitoring)
* comms templates
* comms scope
* personnel chains
* training
* exercises

### Site security

* visitor registration
* CCTV
* door/window security
* street-level access
* manual confirmation
* elevator controls
* chaperoning
* badge control

## Access entitlement audit

The complete list may not be necessary at the start of setting up an access & entitlements audit program. This is a summary of possible dimensions to audit, especially in the case of a SaaS/app with an uncertain auditing history. (i.e. a reset)

1. Admin activity log, if any
1. Number of accounts
1. Number of admins
1. Team groups, if any
1. Match SaaS team size to HR team size
1. Number of Accounts to non-even

Then, a log should record that the entitlements were audited

* software / system
* datetime
* person checking
* yes/no confirmation, or
  * list of which audits performed, or
  * name of audit-scheme-version performed


# Integrating with Partners and Vendors

### Auth and Roles

* types of systems they use for auth
* ” ” ” for permissions (e.g. active directory?)
* hardware keys / 2fa / etc?  (might say more SaaS/integration names)
* name of roles they have
* do they use those roles in all cases?  are there edge cases?
* is he involved in related audits? Does have have ‘ops needs’ that relate to compliance?

# Cyber Kill Chain

The concept of a cyber kill chain involves the identification of E2E attack strategies.  Identification allows teams to devise comprehensive multi-layer strategies for operationalizing cybersecurity.

1. Reconnaissance: harvest loose ends outside the secure system   
2. Weaponization: engineering an exploit to an attack vector
3. Delivery: launching the exploit
4. Exploitation: mechanics of the exploit
5. Installation: malware and other assets
6. Command & Control: sending and receiving of instructions, information
7. Objectives: performing the intended action, data harvest, etc.

# References

* [awesome-list of IAM tools](https://github.com/kdeldycke/awesome-iam)