# Planning Strategy Doc for Team Transition (IN-PROGRESS / NOT DEFINITIVELY DEFINED)

## General Notes (TM Messaging Generally):
### CORE REASON WHAT WE DO: SOLVING PROBLEMS 
### Proposed Vision: To provide quality conceptual solutions for our enterprise challenges/problems (TBD)
### Proposed Mission: Devise strategies to solve XXX (TBD)
### Proposed Identity: Our team identity is XXX (TBD / one of experimentation, learning, and solving systemic/achitectual challenges)
- Note: "Less focus" towards "hands-on implementation" -- esp. no manual testing -- we DO provide: guidance, knowledge, training, documentation on concepts/best-practices/proof-of-concepts
- Industry best practices & standards 
- Explore & Pivot & Implement FASTER
- Research & Analysis > Recommendations and Best Practices
- Knowing what the "Enterprise is Doing" Concurrently / Focused on (& How we can align / understand / help)
  - Ex: Testing/Validating Kafka
  - Ex: Various Testing Types: Unit/Mutation Testing, Integration Testing, Mobile Testing (non-RMO), etc.
    - Standards/Best-Practices 
  - Ex: ServiceNow: (Esp. TestCase Management)
  - Ex: OurHouse (Provar)
  - OTHER Quality Tooling: (common-ize/standardize/support/licensing/capabilities [overlaps?])
  - Measuring Quality Impact (measurable KPIs)
- Building-In Quality into the start/maintenance of application/solution/system developement
- Architectural/System Design Patterns (Esp. Quality) {per "Tech Stacks"}
- Automation Coverage (All Testing Types / esp. APIs)
- 

## Overview Summary:
- This is an exciting new change!
- This is to better align 'like-roles' in better delivering value, more efficiently
  - There are a lot of benefits to this change : like roles grouped/focus, steel sharpens steel, better collaboration, less silos, more clarity in communication and work allocation
