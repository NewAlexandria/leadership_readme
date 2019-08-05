# The Anatomy of Email Engagement Systems
 
## Email Database

First Party 

The addition of these services will require the storage and access of data gathered about an email, external to a lead. This database would facilitate campaign (or another microservice) in being able to manage these in an abstract manner and fork updates to relevant subscribers (like ESPs).
a) Email lookup table (id, email, hash? )
b) Events Tables (Sendgrid and Optizmo - add event source to public.events?)
c) Statuses Table (FA, Optizmo?)
 
## Campaign Management

Ongage is an email management tool which sits above ESPs (and SMS) to consolidate information and allow marketing to create transactional, drip, and campaign based email changes without engineering involvement (post setup)
Eng Tasks:
a) Integrate SG via API tokens put in Ongage, separate via IP.
b) Feed new leads into Ongage via their API (dupe info coming from SG)
c) Add events to fire to ongage
i) Current TXL trigger (Rate Table Created)
d) Create webhook receiver to receive ongage events and replicate to DW
e) Remove TXL and Remarketing Email from current system (handoff to marketing to turn on Ongage version)
i) Rollout across rest of email ecosystem.
 
## Social Sourcing

Social a useful tool for lead gen and consumer engagement.  

Influencer profiles are an important part of outreach, requiring training just like any other facet of PR. 

## Address Validation

Fresh address is an API which provides statuses for an email’s likelihood of deliverability. Given an email address, it will return statuses like ‘spam trap’, ‘disposable email’, ‘regular complainer’.
Eng Tasks:
a) Just before triggering the current TXL trigger query email status and report to Ongage.
i) Integrate Fresh Address API as service
ii) Create cache based on hashed email to avoid re-querying FA (Statuses Table in Email DB)
iii) Patch contact in Ongage with FA status
 
## Unsubscribing

Optismo is a centralized suppression list management solution to manage unsubscribes across emailers (internal and 3rd party) and improve distribution to vendors.
​Eng Tasks:
a) Subscribe to the Ongage Webhook and append to optizmo when an unsubscribe occurs
b) Save unsubscribe event to email DB events
c) Add status as ‘likely uninterested’ to Statuses
 
## Reputation Monitoring
 
Pipeline Updates For New Sending Domains
Setup each to be usable by Ongage.
a) Authentication
i) DMARK
ii) SPF
iii) DKIM
b) MX / Reply Setup
c) Setup IP (s)
d) Map Sendgrid setup to Ongage based on IP
 
Supply partner isolation (FE/PLAT Ticket / Mini Epic)
Create a pipeline to create and monitor isolated domains for partner sends.
a) Script (TF template) creation of DNS entries, CF Distro, Lambda@Edge to only allow approved PPs, pointing to consumer service.
b) Create monitoring dashboard for maintenance and view of existing domains

## Inbox mechanics

Time to inbox audit and improvement
Get our TXL email in inbox first
a) Audit campaign and make sure we send out the email ASAP

* [length clipping](https://www.adestra.com/blog/avoid-gmail-clipping-emails/)
