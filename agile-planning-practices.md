# Chartering 

I like to aim for a lightweight workflow for master planning documents (Charters / Charters / etc) as they move from an idea until they're ready to be implemented. Usually this process is managed in an ad hoc fashion, and as a result often lacks visibility and consistency.

### Issues:

*     incomplete view of medium term priorities
*     some potential Charters lose momentum
*     in progress Charters are reviewed inconsistently

### Goal:

*     complete visibility into all planning and design work
*     consistent process and cadence moving from gathering requirements to completed Charter

### Non Goal:

*     define the actual process of writing a Charter
*     define the contents of a Charter

### Background

The idea of reviewing and leaving comments on a completed Charter is well-established in the tech organization, and the subsequent epic process is mostly standardized. However the process of actually developing a Charter has largely been left as exercise for the reader. This worked fine when the vast majority of the work on Charters was done by 2-3 people, but as the Engineering and Product teams grow, we need some process to better coordinate everyone involved.

As well, the Charter process in Engineering generally occurs after some Business planning.  Afterward, a release or launch planification helps the company own the success.  These major stages needed a place in the big picture.  Here we'll proposes to outline and detail all of that, in a way that can translate to input from stakeholders org-wide.

![](assets/planning-highway.jpg)


## Oversight Structures

### Planning Charter Dashboard

The ideal is to minimize locations-for-things and time, by having one project that holds all the planning.

The Boards:

*     Biz Charters 🧭 
*     Tech Charters 🧭 
*     Product Verticals 🧭
*     Launch Charters 🧭 


> Each board has a "Fuego 🔥" swimlane, which shows any epic with that Priority.  Use this to draw attention to that needs focus until resolved.


For the sake of planning (or time sensitive Charters), tasks in any state (or with no state) can have a start date and / or an end date - this can be used to prioritize moving a task along in the workflow. Tasks that are In Progress should have a start and end date that reflect reality.

Any dependencies between Charters should be explicitly called out.

All incomplete Charter tasks should be presented in a unified board view (quickfilter)

### Workflows

A Charter task card needs to be moved through workflow states by an owner.  A task can have no state, in which case it's just a name that's acting as a placeholder for future requirements. If a tasks has a state, it must have an assignee.   It's possible that we should abandon assignee-less Charter cards, and instead put them in an 'IDEA' project of elevator-pitch style concepts.

### Requirements 📒

Any Charter has requirements unique to each type (or stage) of Charter. These requirements represent major facets for understanding the work proposed.  Unless there is a clear exception, they must appear in each Charter before it can move to the next stage, and the next set of stakeholders can become involved. 

Sometimes Charter requirements will be brief, or expansive, based on the nature of the work in proposal and development.  This natural variation gives a clue to the relative size and complexity of a new Charter.  As well, the intuitive to create new sections of requirements, or completely abandon some, indicates when an idea maybe sufficiently new (and maybe risky) to the business.  This can also indicate shortcuts in the Charter planning process that can manifest as delivery or live support risks.  Every stakeholder benefit the process with mindfulness to these variations, and by discussing them.



## 🧭 Biz Charters
### Workflow

Let's choose stages that make sense for incrementally identifying and operationalizing value more-clearly.

Whatever we decide, let's choose stages for a process, where even if there is a mandate to Go, we can still ask for info to fill-in the ‘skipped’ stages.   i.e. they might get skipped because of ‘good gut instinct’, not because the information isn’t available if more time is spent. 
### 📒 Requirements

*     Motivations
*     Product Value
*     Financial Model / sim
*     Integration Scope
*     Assumptions
*     Stakeholders
*     Proposal Details
*     Timeframe
*     Market
*     Partnerships
*     Associated CharterS
*     Related drive and docs

### Motivations

Product Value
Financial Model / sim
Integration Scope
Assumptions
Stakeholders
Proposal Details
Timeframe
Market
Partnerships
Associated CharterS
Related drive and docs


