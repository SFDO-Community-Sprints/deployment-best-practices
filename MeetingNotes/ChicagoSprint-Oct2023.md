---
title: Chicago Sprint October 30-31, 2023 
parent: Meeting Notes of the Working Group
has_children: false
---

# Project Team & Accomplishments
Diverse, rich, dynamic consultation about common practices, challenges, and opportunities for deploying solutions on the Salesforce platform. Built a foundation for a bridge to future practices.  Started a dialogue about what it looks like for our orgs and communities to move forward - beginning with what we know, and envisioning what might be.  We realize that there are so many personas and circumstances involved, and spent time identifying and defining opportunities, challenges, and circumstances for each, so we can help define what would be helpful for the community. 

# Contributors
Judi Sohn, Jason Lantz, Michael Kolodner, Heath Parks, Jessica Rosenberg, Leigh Petersen, Daniel Gorton, Sita Kunz Samuel Kennet Rajkumar, Greg Brice, Ethan Norris, Cassie Supilowski, Tim Calalang, Akash Mishra, Taylor Moyer, Mary Pustejovsky, Kim Schaefges, David Reed, Arthur Price, David Cheng, Katy Porray

# Future Contributions / Next Steps
1. Continue conversations in Slack to translate concepts to experience
2. 'Version Control for Admins' - community group/DF presentations
3. Recommendations matrix for different stages/paths
4. Gather other perspectives/personas.  Survey? 
5. Continue to add to Resources page.  New Trailmix?

