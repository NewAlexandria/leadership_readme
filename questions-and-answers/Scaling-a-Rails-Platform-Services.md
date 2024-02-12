## Objective: 
Scale our Ruby on Rails API to handle 500K+ concurrent users.
### What are the typical scaling issues you encounter in a ruby on rails application? 
*What are your lessons learned from previous projects?*

There are many, I find.  App servers often have large footprints of memory even after resolving many other scaling bad practices. While there are several strategies toward alleviating this condition in a platform, perhaps the most significant is to offload activities to asynchronous workers.  For systems of the scale requested in this study, it would be most proper to use an event queue. If there are legacy systems that may lack easy/maintainable support for an ideal event server, there are several strategies for a database to act as the source of events replicated to the event queue/bus. Lately I prefer to use Temporal as the workers framework, as it supports a number of language clients.  The Temporal framework also captures great introspective information about the runs, which helps for recovery and orchestration.  

In a rails project it’s typical to lean into the callback systems involved: Activerecord, a state-machine like AASM, action cable, and any others.  This can also lead to confusion for less-senior engineers, and requires good linting in order to ensure that errors are raised or handled correctly, and the request boundary reinforces restfulness.  The memory activities of mono- and meso-lithic apps needs to be closely monitored to decide when and where to split into a smaller services. This is separate from offloading worker activities.  

The environment of the test suite can often be in disarray, with poorly labeled test groups, weakly structured factories or fabrications, poor reliance on fixtures, and overlapping test scopes, often with loose semantics.  [I expand on this here](https://leadership.newalexandria.org/qa-test-framework.html). Often the root cause of these has been driven by systems with coarse semantics and poor SRP in the codebase.  

Authentication and permissioning may also have unresolved design issues.   Good choices of linting rules can setup a program for resolving many of these things. Quality evaluation frameworks need to extend beyond ‘tests’ to monitoring practices that encompass the data stream, engagement lifecycles, all of which need traceability for feature flags, data model versioning, and the client or hardware device fleet. 
### How would you implement horizontal scaling in ROR?

For the scale of an application with 500,000 concurrent users, the design of UX expectations, as well as interactive side-effect and their expected resolution window - will all influence choices for an architecture that supports today and the future.  

As mentioned above, monolithic and mesolithic apps need to be evaluated for their memory footprint, resource churn, and available services.  Partitioning an app’s services can then reduce the total footprint and allow multiple runners with a compatible resource fingerprint.  Endpoints need to be restful relative not only to the DB, but the entire transaction boundary.  Where users can tolerate some asynchrony, state machines or similar but liteweight governing mechanisms can coordinate the multiple worker/services that process events for a given interaction/transaction lifecycle. 

In the case of a user-client that may need many pieces of data via websocket, a balance needs to exist between the amount of events (in a interaction/transaction lifecycle) and the criticality.  The client app can increasingly maintain a registry of event expectations before it allows that part of the UI to become ready. Or the user may need implicit training on how to recognize partial readiness. 

Routing between these services would involve normal things - CDN where assets or feed/pub data may be long-lived, regional routing via DNS, and kube clusters to support blue/green and other availability.  The CDN or internal DNS network edge can also hold auth services, with high availability and updated auth model state. 

There is more that could be said about CI and deployment orchestration, builds and artifacts, including webpack, and maybe ‘building’ from a rails-monorepo, etc, including if a full react / SPA-style app architecture exists (no need for that since we all efficiently use ActionCable for most things, right?)
### What typical DB changes are needed for scaling?

While we should presume correct data model design, and indices, it’s worth mentioning that these need review from time to time.  Probably the first step-up from smaller apps is the use of views and persisted views.  The recalculation of persisted views needs to accommodate client apps, and may involve triggers sending notif to app hooks.   A database cluster may need to be rebalanced for ingest and write, while monitoring time-to-availabilty at read nodes. 

Data tables / schema may need to be partitioned across more than one database, so that vacuuming, de-skewing, and other garbage collection can be more controlled.  This most commonly occurs due to high-turnover tables, so the impact can be minimized by uses queues like redis. Redis particularly has a robust module system for doing some processing, prior to other apps/workers processing the data into a DB for apps, or laying down data onto S3/disk/etc, for later analytics, data ops and orchestration and other things upstream of the warehouse/lake.

### How would you implement a service-oriented architecture?   

Many of the elements of this answer exist above.  These regard a data model, handled by code and app data structures, and optimized separability as possible.  Ideally this also covered the separation and overlap of read and write paths / identifies at the queues, ‘file’ stores, caches, and any other dependent resource.  

With this, it’s easier to maintain resourceful endpoints that can be separated into services that are dedicated to handling specific parts of the application data.  GrapeAPI is one way to make this easy, while maintaining formats in which the data can be expressed.  Placing a graphQL server as middleware here can provide value — given that the client apps are sufficiently dynamic in the way they will query joined-subsets of the data mode.  

It’s often faster to cache API endpoint results, provided that the client app is not overly constrained on the amount of data received, and reduced, for the end UI.  But if user behaviors (the rest of their runtime env) make this the case, then some data-shaping proxy can cut down the transmit volume and complexity.  Such a proxy could be graphQL, and I’ve relied on Hasura when needing such. 

### What tools would you use to test the performance of the application to ensure it meets the objective?

The previous topic, of platform services, implicitly involves consideration of observability.  The health of individual VMs, from apps to DBs, and CDNs and other persist targets, are only part of the overall picture.  They represent a necessary foundation of dashboards that need to constant health and assurance.  

However with the scale of platform discussed here, other forms of monitoring will take equal weight.  Most significantly, these include lifecycle event collectors - which need to trend monitoring to ensure a signal occurs for service alerts. While the Product or RevOps teams will likely monitor these regularly for orders / billables a complex system of analytics can have things go offline for too long before noticing.  

External monitoring tools for endpoint response time, etc, should have data ingested to a log store - whether directly ingesting to grafana, scylla, etc, or via API ingest through Fivetran, Stitch, etc.  

Where client contracts for platform services may have different SLAs, we might implement more realistic canaries via live dummy clients. 
### How would you ensure that you’re not sacrificing security for scaling?   

Performance monitoring can smoothly transition into access and security monitoring.  Behavioral lifecycles start to include more exception rate, and type, monitoring especially for critical services.  Depending on the rate of scaling the MAU, an auth vendor can be instrumental to offloading the development of critical identity infrastructure monitoring.   Architectural patterns from top vendors can teach a team lots about the reasons to grow the same pattern of services in-house. From there, teams can decompose and take-over subsystems in a way that best accommodates the structure of the in-house platform. These learnings inform the way you evolve the SEIM.  Pen testing will advance from external surfaces to internal surfaces, which will help reveal leaks and other potential risks.  SOC and ISO programs can have a modest scope that limits the number of controls.  The scope of these can tailor to the clients anticipated for the scale the company exists at today.  Clients that require stepped-up commitments will occur, and giving them increased transparency and reporting will often abate concerns through until subsequent audit recertification.