# Classifying Data across the Company

The need to classify kinds of data throughout the company is driven by risk audits (security, compliance, etc) that we have been recently exposed to.

Probably we are not yet at a risky scale, but it’s coming with Series B and other broad press.  While we currently have ad-hoc data classifications, any audit that requires more than attestation will want to see more than we currently have today.

## Issues:

* Determine data classes in-use today, and create a framework for thinking about them long-term.
* Determine how we classify data, so that we can search and identify data 'classes' across all of our systems.
* Data classification help with eDiscovery. For startups, that’s probably an optimistic value, since ‘Discovery’ is usually code for a law suit or other court-action.
* Sometimes data classification can pertain to diligence in an M&A or other valuation. 

## Goals

Conceivably, this kind of process(es) is to catch if PII is leaking. In that case, we would want fast(er) alerting so that we could try to prevent or halt a breach, and do forensics

We can probably say that there is a broader goal of understanding when data from one kind of activity appears in various scenarios - apps, teams, workflows, vendors, etc.   

# Strategy
## Sourcing

The most ideal solution would handle data from all of the major places that we have it:

Sourcing

The most ideal solution would handle data from all of the major places that we have it:

* Comms
    * Slack
    * Email
* Data stores
    * PII DB
    * regular DB
    * Data warehouse
    * Logs
* File stores
    * Drives
    * Cloud Doc stores
    * S3, and similar
    * Endpoints, laptops
* SaaS (e.g.)
    * Atlassian
    * Zendesk
    * Salesforce
    * ESPs
    * SSO, secrets & auth
* Non-official places
    * other cloud file stores (dropbox, office360, box, etc)
    * other SaaS (Notion, etc)

It's likely that this list can morph, based on business practices.

### Classifications Rubric

When thinking of classification, we must keep in mind the purposes that are served by developing one:

1. classification / criticality
1. security / data
1. teams dependency
1. LOB/revenue dependency
1. cost review
1. intervals

## Querying

We need to define ways to identify the things in each class of data.

There may be more than one way to query for something in a given classification.  This could result in query groups, or building complex queries.

By using a centralized approach, we have the opportunity to consolidate ‘internal data classification’ needs under one app/roof. If we do not, we will need to maintain different queries in different locations/tools.

## Monitoring

Monitoring will principally be the frequency and alerting, based on queries.

Regardless of which tool we would choose, the consolidation pattern would be to either a) sync data from others to the place that we monitor, or b) talk to the APIs of each and run queries against them for the ‘classified data patterns’. That is probably lots of tooling that we can rent instead of build + maintain.

## Centralization

We can split data search and monitoring in AWS via Macie, and other in Gsuite via a service level+config that Google offers, and others in the other data/doc repos.  The downside of that alternative is that we would need to keep the rules for each in sync.

## Implementation

Types of data could be things like

* PII,
* non-PII lead,
* ML / 'Anonymized Data',
* configs,
* client,
* financials
* vendors, clients, or similar sourcing