## Notes from Day 1
### Ways to frame the conversation
1. Lifecycle of a project
* Implementation phase
* Ongoing maintenance/enhancement
* Change management
* Continuous improvement, adaptability, responding to change
* Requirements > Build > Deployment
* What to build, where to build it, how to build it, how to move it
* What, how to build - out of scope for today
* Assume ‘Definition of Ready’ is met - focus on how do we deliver it
2. Lifecycle of a team
* Devs, admins, size
* Solo admins/small teams
* In-house teams - what applies, what is relevant? 
* SI partners - how to help clients get set up with best practices?
* New skillsets, new terminology, new concepts
* Do teams have a dedicated ‘deployment specialist’ or is this another hat worn by an admin or another team member? 
3. Different organizations
* Every org, every team is different
* Some orgs do not have a sandbox :( 
4. Commonality: Everyone has a production org.  Changes flow into this org.  How can this change stream be managed?  What practices can we align around? Those practices may differ/change. 
* What are guardrails, when/how do we move outside those guardrails (safely)?  How to know what to apply, when? 
>>
### [Salesforce Well-Architected](https://architect.salesforce.com/well-architected/overview)
* Trusted (Secure, Compliant, Reliable)
* Easy (Intentional, Automated, Engaging)
* Adaptable (Resilient, Composable, Application Lifecycle Management (ALM))
* Now what? How do we make recommendations more accessible to this ecosystem?
>>
### Ideas
1. Create straightforward, ‘start-here’ guide for someone starting on this journey
* Build a matrix to guide decisions?  Similar to https://architect.salesforce.com/decision-guides/build-forms
2. Identify steps/best practices for:
* Pre-deployment
* Deployment
* Post-deployment
3. Trailhead ‘Haunted House’ - instead of step-by-step guide, something that went wrong, how to find & fix it
>>
### Challenges
1. Sandboxes
* Refreshes
* Documentation - types of orgs, uses, etc
* Sandboxes can be old, out of sync, have who-knows-what in it… 
* Effort to configure sandboxes, prep data, setup integrations, etc. may make refreshing sandboxes difficult/lengthy process
* Not all orgs have sandboxes to spare
2. Dev/Build
* Overwriting changes 
* Losing changes made by others
* Untangling changes
* Where does latest development reside?  
* What is source of truth?
3. Testing
* ‘Hi-fidelity with production’ - is there an environment that is enough like production, that we can test confidently there?
* Shifting left - 
* How much can you test to the left of sandboxes? 
* LDV in sandboxes
4. Release management
* Salesforce 3x/year
* Apps/packages/products 
* Internal releases
* Configuration as data
* Undeployable changes
* Deployment issues/errors
* Release vs deployment - every release is a deployment, but not every deployment is a release
* USERS! (in different environments)
* What can be done safely in Prod?  When/how to sync into sandboxes (i.e. reports)
5. Governance/advisory
6. Takes more time to follow best practices
* “The right tool” may not solve the problem - 
* Involves people, processes, other transformation
7. Scratch orgs
* Opportunities/benefits of scratch orgs:
* Ephemeral orgs (can spin up, will go away - not persistent)
* Every org can use 40+ for free
* Cheaper more plentiful than sandboxes
* Useful for testing, preparing to deliver to multiple customers, etc. 
* Can isolate work better - less risk of overwriting or losing work
* Enables simultaneous work streams that are independent of each other
* Each change can be captured in version control
* Version control enables compliance, governance, automated checks, automated testing, history, etc
* Setup Audit Trail does not capture everything
* Challenges with scratch orgs
* High barrier to entry - difficult to set up.  Level of enablement, tooling, preparation is high
* Must understand dependencies of what should be in environment
* Not a copy of production - need to configure/specify/set up packages, etc. 
* Requires data seeding 
* Takes work to automate setup processes, etc
* Time to run automation
* Operational challenges
* Work collaboratively
* Keeping orgs in sync while work is inflight
* Building components that depend on data
* Can mitigate this with scratch org pooling - pre-configuring orgs that are ready to use

### Terminology
* Solutions vs implementations
* Deployments
* “DevOps” - Means different things, confusing term.  How do we scale up, scale down?  Meet needs of teams of different sizes, stages
* Source-driven development - Is it viable for all?  What are gaps to adopt?  How to make it more approachable? 
* Org-driven development - Is being done, widely, today
* “Source of truth”
* “Easy” - relative to different sectors/teams/persona.  What is ‘easy for developers’ may not be what is ‘easy for admins’ or what is ‘easy for a solo admin at a small org’
* ‘Shifting left’
* Composability - Learning how to build smaller, modular solutions that may be combined, and are reusable across organizations.  Especially useful for SIs, ISVs

### Starting assumptions for this week:
* Green-field (brand-new) implementation project
* Built on top of PMM 
* Planning to use source-driven development
* Focus on declarative, admin-friendly solutions

_I’m starting a new Salesforce implementation project.  I have identified the first application feature set I want to build and know how I want to build it in an org. 
I want to build this project to be as much in-line with recommendations of Salesforce Well-Architected’s recommendations around [Adaptable](https://architect.salesforce.com/well-architected/adaptable/overview) → [Application Lifecycle Management](https://architect.salesforce.com/well-architected/adaptable/resilient#Application_Lifecycle_Management) and [Packageability](https://architect.salesforce.com/well-architected/adaptable/composable#Packageability) while ensuring that implementing , maintaining, and operating the process is affordable and accessible. 
What exists today and what needs to be created to make this possible?_

Starting with a common nonprofit use case: 
* Custom object with 3 fields
* When a Contact is created, a record in a custom object is automatically created, a task is created and assigned, an email is sent... Flow?
* Only certain users should be allowed to do this action
* We should be able to report on… (Custom report type?)
* Some things tried/built in development may not be ultimately deployed

Who are we doing this for?
Identify Jobs To Be Done, Key Challenges / Limitations for:
1. Solo admin
2. Small team - admins & super users
3. SI/Consultant (delivering changes to clients)

What are ways that we might deliver this? What are the characteristics of each path?
Identify Reasons, Risks, steps for:
1. Making changes directly in Production
2. Sandbox(es) with change sets
3. Sandbox(es) with version control (such as DevOps Center, 3rd party tools)
4. Scratch orgs



### DEMO TIME
Jason Lanz, 2GP unlocked package deployment


## Notes from Day 2
_“I reserve the right to get smarter with new information!” - Kevin Bromer_

Reviewed perspectives outlined from yesterday.  Decided to walk-through each processes - no judgment!! 

### Perspective 1 - Solo admin (Heath)
* Requirements gathering - ask questions!!  Understand metrics, and value that feature will add
* Build - adds meaning in screen flows, like training docs, to guide users through the ‘why’ we are doing this.  Adds meaningful error handling in Flows.  Consider system access vs more restricted access in Flows.  Often using custom perm sets. 
* Documentation - used to use Teams, now OneNote.  Lists all objects, components, permissions, separate tabs for projects.  Documents the what and the why, links to Flows, etc.  When ready to deploy, creates checklist for what to add to change set, etc. Ongoing process. 
* Sandbox management - refreshes partial sandbox.  Setup data - mostly manually, or modifying existing data that came over in refresh. 
* RESOURCE: Connected app for user management in sandboxes: https://admin.salesforce.com/blog/2022/how-i-solved-it-enable-users-to-easily-log-into-sandboxes-directly-from-production
* IDEA: runbook/checklist for sandbox setup
* Testing
* Demo in sandbox - gets feedback 
* Reports - starts creating meaningful data to show reports.  Naming conventions for reports/folders.  Admin vs end user report types - streamlines fields on report types for users.  Brand-new reports - creates in sandbox with fake data.  Tweaks to existing reports might be in prod. 
* Gathers more feedback
* Change management - how to communicate to staff, how to approach training, who needs to test.  Hard to include people in testing.  Ask for more feedback.  Decides when to release to production
* Deployment - plans for after-hours deployment (not Friday!).  Change set based on documented components/steps along the way.  
Post-deployment - validation test in Prod. Deletes test data. 

### Perspective 2 -  Multiple admins / small team  (Cassie, Jake, Greg)
* Sharing Runbook doc - team has been working on environment strategy since 2019
* Team:
5 person admin team with 5-9 years of experience.  Up until 5 years ago wasn’t organized with deployments.  Hired team member specific for devops.  No sprints - work is tracked in Cases and Jira tickets.  Team members self-assign.  Pair programming.  Standups 2x/week.  No governance board to prioritize requests, no product owners yet - most work is project-based
* Takes notes on how long it takes for each step
* Sandboxes - Has both full and partial sandbox.  Seeds partial sandbox blank.  Uses Own Backup to anonymize data.  Justified it because of documenting how many hours it saves.  Tries to refresh both sandboxes on same cadence once a quarter - takes about a day (mostly with anonymization).  Partial and Full are normally preview sandboxes - may have to re-create change set to go to Prod because of API.  RESOURCE: SF Toolkit (to compare orgs) https://www.mstsolutions.com/technical/salesforce-toolkit/
* Future state - moving away from change sets.  Discussing what goes into personal vs project dev orgs, partial org, etc.  Diagrams of current state and future state pipeline (Dev > Partial > Full > Prod).  Everything goes (or should go) through partial and full copy sandbox. 
 Challenge: deleting/cleaning up components in all environments.  Challenge: many requests are upgrading something that exists, rather than net-new projects.  
* General team guidelines - No new work in Full Copy - bugs should be fixed in partial/dev and re-deployed. All work passes through Partial and Full (Pardot is exception). Keep partial data realistic, except when doing negative testing.  No new data creation in Full except as part of testing create functions.  Active work should not sit in partial/full for more than a few days. 
* Change sets - named for Jira ticket. Uses Audit trail to check changes.  RESOURCE: ORGanizer for Salesforce (Chrome extension) - ‘Add to Change Set and add again’ button.  Also viewing editing any fields on a record https://chrome.google.com/webstore/detail/organizer-for-salesforce/lojdmgdchjcfnmkmodggbaafecagllnh.  Can often reuse change set between environments - but not if on different release versions. 
 Deploy as needed
* Exempted from deployment pipeline - reports, permission assignments, user assignments (gone back and forth - assume will be caught by refresh).  Challenge: adding a field (add to report types, or leave off?  What if field needs to be walked back?)
* Feedback from team about DevOps center - What about manual changes? Profiles. RESOURCE: BlueCanvas.io. Hard to test DevOps center in sandboxes before enabling in Prod.  Spinning up a scratch org may be a barrier. 
* Testing - Try to document testing scenarios in Jira tickets. Rarely live testing in Prod.  Usually view only validation. Challenge: test users in different environments (permissions/access necessary for testing, but then may show up on reports, etc.  Esp for integrations/3rd party app testing.)
* Hotfixes - May change in prod and backfill to other environments, or backwards change set between pipeline environments. Post-production bugs are logged in Jira. 
* Business processes & translating to Salesforce
* Governance, prioritization, will we need this in 3 years?
* Challenge - how to learn best practices, how to use change sets in a practical way, etc.  Sometimes re-build things in Prod after building in Sandbox.  
* Challenge - coming into existing org, finding documentation, history, why things were built.  Also, finding documentation of things that were built by consultancies, implementation partners, etc. 

### Perspective 3 - Consulting partner / SI (Judi, Mary, Arthur)

* Starts from user story (as a... I want to… so I can…) with acceptance criteria.  Approval process, time estimation (revisit estimations in retros).  
* Default recommendations to standard functionality first - burden to show why this won’t work, before exploring customizations. 
* Net-new orgs have been done directly in production before… Challenge is no history of changes.  Challenge has been cleaning up elements that weren’t part of final solution. Moving toward using sandboxes as default process. 
* No 3rd party tooling for deployments
* SI also has a 2GP managed package offering - uses CCI.  Team is savvy with CCI/GitHub
* Individuals have persistent orgs as demo orgs - starting to use scratch orgs from repo, spin up and use as needed
* Challenge: many nonprofits do not have full sandbox
* Challenge: opportunities/resources/information may be shared informally via community, some orgs/users do not know how to access (i.e. MVP Slack Channel, Twitter, etc.)
* Challenge: sandbox seeding
* Benefit of source-tracking is to see history of changes, in context, tied to requirements.  Can separate from user-facing documentation (help text, descriptions, etc)
* Benefit of version control - in addition to history of changes, can also implement controls and governance around future changes. 
* Development industry standard (outside Salesforce) is infrastructure as code - everything needed to run, deploy, provision applications is stored in code (instead of manual processes).  Hard to do with Salesforce.  
* Nonprofit SI perspective - ‘we are guests in your home’.  
* Another SI perspective (Arthur) - start with partnership, what is your process, will embed in local team. If smaller teams, will offer processes as model, will train on final steps of deployment, etc. 
* Uses scratch orgs, especially when devs are involved
* Agile practices can help give structure to deployment processes (sprints, discovery/acceptance, testing, deployment cadence)
* May bill by sprint vs by hour.  Discussion - how does business model / billing model incentivize (or disincentivize) finding efficiencies in workflows / improving workflow processes?
* Challenge - organizations hiring dedicated Admins who can take over / maintain processes after SI engagement ends
* Challenge - executive leadership in governance, change management, development lifecycle processes, etc.  ‘Managing up’ - how to convince leadership to invest in DevOps.  Helping people understand the hidden costs of NOT implementing these things. 
* IDEA: Hidden Cost calculator/template
* Challenge: cannot accurately measure KPI, ROI if everyone is regularly inflating estimates to account for infrastructure/overhead

### Perspective 4 - Developer Tooling / Product Delivery Model (Jason)
* Org development model, package development model (see [Determine Which Application Lifecycle Management Model Is Right For You](https://trailhead.salesforce.com/content/learn/trails/determine-which-application-lifecycle-management-model-is-right-for-you) ).  Challenge with org development = dealing with full complexity of org, all the time.  Challenge with Package development = developing on an island; separated from environments that will use/run packages
* New idea: dynamic delivery.  Instead of one trial version, what if we could preconfigure based on target org?  Requires composable solutions, tooling to combine and deliver.  
* (Jason sharing slides, demos Metecho)