# Testing of Relational systems to Event systems

We need to make sure that each service can do things on its own, while also we need to understand if they work together in concert.  Replaying an event stream can validate both.  Replays would be done be

## Service Health Permutations

A classic strategy would be to rerun this a few times, for each service. Then we could run a tier of tests that ensure failsafe against network segmentation / unavailability, and the interoperation between services. I’ve had to build these layers of tests, and it’s both reliable and efficient to maintain and scale. 

In the context of an event-driven set of services, there are some new strategies ways to implement this pattern. Some core patterns that need to be tested revolve around parallelism:

* Services’ stand-alone functionality
* Correct interaction with related services
* Stability when other services are down
* Recoverability from downtime,  segmentation, and multiplicity. 

## Test Types, or Layers

The above link calls out the kind of test-isolation layers that we should look for in this situation.  The app-level integration tests (usually focused on interfaces), can be generalized here to any application’s or service’s interface with another.  In this way, we can preserve the ideas of 

- Service unit tests
- API static schema exerciser
- Happy paths
    - Operational integration tests
    - Multi-step integration tests
    - Multi-service integration tests

## Service Dependencies

These tests would work within the scope of each service, e.g. Customer, User, Roles, Contract, and Approvals.  For multi-service ‘workflows’, there it seems there is some degree of order needed: Customer & User first, then Roles & Contracts, and finally Approvals.  This is based on the assumption that they stack in this way – but in principle this would work in regardless of the appropriate order.  This order could be defined as a dependency tree, in the test harness config or in a more generalized config as for terraform or kubernetes.

## Seeding event data

The typical sources for testing data are 

* backups, 
* exogenous imports, and 
* seed data.  

These can be read from relational databases, flat files, graph stores, etc.  In all cases, the importance lies with correctly translating source data into network events.

The primary way to accomplish this is with the services / applications themselves.  Specific business logic is generally located within a specific service.  Such [micro] service design patterns include an initialization function that translates stored data into event activity.  

Such initialization need not be limited to bootstrapping, but can also be applied to 

* cache-warming, 
* data for test mocks or 'fabracations', and 
* 'live event simulation' for compliance. 

### Seed Generation

An ideal strategy is to generate seed data from sources, using statistical modeling.  Such methods include 

* bounds identification, 
* freshet distribution, 
* holographic reduced representation, 
* fast-fourier transform, 
* irrelevant variable removal, 
* spectrum-based variance localization
* and others

These and others form a general class of heuristic analysis that can be used to produce data kernels for seed data.  Besides derived data, it is important to add ‘oracle’ data, such as canary data that was known to cause issues of specific risk. 

Sourced (non-seed) data needs to be ‘fuzzed’ or changed to anonymize values that could represent PII, trade secrets, IP, or otherwise. Sourcing such data from a sanitized dictionary is more correct than scrambling or permuting the data in-place data, since sufficient analysis may reveal clues useful in a security/hack operation.  

### I18n
Even then, ideally the created data follows certain situational norms, such as person-names localized to the jurisdiction / society of the users, heuristically-correct data bounds, etc.  

### Validation

Data seed generation needs to be a first-class app/service with its own validation.  In addition to programmatic analysis, manual analysis can be performed intermittently, as part of the company’s compliance process. 

## Test framework as Event listener

Since this is an evented system, any integration testing layer can be be multi-purposed to look for emitted events — instead of, or in addition to, a classical response (REST, or language API/hooks). The same tests and scenarios could be used with a switch, causing the framework to use the event-based validation. Likely though, the expected events (mocked or duck-typed) would be the sole manner of asserting success of the integration test.  Some new patterns may need to be introduced, to correctly simulate Time, for scenarios involving scheduling.

One of the utilities of this method is that a large suite of existing tests can be incrementally migrated to use event-based validation.

