# Aspire to Better
# Our Path to Excellence
## A Proposal/Plan for Test Data Quality



## Problem Statement (Context)
We have "test data" in BETA (and PROD) environments, which leads to all kinds of badness:
- "Band-aid" logic / solutions in code
- Unreliable testing of data / our systems
- No consistent process for deleting data/scenarios we create (regularly)
- No documented/well-understood process for tagging "Test Data"
- Lots of "etceteras"

## Hypothesis Statment (Action)
We propose that the following experiments/actions will allow us to resolve the aforementioned issues:
- Understand our "Loan Data and Lineage"
  - What: Identify all data points needed for a loan
  - Who: What systems need what/which portions of the loan data points
  - When: When is the data needed 
  - Where: Where did the Loan data points originate/populate from {source system(s)}
  - Why: Do we really require that data point: who needs it, why > Document it all!
-  "Tagging Test Data" (999s and/or a field in AMP)
-  "CRUD Ops Needed esp. Deleting Test Data" (practice in BETA, gain trust in the processes, then implement in PROD)
  - Ultimately, being able to conduct valid "Testing in Prod"

### Open Questions/Answers:
- How do test loans get into AMP?
  - Other systems bombard AMP Beta daily
  - Loans copied back from Prod into Beta for research (created/copy processes: manual, test automations, Test Data Generator (TDG) tool, home grown loan-copy tools, etc.)
  - All Origination Systems/Eco-Systems: 
    - Rocket Pro Originate (TPO), RMA/RMO/RMS, Rocket Pro, Mobile team, LOLA, Our House Rocket Logic
- How do we decrease the number of test loans in production?
  - Need a way for them to test confidently in Prod
  - Should they be testing in Prod?
  - Peter’s team documenting fields needed to create loans in Beta and automate it.
  - Potentially create a new DB field called IsTestLoan and default to No.
  - Have teams update test loans with this field set to Yes.
  - Cleanup all unflagged test loans in Beta.
  - Create a job to read in a list of test loans that can be deleted.
  - ACD with an older date, renaming to ZZZZ and cleaned up after 2 weeks (Christine A’s team). Purging about 2500 loans a day.
- What guidelines exist for teams interacting with AMP as to how and when to clean-up test loans?
  - Is anything in the guidebook?
  - Loan number must be changed to 99 or 9999 (AMP code looks for one or the other)
  - Fannie Mae test case SSN
  - Is there a timeframe that they must be cleaned up in?  Can we create a tidal job that runs weekly to cleanup loans?
- OpenAMP has an endpoint that can be used to delete test loans – where is it?
  - The api exists in Beta. 
  - Calls loancopy logic to create a copy of the loan.
  - Then calls loandelete code to delete it after done.


### Action Items/Experiments/Learnings:
- Research what quantifies a test loan in AMP – Faith & Becky
- Research what it means to integrate test loans with other systems – Mark & Steph
- Query test loans: John Homeowner; Alice Firsttimers; 99 first account# in all environments – Team Shield
- Document "Test Loan Data Process" in the Guidebook - Peter


### Preliminary Meetings Attendees:
- La Luna, Vickie <VickieLaLuna@rocketmortgage.com>; Eaton, Stephanie <StephanieEaton@rocketmortgage.com>; Adkins, Mark <MarkAdkins@rocketmortgage.com>; Murtaugh, Rebecca <RebeccaMurtaugh@rocketmortgage.com>; Sajdak, Faith <FaithSajdak@rocketmortgage.com>; Dunne, Rachel <RachelDunne@rocketmortgage.com>
- Armbrust, Doug <DougArmbrust@rocketmortgage.com>; Stuckey, Vincent <VincentStuckey@rocketmortgage.com>; Bennett, Jason <JasonBennett@rocketmortgage.com>; Herring, Ken <KenHerring@rocketmortgage.com>; Varga, Peter <PeterVarga@rocketmortgage.com>; Andrusiewicz, Christine <ChristineAndrusiewicz@rocketmortgage.com>; Walker, Dan <DanWalker@rocketmortgage.com>


## Things Learned/Summary (Results)


### TBD - Experimentation Underway / In-Progress

 
