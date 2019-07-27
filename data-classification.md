
## Sourcing

The most ideal solution would handle data from all of the major places that we have it:

* Databases
* Data Warehouse
* Data-related Services (caches, ML pipes)
* Wikis
* ticket systems
* Backoffice tools
* Intranet
* Email
* Drives / doc stores
* Chat
* Customer Support

It's likely that this list can morph, based on business practices.

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

