
**Key Topics:**



1. Define the why, what, who, when, how for Redbird end to end testing
2. Discuss expectations
    1. Buy in that each team is testing their own functionality
3. Follow up on Tactical Next Steps:
    1. Peter Varga posted current e2e testing documentation on shorty/RBQAS
    2. CONN: Tanya to set up follow on to complete discussion on the who and how
    3. Peter to email group what documentation is needed for him to start putting together the e2e test strategy
    4. Coming soon: Peter to Working session to define scenarios
    5. Coming soon: Visibility (knowledge of what has been testing, pass/fail, bugs) and Coordination on how to solve bugs




**Key Discussion Points:**



**Why as we doing e2e testing for Redbird?**

    1. Need to have an exceptional experience for the client and the influencer
    2. Need to have a successful transfer from the Redbird Loan Officer to the QL Banker and the QL CE/OPS Team Member
    3. Need these influencers to be able to originate loans
    4. Need to be able to onboarded
    5. QL will need to sponsor these Redbird individuals (agents). Therefore existing licenses must be transferred.
    6. Ensure they have access to systems they should and do not have access to the systems they should not
    7. Needs to be a compliant process and technology
    8. Need to make sure reporting is working as expected
    9. Influencers can see all assigned clients in their client list
    10. This solution needs to work end to end (it is not enough for individual components to work)




