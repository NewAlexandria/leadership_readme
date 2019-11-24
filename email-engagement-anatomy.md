# The Anatomy of Email Engagement Systems
 
## Email Database

First Party 

The addition of these services will require the storage and access of data gathered about an email, external to a lead. This database would facilitate campaign (or another microservice) in being able to manage these in an abstract manner and fork updates to relevant subscribers (like ESPs).
a) Email lookup table (id, email, hash? )
b) Events Tables (ESP and Suppression-management - add event source to public.events?)
c) Statuses Table (FA, Suppression-management, etc)
 
## Campaign Management

Ongage is an email management tool which sits above ESPs (and SMS) to consolidate information and allow marketing to create transactional, drip, and campaign based email changes without engineering involvement (post setup)

#### Pattern

1. Integrate SG via API tokens put in Ongage, separate via IP.
1. Feed new leads into Ongage via their API (dupe info coming from SG)
1. Add events to fire to ongage
  * Current TXL trigger (Rate Table Created)
1. Create webhook receiver to receive ongage events and replicate to DW
1. Remove TXL and Remarketing Email from current system (handoff to marketing to turn on Ongage version)
1. Rollout across rest of email ecosystem.
 
## Social Sourcing

Social a useful tool for lead gen and consumer engagement.  

Influencer profiles are an important part of outreach, requiring training just like any other facet of PR. 

## Address Validation

Fresh address is an API which provides statuses for an email’s likelihood of deliverability. Given an email address, systems should return statuses like `spam trap`, `disposable email`, `regular complainer`.

##### ​Engineering / Integration

* Just before triggering the current TXL trigger query email status and report to the Unsub/validation system
  * Integrate, e.g., Fresh Address API as service
  * Create cache based on hashed email to avoid re-querying FA (Statuses Table in Email DB)
  * Patch contact in Unsub/Validation, with the status
 
## Global Suppressions

* Unsubscribes
* Spam Reports
* Bounce List

Aim to build a centralized suppression list management solution, to manage unsubscribes across emailers (internal and 3rd party) and improve distribution to vendors.

##### ​Engineering / Integration
​
* Subscribe to an API/Webhook for the unsub system(s), and append to Supression system when a related event occurs
* Save unsubscribe event to email DB events
* Add status/label as ‘likely uninterested’, or a similar method for cautious low-risk re-engagement
 
## Reputation Monitoring
 
Pipeline Updates For New Sending Domains
Setup each to be usable by the Unsub system

* Authentication
  * DMARK
  * SPF
  * DKIM
* MX / Reply Setup
* Setup IP (s)
* Map the ESP setup to Unsubs based on IP
 
### Supply partner isolation

Create a pipeline to create and monitor isolated domains for partner sends.

1. Script (TF template) creation of DNS entries, CF Distro, Lambda@Edge to only allow approved PPs, pointing to consumer service.
1. Create monitoring dashboard for maintenance and view of existing domains

## Inbox mechanics

Time to inbox audit and improvement
Get our TXL email in inbox first

* Audit campaign and make sure we send out the email ASAP
* [length clipping](https://www.adestra.com/blog/avoid-gmail-clipping-emails/)


## Fraud

**Types of Fraud Risk**|**Result of Risk**|**Manual indicators or precautions**|**Automatic Proactive Precautions**|**Reactive Precautions**
-----|-----|-----|-----|-----|-----
Bot Traffic|Wasted ad budget |Spike in traffic/ conversions * Low Retention * Low Activity||Manual review of traffic in BI deep dive
Click Fraud|Poor optimization|Wasted budget|Abnormal Click to acquisition ratios.High Activity, Low/high Retention/acquistion| [Forensiq (Impact Radius)](https://impact.com/ad-fraud-detection/),[White Ops](https://www.whiteops.com/),[Fraudlogix](https://www.fraudlogix.com/),[Integral Ad Science](https://integralads.com/)|BI deep dive
Conversion Fraud|Revenue impact twice over as money for fraudulent conversions can’t be used for legitimate traffic.|High # of acquisitions with low activity| |BI deep dive
Fraud signups and application |* Fake acquisitions resulting in low brand expectations * loss of reputation * Demand side conversion issues|increased signups and decrease or stagnant conversion | https://sift.com/products/account-defense, https://trunarrative.com/what-we-do/application-fraud/, https://www.datavisor.com/industry-solutions/financial-services/application-fraud/, https://blockscore.com/ |BI reviews
Content Fraud|Fines, loss of reputation|Spike in traffic/ conversions * Low Retention * Low or extremely abnormal high Activity|Performline|* Manual review of traffic * Audit Scanning|
Email Fraud|* CANSPAM violations * loss of reputation * low conversions | * Low Activity,Complaints|Lashback||