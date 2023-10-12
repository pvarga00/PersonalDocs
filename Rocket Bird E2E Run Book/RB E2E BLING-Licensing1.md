
## **RocketBird E2E (in BETA):**

[Rocket Professional Loan Officer (LO) Life Cycle Diagram](https://editor.signavio.com/p/hub-preview#model/ff04d56e3b8644cd880073bf5a6af3ab;diagram) (Overall)



**Process + Things To Test/Verify:**

- Triggers into processes (prerequisites)
- What testing is being done / how / by whom
- Detailed workflow processes using what data (sequential)
- Integration Points (Other Apps/Etc.)
- Triggers/outputs from your processes (output)



| <br> | Process Steps / Things to Ensure:<br><br>(Function / System)<br> | Owner/Responsibility Conn (PO)<br><br>(Primary / Secondary)<br> | SME / Testing Conn<br><br>(Primary / Secondary)<br> | Input and Output Triggers / Notifications<br> | Estimated Duration<br> | Status<br><br>(Complete / Not Started)<br> | Notes / Issues<br> |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | BLING Tables updated:<br><ac:task-list><ac:task><br><ac:task-id>6</ac:task-id><br><ac:task-status>complete</ac:task-status><br><ac:task-body>Identify bankers in the updates &gt; appear in BLING (search by banker)<ac:task-list><br><ac:task><br><ac:task-id>7</ac:task-id><br><ac:task-status>complete</ac:task-status><br><ac:task-body>Ensuring: TM Data populated + correlated to NMLS data (deficiencies / requirements)</ac:task-body><br></ac:task><br></ac:task-list></ac:task-body><br></ac:task></ac:task-list> | <br><ac:link><ri:user ri:userkey="ff8080814bd81a96014befc6ba6c0034"></ri:user></ac:link>, <ac:link><ri:user ri:userkey="ff8080814adbc64a014adf36c5620003"></ri:user></ac:link><br> | Team Batman | Input: CSA provides TM Table is updated with new data (SSIS notifications)<br><br>Input: NMLS Data (nightly) &gt; Updated for bankers that are "hired" (this may take some time to "mock-up/fake the data")<br> | 60mins | **COMPLETE** | <br> |
| 2 | License Check: Check on originating a new loan: (on Address entry / State):<ac:task-list><ac:task><br><ac:task-id>8</ac:task-id><br><ac:task-status>incomplete</ac:task-status><br><ac:task-body>New Loan Originating: Also check for &quot;bad status&quot; (expired license, surrendered, approved-inactive, disabled accounts)</ac:task-body><br></ac:task><br><ac:task><br><ac:task-id>9</ac:task-id><br><ac:task-status>incomplete</ac:task-status><br><ac:task-body>1B) Licen<span style="letter-spacing: 0.0px;">se </span><span style="letter-spacing: 0.0px;">Check on Existing (in-progress) Loans: </span><ac:task-list><br><ac:task><br><ac:task-id>10</ac:task-id><br><ac:task-status>incomplete</ac:task-status><br><ac:task-body><span>Loans becomes unclickable/accessed(clicked) for unlicensed states - can longer enter the loan</span><span><br></span></ac:task-body><br></ac:task><br></ac:task-list></ac:task-body><br></ac:task></ac:task-list> | <br><ac:link><ri:user ri:userkey="ff8080814bd81a96014befc6ba6c0034"></ri:user></ac:link>, <ac:link><ri:user ri:userkey="ff8080814adbc64a014adf36c5620003"></ri:user></ac:link><br> | Team Batman | Check the logs to ensure that successful / disabled LOs can/cannot access RocketPro | 30mins | **INCOMPLETE** | "All the flavors" of licensing a LO can be in - mocked data needed for these<br><br>Dependency: License Service<br><br>NOTE: There is no licensing check in BETA - we "faked" the API call - and it worked as expected - but a not true test - as we cannot validate the messaging from RB (tested TEST + BETA both)<br> |






<u><strong>BLING</strong></u>

**Conn**: <ac:link><ri:user ri:userkey="ff8080814bd81a96014befc6ba6c0034"></ri:user></ac:link>, <ac:link><ri:user ri:userkey="ff8080814adbc64a014adf36c5620003"></ri:user></ac:link>

- Triggers into processes (prerequisites)
- What testing is being done / how / by whom
    - Team Batman:

        - Workday data arrives into BLING

            - Ensure LO data is in BLING's TM table
            - **\*More details needed**
        - Load test of expected influencer value on BLING system
**<ac:link><ri:page ri:space-key="IER" ri:content-title="BLING Red Birds Stress Test Plan"></ri:page><ac:link-body><span style="color: rgb(128,0,128);">BLING Red Birds Stress Test Plan</span></ac:link-body></ac:link>**
**<ac:link><ri:page ri:space-key="IER" ri:content-title="BLING Red Birds Stress Test Analysis"></ri:page><ac:link-body><span style="color: rgb(128,0,128);">BLING Red Birds Stress Test Analysis</span></ac:link-body></ac:link>**
- Detailed workflow processes using what data (sequential) - Licensing Flow for BLING
    - Data gets placed into Workday
    - CSA moves data and populates data tables for all systems that aren’t provisioned by MIM. Systems provisioned by MIM are LOLA and AMP (Dakota Ridder can explain more about this process)
    - CSA moves data into BLING team member table and banker table. Once in this table these bankers appear in BLING.
    - Bankers are licensed in BLING based on their current licenses they have, or by the licenses that themselves or Redbird want them to have.
    - BLING reads in licensing file from NMLS which will contain Redbird bankers, and then updates both BLING and the Licensing service with their license status
- Triggers/outputs from your processes (output)



