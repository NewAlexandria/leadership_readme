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


## Process Structures

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