**The What?**

    - Scope for Onboarding and Licensing


        1. Need to make sure they can fill out a QUALTRICS form and that we can download results. This kicks off who is interested and also data we need to start onboarding.
        2. Ensuring workday accounts get created via excel document that gets uploaded STFP
        3. Once workday profile created, Redbird LO gets an email notification
        4. Ensure the Redbird can access their candidate profile in Workday
        5. Ensure the Redbird LO can fill out appropriate forms. Consent and personal data.
        6. Background check gets executed, including sending data to BC check vendor
        7. Either they return a pass or a fail. We would want to check that the vendor didn’t mess it up.
        8. Consume pass or fail. If fails, make sure SOA has access to Dashboard to show them failures. Then they do their manual process. LO gets a notification of the failure and have an opportunity to dispute it (ensure dispute info sent). Note there is some debate ongoing right now about how we notify Redbird LO on failures. If it BC passes, workday sends notification they passed and notify them of next steps. LO comes back to workday to provide more info.
        9. Make sure can reset Workday PW if they need to. Make sure can fill out MLO agreement and w9.
        10. Contracted into Workday. Create as a Team Member.
        11. Azure ID integration will fire account. Provision email account and AD account.
        12. Email address written back to Workday.
        13. Workday to trigger another set of email, which is you made it good job. Here is next steps, licensing and training expectations.
        14. Need to be able Sign back into Workday and fill out ACH for direct deposit.
        15. Invited to reset their email PW which is LOG in for all the systems (SABA, RocketPro, Workday, Office 365)
        16. Test access to all systems.
        17. DUO multi factor authentication for each application.
        18. Test data distributed to CSA. CSA distributes data to all Applications. Bling, CSA web service (AMP and LOLA use). HR onbase for doc storage.
        19. Ensure the Redbird LO shows up in SIFT.
        20. Make sure they can update in Workday their ACH, legal name, home addresses, preferred name, email address and phone numbers.
        21. Licensing Steps
            - In Bling, make sure they fall into right hot lists
            - Make sure licensing data comes with them as we will be getting data from NMLS (nightly job). CONN: Tanya to follow up with Battershell.
            - Make sure if deficiency falls under this hotlist
            - Make sure have access to **My License Center**
            - Need to be able to update NMLS and passwords (My License Center)
            - Assigned a licensing contact? Puja/Jen to follow up. CONN: Tanya to ask Battershell.
            - Bling HR Onbase transfer to NMLS (need to validate with someone from business)
            - Need to ensure that the licensing team can fill out spreadsheet to provide to HRIS who will upload to workday. Data in excel will be their branch location and address.
            - Make sure licensing information transfers to AMP.
            - We will not configure authentication to my License Center until 9/1


    - Rocket Bird


        1. Need to be able to successfully sign into RocketPro
        2. If they forget PW, need to be able to reset from that screen
        3. Upon log in, need to be able to see all Loans that are assigned to them in their Client List
        4. Expect Client List to reflect status updates from AMP
        5. Three States: Redbird LO in control, QL in control, DONE for one reason or another ( live there for 60 days, then fall off)
        6. Need to have assigned QL contact person show next to each individual client. In situation where active with the Redbird LO state, expect it to be blank, Unassigned or TBD
        7. From Client list, LO needs to be able to do three things: straight referral and submit refer form(HBLP process), start a new application (forks to RMA), and go into open application and continue RMA
        8. New origination: Make sure that the loan can be transferred at ANY point not just due to a PIT STOP. The Redbird LO gives up and transfers to QL Banker. Assign to QL banker at this time.
        9. For happy path get all the way through product selection. At that point, handoff to a QL Banker by pressing select my product button.
        10. Pitstops: Working this out as to which ones could be moved post product selection. If hard pit stop, it will halt the Redbird LO from moving forward.
        11. Test ability to withdraw at any time up until product selection. What happens to the data and any downstream process? Need to Follow Up - Ask Manisha.
        12. Top Priority: As a whole need to have a separate meeting to discuss Compliance Testing is critical (TRID Timers, ECOA, Banker of Record , Withdrawals, AKA correct name on documents). Need to collaborate as a team to ensure this is covered. CONN: Tanya to reach out to Phadraeh (for docs), Vicki L (Puja, TIMERS) to set up compliance testing meeting. By next week.
            - Need a Deep DIVE within the next week
            - Leverage existing automated tests.
        13. Need to test ability to have agents send signatures on documents.
        14. Need to test loan channel/sub channel.
        15. Test what happens with LO terminated pre/post product selection.
        16. Make sure that the Redbird LO is compensation per the requirements (product selection, loan closes, loan disburses). Make sure AMP generates the excel file. Make sure it gets put into right location where Workday and pick it up and processes it. Make sure Workday can issue Direct Deposit or Check. TBD: whether payment issued displayed in Workday.
        17. Contact Names and Addresses
            - Implications of Internal versus External Contact (one of the “R” systems does not consume the internal contact). Qtweet functionality. Reporting implications.
            - In AMP, doesn’t show internal versus external contact.
            - How do we view this person? Are they internal or external entity? They should be INTERNAL.


    - Although the testing will be centered around technology, there are aspects of the process that will be critical to be tested (for example, correct toll free phone number showing the screen, make sure the right titles are displaying, Internal QL Support Team Members (if new position created) will need to be able to access LOLA and AMP as an example.
    - Once Jen finalizes support model and process, she will get with Peter and Dakota to highlight and identify touchpoints with technology solutions
    - Need to test integrations with Loan Engine, Einstein, and Document Services
- **Type of Testing?**
    - Manual and Automated.
    - Can we reuse RMA automated testing? Peter spent yesterday working with RMA automated tests and plans to leverage.
    - Peter looks to automate as much as possible.
- **Who?**
    - Peter will be the quarterback taking it all the way through. Putting together a run book. Coordination of all of the handoffs.
    - Who specifically will do what in the e2e testing process? Expectation is that each PO test individual components and do as much e2e testing within their product.
    - Get Redbird Clients to participate in e2e testing (follow up required with Redbird). CONN: Dan D to coordinate with Redbird and include in implementation strategy recommendation.
    - Karlee volunteered to partner with Peter V to do end to end testing for onboarding, licensing and Rocket Bird
- **When?**
    - Entire month of July allocated to e2e testing
- **How?**
    - Test Party going through the Run Book (could be virtual)
- **How deep should testing go?**
    - Client and LO User experience
    - Integration Testing -  AMP, LOLA, Pitstops, Credit getting pulled
    - API Testing
    - LO gets paid
    - Terminated
- **Environments?**
    - **Next Meeting**
- **Test Data?**
    - **Next Meeting**




**------------**





**ROCKETBIRD**

What is needed for Rocket Bird: ?

- Scope / mvp




Automations: ??

Unit

System (API)

Integration (API)

UI



Applications Involved:

RocketPro UI

RocketPro BFF

??



Test Data / Scenarios: ??



Environments: ?

AWS?

TEST &gt; BETA &gt; PROD



Deployment Pipelines?

————



**NOTES FROM MEETING WITH TANYA BRENNAN:**

- DEV Complete 7/1
- Work with Stacey Adams to ensure E2E… MVP scenarios / integrations
- OnBoarding process - ASAP
- Rob Costello / Karlee Pikarski - RocketPro scenarios




————



Ask QEs:

How do we catch integration issues faster? Did we not test APIs with dependencies enough?





**ACTION ITEMS:**

- **E2E + Test Strategy (Documented + Tracked)**
- **Start physically coding E2E scripts (me/Peter)**
    - **ESP. in-between components**




- And figure out the names of each QE who is testing each component \*AND\* it’s nearest integrations… (for each box + between ‘em)
- Test script inventory
- “One Team”
- BA:
    - Functional Testing
    - Integration Testing
- QA:
    - Automation (one iteration behind)
    - E2E (one iteration behind)





