# Judgment Call

I had a tough decision to make recently. 

### the business issue

The context was our business growth, and the targets that were needed.  We were a Series A company and were targeting our B round. More than $60MM valuation at Series A, we needed to raise $200-250MM in our B round.  The milestones to get there were something of a moving target, but a common hunch was that we would do well if we secured a new major partner that was tied to diversifying to deliver another major line-of-business (LOB).  Getting there would require strong coordination from everyone, to plan, sell, and build, while executing on the growth of existing business.

### the situation

For this new LOB, a SaaS offering was one of the main concepts in development.  Several other ideas were tested, but were not getting as much traction as fast, regardless of how to execute. We determined that we could offer a new product that used our existing infrastructure and services, with the help of a new webapp that offered admin and portal features based on a range of users roles.

### intractable analysis

To get the SaaS offering right would require clear planning, specification, and execution speed.  While these are normal operational values, the tolerances for wobble were low because of the slow client-dependent cycles, and the need to ultimately deliver faster than the opportunity cost of their internal development.  Doing so would represent a major challenge in our startup environment.  Teams that would plan and design the offerings and product were recently hired, and did not have developed-relationships of working together.  OKRs showed our recent cadence was not working hard to maintain current operations.  A complex new project would introduce new forms of risk in addition to heightening existing risk.   The root of the matter needed to be solved in order to successfully deliver on any plan that would materialize a new LOB capable of solidifying our next venture round.

### A decision making process

A break-down of the specific patterns occurring aroused disagreement about the source and solution to each.  One of the core observations was a low team velocity.  That assessment came from several in leadership with experience delivering initiatives with similar feature-complexity.   The speed and depth of specification delivered from the product team would vary widely. IT was possible that the existing personnel were simply be asked too much, with too steep of a learning curve for what our startup could afford to educate / support.  Engineering delivery also had limits that were throttled by toolchain, code typesafety, library support, and boilerplate.  The size of our team limited the support available for toolchain and environment, and this was after paying a premium to hire upper-level engineers.  While choosing a typesafe language (scala) had strength, the toolchain, onboarding, and general availability of affordable candidate engineers were all factors in final delivery.  Scala lacks libraries for quickly building admin apps and similar portal webapp patterns, yet engineers on the team had taken an inflexible position on the importance of driving innovation in the scala community, by using it for all systems.  The absence of library support meant that we needed built more boilerplate, or dedicate more senior-engineer time to developing generalized libraries.  Even in this break-down, there are many ways to look at these complexities.

I knew that any solution would need as much input as possible, and the socialization of that knowledge.  The socialization would not-only ensure we had a rich perspective, but also help those that were defending any options we may not pick to feel aligned with a go-forward plan.  I realized this would take support from outside perspectives as well.  I considered how I would want perspective, in the same way.  It was also clear that different peoples' communications styles would require different meeting formats and hearing styles, and that due to normal time constraints, some of these discussions would need to to occur as a part of existing meetings.

I got feedback from people during meetings, and in 1:1 sessions.  I asked people in confidence, seeking 'tough choice' opinions of the situation, as well as in group settings where I supported each rationale and mediated dialogue.  I researched meetups and professional consultants in the community.  I discovered that many teams that epitomized 'scala vanguards' did not use it for the admin-style portal webapp that we were seeing as a route to Series B funding.  Instead they used non-typesafe languages for the flexibility of rapid changes and re-release, which was an option in a service-type that was more tolerant to program faults.  As well, long-standing non-typesafe language communities had build robust libraries and frameworks for delivering similar projects, and with similar rapid evolution of the delivery. 

I saw the option for delivering the target product using javascript, as the language was flexible and had a broad set of libraries, while also we could implement typescript at any time.  Though most scala-committed teams seemed to chose ruby for this application, it was clear that our engineering culture would not be comfortable with a non-typesafe language.  I further validated this by building a POC app concept in ruby and rails, and launching it, in a couple days.  Despite the speed and flexibility of delivery, the demo met with many cultural rejections because of typesafety, and would clearly not be a supported option.  Even with javascript, it was clear that I would need to give support for a small team to form based on those that were supportive in 1:1 or group contexts, to accomplish the target deliverable.   This route seemed possible, particularly when considering the limited influence that I could have there in the operations of other teams — and Series B depended on it. 

### work to disconfirm the assumptions

validation by meetups; internal solicit.   convey imperative / impact / value, and ask for improvements.  team level.  1:1. leads. managers.   Feedback: behavioral. process. tooling. left-field.

alt: let team BAU, hire-up, riskier arch., build/contract a lib.  [the alternatives you considered and evaluated, and

decision: dyn. small smart team.  cuts: product variance-ing,    [why you chose the alternative you did relative to others considered

deal arrival, comparison pricing Qa, speed, win.  [strong business judgment and good instincts

series B via prioritization.  privately, is a min $200MM