## 🧭 Product Charter

We have seen an emerging need for a Product Charter in the wiki.  This planning doc collects all of the product release pieces. 



## 🧭 Tech Charters
### Workflow

Track potential and complete Charters using tasks that implement a workflow that moves through the following states:

1.     **Gathering Requirements** - the task is assigned to a product manager (or an engineer, if the change is eng only) who is actively gathering requirements. Once the requirements have been captured in a partial Charter and linked to the task, it changes state to Triaging Charter.
1.     **Triaging Charter** - the task is unassigned until we find a lead engineer, and all stakeholders agree on the requirements as stated, at which point it changes state to Writing Charter.
1.     **Writing Charter** - the task is assigned to the lead engineer, although they may be collaborating with other stakeholders (e.g. product) on producing the full Charter. Either way, everyone is actively working on the Charter, which will be continually reviewed in this state. Upon completion, the Charter is circulated across the org, and a final review is scheduled. Once the appropriate stakeholders agree on the proposed work, the task changes state to Build Backlog.
  *         Rough skeleton of requirements
  *        Requirements iterations with Product
  *        Storymap
  *        Writing details
1.     **Build Backlog** - With a storymap in place, an estimation can get approved by biz-prod-eng stakeholders, and prioritized by ROI that mixes the needs of all stakeholders.  Once approved, the Charter is prepared for implementations. The tasks remains assigned to the lead engineer while the associated epic is staffed and scheduled. A full backlog will get built by an agile team that breaks-down the storymap.  Provided no new discovery was made that changes the estimates, boards are built in Jira.  The epic kicks off, and the task changes state to In Progress.
1.     **In Progress** - when the corresponding epic is complete, the task is marked complete.  The team will do a retrospective to learn from the Charter and share that knowledge with other teams.

### 📒 Requirements

1.     Biz Value
1.     User stories
1.     KPIs / data / reports
1.     Main Reqs (from Biz Charter, or internal)
1.     Related research pages
1.     Linked docs (widget / macro to google drive)
1.     Alerts
1.     Runbooks
1.     Mocks and Interfaces
  1.         API
  1.         Embed
  1.         Portal
  1.         Admin
  1.         DW schema

#### Biz Value

This is a 1-3 sentence motto that focuses everyone on the feature's worth to clients and users. Could be a precuros to external-facing slogans, etc, about the feature.

#### User stories

Several on-liner sentences that speak about the things that users will do while interacting with the feature.

#### KPIs / data / reports
#### Main Reqs (from Biz Charter, or internal)
#### Related research pages
#### Linked docs (widget / macro to google drive)
#### Alerts
#### Runbooks
#### Mocks and Interfaces




## 🧭 Launch Charters
### Workflow

This is still TBD, as many variations occur in Launching. Sometimes, no meaningful launch plan will appear, because stakeholder review, and natural discussion, have solved the needs for launch.  Other times, elaborate launch planification documents are needed to ensure the success of Even and its partners. 
### 📒 Requirements

*     Partner Services / AM docs
*     Partner actions matrix
*     Press materials
*     How-tos
*     Onboarding material and updates


#### Partner Services / AM docs

This is any workflow-related information that the PS teams maintain, for handling partner onboarding, basic debugging, and similar.

#### Partner actions matrix

This is a spreadsheet document that timelines which partners get which features. turned on.

#### Press materials

Any information posted to Even's website, as well as communications with news organizations, search engines, etc.

#### How-tos

Instructional material involved in the ongoing use and ownership of the new feature(s).  These may be either more or less technical in nature.

#### Onboarding material and updates

Updates to Even School and other materials used to orient new employees.



Expanded view of stages of Planning, Delivery, and Operationalization

All of the above stands as a simplified version of more-detailed phases of work that go on within an RFC stage.  These phases can overlap.  The current consideration of these looks like this:

