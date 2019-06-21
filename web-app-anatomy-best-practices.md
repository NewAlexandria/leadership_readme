# Anatomy of web stacks


* Asset packing / bundling
* Above the fold / critical path
* CSS splitting and namespacing
* Responsive

.

* Templates
* Rendering?
* display components
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
* Flash message 

.

* State management
* State hooks / lifecycle actions

.

* SPA routes
* Routing
* Data model / access / ORM
* Data schema Versioning (Validation?)
* Validation
* Caching

.

* Streaming
* event / message bus / workers?
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

# References
* https://frontendmasters.com/books/front-end-handbook/2018/practice/skills.html
* https://medium.com/discovery-engineering/component-level-isomorphic-webpack-code-splitting-b98922382cc1
* https://medium.com/@cramforce/designing-very-large-javascript-applications-6e013a3291a3
* https://github.com/jamiebuilds/react-loadable#how-do-i-handle-other-styles-css-or-sourcemaps-map-with-server-side-rendering
* https://frontendmasters.com/books/front-end-handbook/2018/practice/skills.html
* https://hacks.mozilla.org/2018/04/sneak-peek-at-webassembly-studio/
* https://medium.com/airbnb-engineering/whats-next-for-mobile-at-airbnb-5e71618576ab