- EQAs focus on solving deep-systemic problems (1-2 focus areas at a time, lots of collaboration, and rotating pairings, building guidance and processes to support increasing quality across the entire enterprise (Streams > Trains > Teams > Team members/Apps)
  - Build visibility around challenges -- with a metric/kpi to show progress & milestones [1-2 core focused quality drivers (Stories/Challenges), per iteration]
  - Solutions focused
- Dragon team focuses on TDG, QHub, and creating/supporting other tooling solutions (engineering focused)
- There are a lot of unknowns still, but once we storm/form as consolidated teams, we will figure it all out together, collaboratively
  - Work intake / management (Service Now soon)
  - New ceremonies
  - Re-Focus on mission/vision (collaboratively) >> Roadmapping & Timeline & Assigned Conns & Reporting Progress/Blockers (keep-it-simple/understandable/visibility & clarity/default-to-open!)
  - Lessen dependencies on external clients/teams > Blockers abound ** (Note: addressed potentially by our work intake processes)
  - Find ways to solicit/integrate client's into solutioning (as value-drivers: client feedback, success metrics/KPIs, assigned conns/SMEs, roadmaps, etc.)


## MEASURING PROGRESS/SUCCESS (DELIVERY FOCUSED):
- Problem Solving and Solutioning 
  - KPI example-> # quality Problems/Issues solved Standards, Best Practices & Architecture alignments KPI -> # of imp  implanted standards
- Finding  Quality Gaps & Opportunities
  - KPI – example  # of quality Gaps/Opportunities identified
- Tooling Architecture
  - KPI # of blueprints/quality systems designed
- Quality Infrastructure
  - KPI -> ?
- Strategy (Projects)
  - KPI -> ?

## ROLES & RESPONSIBILITIES
- Make our presence FELT and ensure the "right" expectations/perception
- EQA
- BA
- TL
  - Team morale / safety
  - Team member career progression
  - Vision/Mission Guidance
  - Prioritzation
- etc.


## What We Do / What We Don't Do (Our Capabilities/Solutions)
- TBD
-  ... 
- Provide guidance/documentation/best-practices - Enabling dev-teams to do the work easier & faster
  - Quality Practices to happen on the dev-teams:
    - Conduct an Enterprise-Wide Analysis on challenges/opportunities, languages to support, existing tooling, etc.
      - Cypress, SorryCypress, CodeceptJS, etc.
    - We provide/set standards/examples & Docs/Guidance (Guidebook, TechToolbox, "Standards" & Tracking Tooling (QHub, BIG/AHS, etc.)
      - Blueprints & Guidance >> Production Agreement
    - Visilbility into which teams are following practices
      - Load & Performance > Expand Automation (Enterprise) **
    - Healthy practices / implemented quality needs >> Score Card
      - BIG Score Card >> Feed/Get the Data (to/from DataWarehouse)
    - Gatekeeper / Production Agreements
    - Compliance & Tracking (Metrics!!)
    - Building FWs for various testing types: Integration (CodeceptJS, TBD), Performance (k6), Load (Loadrunner/K6), etc.
    - NEED SR. LEADERSHIP BUY-IN / SUPPORT / PRIORITIZATION!!
    - DECIDED: Integration Testing will be our Q1 2023 Area of Focus!!! 
      - Analysis, Metrics, Concept, Docs, Tooling & Guidance, etc. -- We'll need a Strategy for solving for Increasing Int Testing across the enterprise


## Work Intake & Work Management Processes
- BA(s) & Aspire TMs, Leadership (& Everyone/Anyone) identify and populate the list of items/problems/challenges to be worked on (our: Prioritized Backlog) (> GHE issues?)
  - Note: ProductBoard is going away > Replacement > GHE / ServiceNow : TBD
    - "Large work ideas" are broken down into Features/Stories -> Discussed, Prioritized, Estimated, and Tasked
  - Planning & Refinement Agile ceremonies
    - Note: "Implement an "Express Lane" - for fast tracking high priority items - to the "top of the stack/backlog"
  - We need to be better at "Aligning & Vetting" ideas/priorities
    - Client feedback/priority
    - All CQ RT Planning/Prioritization ("CQ Meta Scrum" meetings") >> Once per iteration typically (1x weekly to start > "We'll Figure It Out, and tweak cadence as necessary) --> (We look at/vette out each other teams' planned Iteration work)
- PO(s) define and prioritize the challenges to be solved for (Collaboratively : Joint-planning/prioritization of IDEAS > Work sessions)
  - Business/Enterprise Criticality
  - QwikJif / RICE Scoring 
  - Timing ("Opportunity Cost" lost in waiting : "Actively Bleeding/Pain")
  - (TPMO/Initiatives) Project Priority
  - Leadership/Client Needs/PRIORITY
- EQA(s) focus on typically solving 1 (at most 2 concurrently) challenge(s) (Stories) - until we're "(Proven/Metrics based) DONE" (Demo'd)
  - (or "Waiting to be Proved/Demo'd")
    - Note: All challenges (Stories) will contain a baseline measurable "KPI/metric" -- which will be proven to be solved, by incremental/complete progress made on each Story KPI
      - Note: Stories move to "Done" once verified as "Proven" solved (based on target KPIs achieved)
      - Note: Expected target of "Challenges/Stories" to be solved per year: ~30-40+ Effort 3-5 Stories/Solutions (Proven) delivered per year (Achieves Expectations)
  - (or "Blocked/With "Another Team") -- Assuming 26 iterations per year ... x2 Stories/iteration
    - Note: There will be a "timer" on the "Wait/Blocked" status Stories - and they will be reported out periodically to the respective Teams, TLs, RTLs, and STLs for visibility - How long we've been blocked by them/waiting
    - Note: Once work items become "unblocked" - work items will re-enter our backlog, be re-prioritized, and then work will resume once again based on priority/timing
- We will aggregate and report out monthly of progress made/solutions delivered -- Evaluated for the actual value delivered
  - Including:
    - Client Feedback
    - Clients Using Solutions (Actively / Monitored)
    - Target KPIs measured/improved upon (Note: "mocked" if not realized actually)
    - OTHER measurements of Success? (TBD) >> How do wee know we're winning AND can prove it to others, regularly



## PROPOSED CHALLENGES TO SOLVE:
- **Load & Performance (incl. Standards/Docs) > Expand Automation (Enterprise)**
- MaaS
- Q2/Halftime
- BETA Env
- Test Data
- Credit Data
- Standards/Guidance (Gatekeeper)
  - [Unit Test & Gatekeeper](https://git.rockfin.com/Continuous-Quality/CQ.Roadmaps/tree/main/UnitTestingGateKeeper)
- SLX
  - SLO Definitions
  - SLIs (DynaTrace)
  - SLAs (internal: Service Now?)
- [Project Evergreen (Strategy / Planning (Lucid)](https://lucid.app/lucidspark/e1f563b6-aae4-4b36-9eb1-e3512f3820aa/edit?invitationId=inv_f2497dd8-e9a6-43c8-846e-1936f39b69cf#)
- We'll want to also align to/support: [RM Technology Goals](https://rockfin.sharepoint.com/sites/RocketTechnology/SitePages/Our-Goals.aspx)

### NOTE: We will want both to help measure our success:
- Client feedback
- Entrance, reoccurring Evaluations, and Exit Criteria 
  - Success criteria (align & buy-in on the problems to solve/deliver -- with clients and us: Who does what/when > **accountability**)
  - Measurable (KPIs) improvements / impact > progress shown
- 

### NOTE: SOLVE FOR ACCOUNTABIITY (& FOLLOW-UPS)
- Who does what when and by what date
- 

## Work Intake (Funnels/Channels > Prioritization):
- Any and all requests are input into the shorty/CQRequest form
  - Peter, Stacie and Deanna are responsible for these items getting in – regardless of the source
- The resulting requests, that are logged in an excel spreadsheet, are ‘triaged’ 1-2 times a week in sessions with Deanna, Peter and Stacie. Other leaders would be optional/made aware of these meetings
  - Stacie currently owns the meeting series
- Aspire acting as the ‘tip of the spear’ will help us analyze requests and determine next steps
- Requests we expect to impact the Continuous Quality roadmap will be triaged and brought to the ‘CQ Core’ meeting for discussion, determining ownership, and prioritization


- "Game Changers" (Self-Identified):
  - Enterprise Issues: Conduct (Aspire) Analysis of the enterprise challenges as a whole *(Metrics Focused)* > Common/Systemic Problems
    - Blameless Incident Reviews (Weekly Cadence) : Opportunities that occur from past "Issues"
    - Look at QHub, AppHub, CloudHub, BIG, Gatekeeper, SonarQube, DynaTrace, PagerDuty, HAL/CircleCI, ServiceNow, Applications Metrics (wherever), etc. >> Targerted specific solutions to solve challenges (metrics based)
    - Postmortems
    - TPMO/Epics/Projects List
    - RMTech Goals (Support / Solving Goals)
    - Rocket Tech Live > # Deployments & # Issues & "Quality"
  - Enablers: Documentation: Guidebook, TechToolbox, StackExchange, Production Agreements, Tooling/POCs, Processes, Work Intake Request Forms, Project Support (no manual testing / guidance & monitoring project health only), etc.
- Dragon Leads
- EE Leads
- Client Work
- [TPMO / Epic List](https://rockfin.sharepoint.com/sites/TechnologyProjectManagement/Lists/TPMO%20Project%20Intake%20List/AllItems.aspx?viewid=cfdf0eca%2Dc03e%2D4bd1%2Daed6%2D6bcefe12b08b&OR=Teams%2DHL&CT=1665514670527&clickparams=eyJBcHBOYW1lIjoiVGVhbXMtRGVza3RvcCIsIkFwcFZlcnNpb24iOiIyOC8yMjA5MDQwMDcxMiIsIkhhc0ZlZGVyYXRlZFVzZXIiOmZhbHNlfQ%3D%3D)


### Stuff to Think About:
- [Software Quality Metrics You Should Be Monitoring](https://cginfinity.com/blog/12-software-quality-metrics-you-should-be-monitoring/)
- [Site Reliavbility](https://chaos.gremlin.com/rs/251-JGH-155/images/Site-Reliability-Engineering-and-DevOps-Can-reliability-and-efficiency-coexist.pdf)
- Chaos Engineering
- Synthetic Testing/Monitoring
- Kubernetes > Automating Testing in K8s / Rancher
  - On-demand testing in a dedicated TESTING infra/env (spin-up > test > tear-down)
- ALL THE QUALITY METRICS: MTTD/R, Coverage, Churn, Complexity, Software metrics, ALL-THE-ILITIES, etc.
- SRE Collaboration : SLX Metrics/Reliabiity/Scalability
- Knowledge Sharing/Transfers/Training : Documentation, Team Sessions (recorded), Mentoring, Presentations, COPs, etc.
- Frameworks/Tooling > Anything that solves "PROBLEMS"


## POTENTIAL RISKS:
- Solving challenges without client feedback and/or priority (don't solve things in a "silo")
- Teams not wanting our solutions
- Tight-Coupling to dependent teams' needs/priorities
- Access (Code Repos, Apps/APIs, skills/knowledge, API Tokens/Auth & Auth, Team members/SMEs, team bascklogs/priority, metrics, etc.)
- Environments/Data, etc.
- "Hand-slapping" > Questions on "Was this the Highest Priority/Why Focused On" >> Why'd you do/doing that? Why is that IMPACTFUL
- App-Dev-Team Ownership "Post/After-the-Fact" of Solutions (hands-off transfers + setup-for-future-success >> Monitored : Wer're watching you perform well)
- Leadership Buy-In & Continued-Commitment (MEASURABLE)
- CLIENT/TEAM PRIORITIZATION
- ALL-THE-KNOWLEDGE-NEEDED: Business, Processes, Systems, etc. (Find ways of getting the info we need faster/easier/more efficiently -- less dependent upon SMEs)
- 

## Open Questions:
- (Naresh) Few things we need to address within CQ: 
  - 1) Create standard test automation frameworks and tools for rollouts 
  - 2) Create Documentation on standards and best practices



## "Going-Deeper" Planning:
1. Discuss which initiatives/capabilities we want to bring into next year/beyond for CQ
2. Discuss how we want to set up work intake pipeline
3. Divvy up rest of work inside of productboard/ADS


### Outcomes should include the following:
1. A short list of agreed upon initiatives
  1.1 Quality Standards > Guidebook/Toolbox
  1.2 Define EQA roles & responsibilities
  1.3 TBD
2. Work intake processes 
  2.1 (See above)
3. Action Items (enabling #1 and #2 -- w/ conn’s and deadline dates)
  3.1  >  1.1 Quality Standards > Guidebook/Toolbox  >  All EQAs/BA (Per Focus Area/Testing Type : TBD)  >  EoQ1
  3.2  >  1.2 Define EQA Roles & Responsibilities  >  All EQAs (Per Focus Area/Testing Type : TBD)  >  EoQ1


## ACTION ITEMS:
- PV: Create a POC GHE "Product/Work Ideation Board" for prioritzation (+4 Boards: ALL CQ {roll-up}, DRAGON, ASPIRE, IMPACT)
- ALL TLs (SB, MZ, PV) > Next CQ Connect Sync > Talk about this page/info
- Review our CQ: [Capabilities & Desired/Future Capabilities](https://lucid.app/lucidspark/ad9f5894-fb1d-4815-bd1d-be5bf6db486b/edit?invitationId=inv_43cd78fb-4623-41b9-8b88-116577f475f1#)
  - "Single Main CQ Board (Prioritized)" > Capabilities/Standards Focused
    - EQAs (tip-of-the-spear) > Ideate & Drive the high-level collaborative initiatives (evaluate the "Value"/business cases) >> Challenges solved (with metrics)
      - TBD


## SHORT TERM GOALS (1/3/23 Iteration?)
- Q2/HT : FW/Reporting (HT takes over their automation & Aspire watches/helps), Pipelines, Processes, Guidance, SauceLabs (LOLA/AMP replacements)
  - Oscar
- Test Case Management Tooling Solutions 
  - Krupali
  - Waiting on SN licensing decisions ("Agile User" in SN to be determined if "regular team members" can access/use)
  - QHub POC (Paolo)
- Unit Testing & Gatekeeper (Q1)
  - Oscar
  - Present to AAT 1/30 - Oscar
  - PR: https://git.rockfin.com/frontier/backlog/issues/1603
  - [Gatekeeper Strategy Doc: Unit Testing](https://git.rockfin.com/Continuous-Quality/CQ.Roadmaps/tree/main/UnitTestingGateKeeper)
- CQ / EE Roadmap (Q1)
  - Divvy up in-flight remaining work & Plan out the upcoming Q1/Q2 initiatives
  - [Official EE Roadmap](https://rockfin.sharepoint.com/:p:/r/sites/EngineeringEnablementLeaders-SeniorLeaderChannel/_layouts/15/Doc.aspx?sourcedoc=%7BE31CDFC2-B4F4-4681-9F2C-A3BC5ECE7FCC%7D&file=EE%20Roadmap%20Template.pptx&wdLOR=cA67EF12C-6C49-AE49-8E4A-D27B19AC91FE&action=edit&mobileredirect=true&clickparams=eyJBcHBOYW1lIjoiVGVhbXMtRGVza3RvcCIsIkFwcFZlcnNpb24iOiIyOC8yMjExMzAwNDEwMCIsIkhhc0ZlZGVyYXRlZFVzZXIiOmZhbHNlfQ%3D%3D&cid=3ffb3a3e-e8f3-4567-8bcd-f6d628fbeec0)
  - [CQ Roadmap]()
- TDG : Rearchitect? (focus on: more Extensible/Maintainable) & Account Creation? 
  - Work with Stacie to figure out
  - LOTS of opportunities/priority
  - "Inner-Source" code base/solution
  - [Architect Diagram]()
- E2E FW > Enterprise Rollout (Q1)
  - Publicize the docs/guidance (Guidebook/Toolbox)
- QHub?
- Enteprise Standards & Best Practices (Quality & Testing & Automation) (Q1)
  - Internal CQ Repos (eat our own dogfood > standardize)
- RKT Rewards Project
  - [RKT Rewards SP](https://shorty/RKTRewardsSignatureCardRedemption)
  - Project Coordination Doc/Guidance Templates/Role: Publicize the docs/guidance (Guidebook/Toolbox)
- MaaS > E2E Testing (UAT & UI Manual / Client Coordination)
  - We help/guide them & Watch them implement
- Enterprise Alignment
  - EQA Role Definition
  - More Collaboration & Alignment with: Leadership (Directors, R/S/TLs), SAs, Team/RT Archs, RTEs, etc.
- Lending Experience: (formerly RPI) Support (Evan Steiner) > Improving Quality > Continued Support?
- STP & CIAT
- KAFKA - Owner: Naresh


