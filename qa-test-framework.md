# QA, from manual to automation

## Roadmap

|                | phase 1                                                       | phase 2                                                        | phase 3                                                                                   | phase 4                                                       |
|----------------|---------------------------------------------------------------|----------------------------------------------------------------|-------------------------------------------------------------------------------------------|---------------------------------------------------------------|
| main goal      | manual / exploratory testing. | manual / exploratory testing. | manual / exploratory testing. | manual / exploratory testing.  | manual / exploratory testing. | manual / exploratory testing.                             | manual / exploratory testing. | manual / exploratory testing. |
| secondary goal | Master plan development.                                      | Write BDD feature files,structure and develop common language. | Prioritize testing labels for Continuous Delivery.Refine BDD language; improve coherence. | Automation test creation.                                     |
| schedule dates |                                                               |                                                                |                                                                                           |                                                               |

Our BDD outline, today, is very rough. We have one spreadsheet with many many test cases (and many are effectively duplicate). Then we have some gherkin-style tests written, with ruby-cucumber step definitions behind them. When writing new automation tests, we want to follow the ruby step definitions we have today, so that our in-house engineers have an easier time updating them.

Our aim with the spreadsheet and BDD files we have today:

1. consolidate & de-duplicate the tests
1. organize into groups, by section and component. These lists (should) reflect the same components
	* Live style-guide website
	* current QA sheet (ad-hoc list)
	* Wiki list
	* QA / Validation Portal
1. keep up with testing (exploratory/manual/automated) of sections and components impacted by code changes for ongoing releases
1. write new automation tests / checks by following the consolidate BDD testing outline that we formulate.


### Phase 1

1. Keep up with feature/section testing, for our releases, and then
2. Refining the existing testing outline, e.g. removing old features
adding new sections and record of major features reorganizing it for clarity
developing mobile-specific addenda for each component / section

### Phase 2

1. We will continue the manual evaluation of sections, particularly
those pages and features related to campaigns, and
the release of ongoing improvements.
2. Write and update the tests as gherkin feature files (BDD) develop @labels for appropriate test categories.
develop a common language across feature files.

### Phase 3

1. We will continue the manual evaluation of sections, particularly related to the release of ongoing improvements
2. label tests by priority, toward having a plan for Continuous Deployment
smoke tests campaign points major content / UX ( other levels TBD )

### Phase 4

1. testing features/sections for the releases
a. manually as required / where automation gaps exist
b. appraise the efficacy of automation check coverage;
Refine.
2. writing more automation tests & checks.
a. Our existing feature files

