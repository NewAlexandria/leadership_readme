# NHO steps - Practice Group

* guilds
* guidelines
* style guides
* FAQs


### Engineering tech debt types

These are a [proposed list](https://technology.riotgames.com/news/taxonomy-tech-debt) of tech debt types.

* Local Debt
* MacGyver Debt
* Foundational Debt
* Data Debt

[Some related thoughts from SO, here](https://stackoverflow.blog/2019/09/05/they-didnt-teach-us-this-a-crash-course-for-your-first-job-in-software/?cb=1)

### Analyzing a codebase

* Is there a dependency analyzer in-use already? If not:
  * What languages and libraries/frameworks are used?
  * What are some commonly used external dependencies?
* What is the file structure?
* You’ve picked a file or a module – what does this file or module do and how does it do it?
* Identify coding style patterns.
* What’s your overall impression of the code quality?
  * Are there localized differences?  Several?
* Fix bugs
* Write tests