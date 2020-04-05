# Anatomy of web stacks


* Asset packing / bundling
* Above the fold / critical path
* CSS splitting and namespacing
* Responsive

.

* Templates
* Rendering?
* Display components
* Charting / visualization
* Animations/transitions?

.

* i18n
* Semantic DOM
* SEO metadata / structure
* Accessibility

.

* Isomorphic code
* Transpiling
* Polyfill / shim
* Dependency injection
* Plugins/externalizations 
* Unit tests
* Debugger

.

* Bootstrapping / configuration
* Email
* HTTP server integration
* Middleware

.

* Auth
* Perms
* CORS

.

* Sessions
* Flash / messaging 

.

* State management
* State-machine
* State hooks / lifecycle actions

.

* SPA routes
* Routing
* Data model / access / ORM
* Data schema Versioning (Validation?)
* Validation (generic)
* Caching

.

* Streaming
* Event / message bus / workers?
* Event logging (app/user)
* Exceptions handling


# Design Patterns

The topic of design patterns is moreover the semantics of the language of systems.  While 'architecture' may take the form of the measurement, by the history of these measures the signifiers of 'design patterns' appear.  

Some of these:

* [SOLID](https://en.wikipedia.org/wiki/SOLID)
  * Single responsibility
  * Open–closed
  * Liskov substitution
  * Interface segregation
  * Dependency inversion
* Patterns
  * Controller
    * Creator
    * Indirection
    * Information expert
    * High cohesion
    * Low coupling
    * Polymorphism
    * Protected variations
    * Pure fabrication

Without a more elaborate dictionary of patterns, we can already consider how the total set of all patterns is the configurations of different resource types defined by the 'metal' of the OS.

### Graphical Rendering

While this file is not the ideal place for it, let's quickly capture an outline of the design pattern of a pipeline for rendering complex visualizations 

1. Raw Data 
1. Analysis 
1. Preprocess 
1. Filtering 
1. View 
1. Mapping 
1. Geometric (data structure) 
1. Draw (or, UI library)
1. Graphic
2. Interactivity

#### Raw Data
CPU/GPU hardware, data acquisition, profiling, cleaning, compression

#### Analysis
data cleaning, statistics, data modeling

#### Filter
basic algorithms, statistical algorithms, common layout algorithms

#### Geometric
trigonometric function, linear algebra, geometric algorithm

#### Draw
Canvas, SVG, WebGL, computational graphics, graph theory, engine design, shaders, 

#### Graphic
visual coding, visual analysis, graphical interaction, display hardware/target

#### Interactivity
design principles, aesthetic judgment, color, perception, cognition, cognitive load, interaction, psychology


## Mobile

When do you decide to build native mobile vs. mobile web, and can a multi-platform framework be used? 

Anything written here will get dated as frameworks evolved.  That said, native mobile is still better when the app needs

* active location services
* running in the background
* highly-interactive UI
* music functions
* heavy use of the native OS API
* complex communications with servers

Mixes of these that can trigger issues could include where chat messaging happens in the app, but then you also expect the user receive notifications when the app is in the background.


## Typesafety

It is important to remember that typesafety is only a 'special case' of design pattern.  You must decide when and how it is best applied in service of the real value to the team and to the business.

Typesafety affords:

* program correctness assurance.
* faster operation due to bytecode or assembly.
* additional IDE guidance.

What it does not afford:

* runtime safety or correctness.
* better application design.
* faster development time.
* simplified toolchain / environment.

Program correctness can have important value for the product and business.  Mindfully validate if this correctness is necessary, and is necessary within the context of the program itself.  Compare/consider if the program need to be internally correct, or if only the data needs to be correct when emitted or consumed.  API correctness and data-store correctness can be handled with other distributed systems design patterns.

## API Health

The metabolism of APIs and their environment.

* Uptime
* CPU usage
* Memory usage
* Request Per Minute (RPM)
* Latency (Average and Max)
* Errors Per Minute
* API usage growth
* Unique API consumers
* Top customers by API usage
* API retention / churn
* Onboarding Time
* API Calls per business transaction
* SDK and version adoption

One of the spanning concepts here is to profile API consumer, to understand who and how. 

Onboarding time probably represents one of the most complicated KPIs to solve, since it involves a rabbit-hole of _prospective API user demographic segments_.  [Some](https://www.moesif.com/blog/technical/api-metrics/API-Metrics-That-Every-Platform-Team-Should-be-Tracking/#) have called this 'time to hello world'.

* synchronization (semantic latency)
* network segmentation


# References
* https://frontendmasters.com/books/front-end-handbook/2018/practice/skills.html
* https://medium.com/discovery-engineering/component-level-isomorphic-webpack-code-splitting-b98922382cc1
* https://medium.com/@cramforce/designing-very-large-javascript-applications-6e013a3291a3
* https://github.com/jamiebuilds/react-loadable#how-do-i-handle-other-styles-css-or-sourcemaps-map-with-server-side-rendering
* https://frontendmasters.com/books/front-end-handbook/2018/practice/skills.html
* https://hacks.mozilla.org/2018/04/sneak-peek-at-webassembly-studio/
* https://medium.com/airbnb-engineering/whats-next-for-mobile-at-airbnb-5e71618576ab
* https://www.moesif.com/blog/technical/api-metrics/API-Metrics-That-Every-Platform-Team-Should-be-Tracking