*     A dash '-' is minimal involvement, such as gut-checks about scope changes, etc.
*     Release and Rollout is sometime called Launch
*     Analysis can include monitoring existing data, or developing new reports or monitors.  This should be prepared in advance of the release.
*     Live Ops can involve new. response. and messaging templates, whole-team quality, revenue operations ('revops'), and FAQs.    These often get recorded into 'runbooks' that give guidance when situations occur.




![](assets/planning-highway.jpg)


# Step-by-step guides


💡_Thing not to do_

* skip steps out of inconvenience
* create new schemes without a prefix namespace
* leave default names like "Copy of ....."
* edit the statuses (they are global)
* edit the priorities (they are global)
* edit any Scheme or Issue Type that is in use by another project, without confirming with them.


## PLAN board - New epic & Charter creation

This happens after approval to begin exploratory work, such as from the exec team. For Tech Charters, this happens once a Biz Charter has been completely prepped for triaging.  Eng. stakeholders have likely been involved or exposed during the Biz Charter stage(s).

1.     create plan card
  1.         add Components for product type, or service area
  1.         add labels for targeted delivery quarter
  1.         add labels for Charter type (biz, tech, launch)
  1.         assign 3 people (unless unknown):
     *             reporter: the Business person, probably from the biz Charter.
     *             approver: the Product person guiding specs, QA, etc.
     *             assignee: the engineer writing the tech Charter / leading it.
1.     create Charter in wiki
  1.         use your team's space. We recommend placing it under an 'All Charters' page.
  1.         add labels to wiki page
  1.         paste URL for PLAN card into wiki, creating a link
1.     share the wiki link to draw discussion to there
  1.         use this instead of slack / email when possible, to avoid needing to trasncribe
  1.         select text on a wiki page, and comment inline
1.     If there is a slack channel for this project, link the wiki page's slack notification to that channel.
  1.         Consider setting the URL as the channel topic, or pinning, for convenience
1.     If any cards are created on an epic, they have their project field set to the team that will work on them.
  1.         multiple teams can collaborate on a single epic, this way.

### How to Read an Plan card (Charter)

### Charter Card Collaborators


## Jira board setup

This happens during the Backlog Build stage of the Charter

🚨 Do not use the normal 'create new board' GUI that Jira provides. Clone & rename a board, as below

1.     Copy from existing team board Query / filter (option under row '…' button)
  1.         Edit query (see example; right)
1.     Copy from an existing Board (option under '…' button)
1.     Change color-coding of cards to be based one something helpful
  1.         located in the board's settings
1.     Add URL for new board to the related epic (PLAN card)
  1.         add the URL to the slack channel topic, too, maybe (smile) 
1.     optional
  1.         Add components for each type.
  1.         Bulk move types to components
  1.         Bulk move all cards to epics
1.     Add the new PLAN to the exclusion list of the project that hosts the board.  This is done in the filter for the project team backlog.

## Jira board removal when done

1.     delete board
1.     Delete board query
1.     DO NOT DELETE epics or cards
1.     Move Charter wiki page to be a child of Archived page
  1.         add a label for archived
  1.         this is all located in the team's Charter section, e.g. Eng. All Charters
1.     Update the filter for the project team backlog; remove the PLAN from the exclusion.

## Example backlog board query

This example covers the range of board configs we use today:

1.     includes and epic from the PLAN board in the backlog of work
1.     targets the Project,
1.     excludes epics that have their own board for this team,
1.     excludes components that have their own board for this team
1.     excludes things that are done (does not rely on `release` / `fixVersion`)
1.     orders the cards by force-rank (manual dragging)

```
KEY in (PLAN-47) or (
  project = PLAT 
  AND ("Epic Link" not in (PLAN-1) or "Epic Link" is EMPTY) 
  AND component not in (Emails) 
  AND ( 
    status not in (done, Closed, Completed) 
    OR (status in (done, Closed, Completed) 
    AND updated >= 1d)
  )
) ORDER BY Rank ASC
```
