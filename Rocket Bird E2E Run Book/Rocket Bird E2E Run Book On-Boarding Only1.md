
**ONBOARDING E2E TESTING : July 22nd - 23rd**



**WHEN**: Everyday the week of July 22nd – 23rd …  9am – 4pm *(see below for scheduling details)*

**WHERE**: Chrysler House : **<u>Sam&rsquo;s Barbershop 12<sup>th</sup></u> <u>Floor</u>** and streaming virtually: **<u><a href="https://rock-meet.zoom.us/j/5036841666">Peter&rsquo;s Zoom meeting</a></u>**

**WHO**: Anyone directly involved with testing and verifying their applications/processes

*Note: we want to limit the audience to team members directly performing testing or subject matter experts, who will help with testing/scenarios/integration points*

**WHAT**: **Testing RocketBird End-To-End (E2E) in** **BETA**:

- What we are focusing on: ‘Happy Paths’ and MVP scenarios, and the hand-offs between applications and systems
    - *Note: If time allows, then we’ll also consider some negative testing scenarios as well; however, we want to focus on ensuring that basic workflows, processes, and our applications work as expected, especially with respect to integrations between systems*
    - *Note2: We chose this “time-boxed” format in order to limit the amount of churn/chaos for teams/testers*
- We will be following the workflows detailed in the **[RocketBird E2E RunBook](https://confluence/display/RB/Rocket+Bird%3A+E2E+Run+Book)** ([http://shorty/rbe2e](http://shorty/rbe2e))


**ISSUE LOGGING:** We will log any **E2E Bugs**: [http://shorty/rbbugs](http://shorty/rbbugs)



**Action Item:**Please work with your apps/teams to identify team members: who/what they will be testing – and add them within this [E2ERunbook](https://confluence/display/RB/Rocket+Bird%3A+E2E+Run+Book)!



**Scheduled E2E Time Duration Per Section / Apps:**

*Note: Please make sure your identified testers/SMEs are ready to test during their time slot(s)!*


| RocketBird E2E | Monday 7/22 | Tuesday 7/23 |
| --- | --- | --- |
| Morning: 9a - 12p | <ul><li><a href="https://confluence/pages/viewpage.action?pageId=152928960">Redbird Interest &amp; Qualtrics</a></li><li><ac:link><ri:page ri:content-title="COPYRB E2E: Licensing Team: Wave Decisioning / Intake Process"></ri:page><ac:plain-text-link-body><![CDATA[Licensing Team: Wave Decisioning / Intake Process]]></ac:plain-text-link-body></ac:link><span style="color: rgb(0,0,0);"><br></span></li><li><ac:link><ri:page ri:content-title="COPYRB E2E: Workday: BackGround"></ri:page><ac:plain-text-link-body><![CDATA[Workday: BackGround]]></ac:plain-text-link-body></ac:link></li><li><ac:link><ri:page ri:content-title="COPYRB E2E: Credential Check"></ri:page><ac:plain-text-link-body><![CDATA[Credential Check]]></ac:plain-text-link-body></ac:link></li></ul> | <ul><li><ac:link><ri:page ri:content-title="COPYRB E2E: WorkDay: Hiring"></ri:page><ac:plain-text-link-body><![CDATA[WorkDay: Hiring]]></ac:plain-text-link-body></ac:link> (continued)</li><li><ac:link><ri:page ri:content-title="COPYRB E2E: Provisioning"></ri:page><ac:plain-text-link-body><![CDATA[Provisioning]]></ac:plain-text-link-body></ac:link>:<ul><li>Accounts Created: AzureAD, CSA, MIM, Saba</li></ul></li><li><span style="color: rgb(0,0,0);">Authentication: </span><ul><li><span style="color: rgb(0,0,0);">Ability to login: </span><span style="color: rgb(0,0,0);">AzureAD, PING, DUO, Auth0, Office365, Workday, RocketPro, </span>Saba</li></ul></li><li><ac:link><ri:page ri:content-title="COPYRB E2E: CSA"></ri:page><ac:plain-text-link-body><![CDATA[CSA]]></ac:plain-text-link-body></ac:link></li></ul> |
| --- | --- | --- |
| Afternoon: 1p - 4p | <ul><li><ac:link><ri:page ri:content-title="COPYRB E2E: WorkDay: Hiring"></ri:page><ac:plain-text-link-body><![CDATA[WorkDay: Hiring]]></ac:plain-text-link-body></ac:link></li></ul> | <ul><li><ac:link><ri:page ri:content-title="COPYRB E2E: BLING-Licensing"></ri:page><ac:plain-text-link-body><![CDATA[BLING-Licensing]]></ac:plain-text-link-body></ac:link></li><li><a href="https://confluence/display/RB/RB+E2E%3A+SignatureApp?src=contextnavpagetreemode">SignatureApp</a></li></ul> |
| --- | --- | --- |




**Note:**

This is the first time we’ll be able to conduct end-to-end testing (by being initially dev complete for 6/21). We will potentially have more of these E2E sessions in the upcoming weeks leading up to “go-live launch”; (however, in a much more streamlined manner).

Since this is our first run-through of E2E, we expect to learn a lot, uncover some gotchas/holes, and find some needed fixes…

Which is why we’re doing E2E: To ensure a seamless, quality client experience for our RedBird users!



# <u><strong>IMPORTANT INFO:</strong></u>

**OVERALL PROCESS FLOW:**[http://shorty/LOLifecycle](http://shorty/LOLifecycle)

**OVERALL ARCH DIAGRAM:**<ac:link><ri:page ri:space-key="~ABruford" ri:content-title="1099 Influencer Data Flow (DRAFT)"></ri:page></ac:link>

**Rocket Bird Docs (RMA):**<ac:link><ri:page ri:space-key="RMSolutions" ri:content-title="Rocket Bird Technical Documentation"></ri:page></ac:link>

**Test Data / Common IDs:** [RB E2E: Test Data / Common IDs](https://confluence/pages/viewpage.action?pageId=150178956&amp;src=contextnavpagetreemode)

**Bug Logging Here:**[http://shorty/rbbugs](http://shorty/rbbugs)



## **Status Key**


| Status Key<br> | Status<br> |
| --- | --- |
| This task has not yet been implemented and tested in BETA | <br>**INCOMPLETE**<br> |
| This task is completed and tested in BETA | <br>**COMPLETE**<br> |
| In-Progress | <br>**IN-PROGRESS**<br> |
| Skipped over / Fake data used | **COMPLETE** |




## **RocketBird E2E (in BETA)**

<u><strong>Stuff We Need to Document/Ensure:</strong></u>

- Triggers into processes (prerequisites)
- What testing is being done / how / by whom
- Detailed workflow processes using what data (sequential)
- Integration Points (Other Apps/Etc.)
- Triggers/outputs from your processes (output)





| <br> | Process Steps / Things to Ensure:<br><br>(Function / System)<br> | Owner/Responsibility Conn (PO)<br><br>(Primary / Secondary)<br> | SME / Testing Conn<br><br>(Primary / Secondary)<br> | Input and Output Triggers / Notifications | Estimated Duration<br> | Status<br><br>(Complete / Not Started)<br> |
| --- | --- | --- | --- | --- | --- | --- |
| <br> | OnBoarding Section | <br> | <br> | <br> | <br> | <br> |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | <ac:link><ri:page ri:content-title="COPYRB E2E: Redbird Interest &amp; Qualtrics"></ri:page><ac:plain-text-link-body><![CDATA[RB E2E: Redbird Interest & Qualtrics]]></ac:plain-text-link-body></ac:link><br> | <br><ac:link><ri:user ri:userkey="8a8903604c9fa921014ca4003dff1a5d"></ri:user></ac:link><br> | <br><ac:link><ri:user ri:userkey="8a8903604c9fa921014ca4003dff1a5d"></ri:user></ac:link><br> | RedBird Email | 60mins | <br>**INCOMPLETE**<br> |
| 2 | <ac:link><ri:page ri:content-title="COPYRB E2E: Licensing Team: Wave Decisioning / Intake Process"></ri:page></ac:link> | <br><ac:link><ri:user ri:userkey="8a8903605d45dfb2015d7e8743fd0021"></ri:user></ac:link><br> | <br><ac:link><ri:user ri:userkey="8a8903605d45dfb2015d7e8743fd0021"></ri:user></ac:link><br> | Qualtrics .CSV | 10mins | <br>**INCOMPLETE**<br> |
| 3 | <ac:link><ri:page ri:content-title="COPYRB E2E: Workday: BackGround"></ri:page></ac:link> | <br>Integrations: <ac:link><ri:user ri:userkey="8a8903604c9fa921014ca40040271afe"></ri:user></ac:link><br><br>HRIS: Meghan Hayward<br> | <br>**Integrations**: <ac:link><ri:user ri:userkey="8a8903604c9fa921014ca400343a1784"></ri:user></ac:link> <ac:link><ri:user ri:userkey="ff8080814adbc64a014ae01e847d000a"></ri:user></ac:link> <ac:link><ri:user ri:userkey="8a890360620700f90162d2b1b131003a"></ri:user></ac:link><br><br><br><br>**HRIS**: <ac:link><ri:user ri:userkey="ff8080814c4551ed014c47fbf86c0003"></ri:user></ac:link> Sydney Frazer<br> | Each Wave's .CSV | 30mins | <br>**INCOMPLETE**<br> |
| 4 | <ac:link><ri:page ri:content-title="COPYRB E2E: Credential Check"></ri:page></ac:link> | <br>Integrations: <ac:link><ri:user ri:userkey="8a8903604c9fa921014ca40040271afe"></ri:user></ac:link><br><br>HRIS: Meghan Hayward<br> | <br>**Integrations**: <ac:link><ri:user ri:userkey="8a8903604c9fa921014ca400343a1784"></ri:user></ac:link> <ac:link><ri:user ri:userkey="ff8080814adbc64a014ae01e847d000a"></ri:user></ac:link> <ac:link><ri:user ri:userkey="8a890360620700f90162d2b1b131003a"></ri:user></ac:link><br><br><br><br>**HRIS**: <ac:link><ri:user ri:userkey="ff8080814c4551ed014c47fbf86c0003"></ri:user></ac:link> Sydney Frazer<br> | Output: Pass/Fail (API)<ul><li>If FAIL:<ul><li>Receive a pre-adverse-action action from QL (Dispute)</li><li>Execute the &quot;dispute&quot; process</li><li>Send adverse action letter (email???)</li></ul></li><li>IF PASS:<ul><li>Trigger the API call to QL</li></ul></li></ul> | 10mins | <br>**COMPLETE**<br> |
| 5 | <ac:link><ri:page ri:content-title="COPYRB E2E: WorkDay: Hiring"></ri:page></ac:link> | <br>Integrations: <ac:link><ri:user ri:userkey="8a8903604c9fa921014ca40040271afe"></ri:user></ac:link><br><br>HRIS: Meghan Hayward<br> | <br>**Integrations**: <ac:link><ri:user ri:userkey="8a8903604c9fa921014ca400343a1784"></ri:user></ac:link> <ac:link><ri:user ri:userkey="ff8080814adbc64a014ae01e847d000a"></ri:user></ac:link> <ac:link><ri:user ri:userkey="8a890360620700f90162d2b1b131003a"></ri:user></ac:link><br><br><br><br>**HRIS**: <ac:link><ri:user ri:userkey="ff8080814c4551ed014c47fbf86c0003"></ri:user></ac:link> Sydney Frazer<br> | <br> | 60mins | <br>**COMPLETE**<br> |
| 6 | <ac:link><ri:page ri:content-title="COPYRB E2E: Provisioning"></ri:page></ac:link> : AzureAD | <br><ac:link><ri:user ri:userkey="8a8903604c9fa921014ca4003983191d"></ri:user></ac:link><br> | <br><ac:link><ri:user ri:userkey="8a8903604c9fa921014ca3ffc39e0039"></ri:user></ac:link> <ac:link><ri:user ri:userkey="8a8903604c9fa921014ca40048621de9"></ri:user></ac:link> <ac:link><ri:user ri:userkey="8a890360543881050155719013cf00e8"></ri:user></ac:link><br> | <br> | 20mins | <br>**COMPLETE**<br> |
| 7 | <ac:link><ri:page ri:content-title="COPYRB E2E: Provisioning"></ri:page></ac:link> : PING | <br><ac:link><ri:user ri:userkey="8a8903604c9fa921014ca4003983191d"></ri:user></ac:link><br> | <br><ac:link><ri:user ri:userkey="8a8903604c9fa921014ca4002200120a"></ri:user></ac:link>, <ac:link><ri:user ri:userkey="8a8903605dec852c015f398d2ff000b9"></ri:user></ac:link><br> | <br> | 20mins | <br>**COMPLETE**<br> |
| 8 | <ac:link><ri:page ri:content-title="COPYRB E2E: Provisioning"></ri:page></ac:link> : DUO | <br><ac:link><ri:user ri:userkey="8a8903604c9fa921014ca4003983191d"></ri:user></ac:link><br> | <br><ac:link><ri:user ri:userkey="8a8903604c9fa921014ca4002200120a"></ri:user></ac:link>, <ac:link><ri:user ri:userkey="8a8903605dec852c015f398d2ff000b9"></ri:user></ac:link><br> | <br> | 20mins | <br>**COMPLETE**<br> |
| 9 | <ac:link><ri:page ri:content-title="COPYRB E2E: Provisioning"></ri:page></ac:link> : Auth0 | <br><ac:link><ri:user ri:userkey="ff8080814adbc64a014af354dd2f002f"></ri:user></ac:link><br> | <br><ac:link><ri:user ri:userkey="ff8080814906e07101491ec208670015"></ri:user></ac:link><br> | <br> | 20mins | <br>**COMPLETE**<br> |
| 10 | <ac:link><ri:page ri:content-title="COPYRB E2E: Provisioning: Saba"></ri:page></ac:link> | <br><ac:link><ri:user ri:userkey="ff8080814affe0b1014b5beb82b5005e"></ri:user></ac:link><br> | <br><ac:link><ri:user ri:userkey="8a8903605438810501550a90752f00ac"></ri:user></ac:link><br> | <br> | 20mins | <br>**COMPLETE**<br> |
| 11 | <ac:link><ri:page ri:content-title="COPYRB E2E: Provisioning"></ri:page></ac:link> : SIFT | <br><ac:link><ri:user ri:userkey="ff8080814affe0b1014b5a0454560057"></ri:user></ac:link><br> | <br><ac:link><ri:user ri:userkey="ff8080814906e07101491ec208670015"></ri:user></ac:link><br> | <br> | 20mins | <br>**COMPLETE**<br> |
| 12 | <ac:link><ri:page ri:content-title="COPYRB E2E: Provisioning"></ri:page></ac:link> : MIM | <br><ac:link><ri:user ri:userkey="8a8903604c9fa921014ca4003983191d"></ri:user></ac:link><br> | <br><ac:link><ri:user ri:userkey="8a8903604c9fa921014ca3ffc39e0039"></ri:user></ac:link> <ac:link><ri:user ri:userkey="8a8903604c9fa921014ca40048621de9"></ri:user></ac:link><br> | <br> | 20mins | <br>**COMPLETE**<br> |
| 13 | <ac:link><ri:page ri:content-title="COPYRB E2E: Provisioning"></ri:page></ac:link> : Office365 | <br><ac:link><ri:user ri:userkey="ff8080814adbc64a014ae9c45e76001d"></ri:user></ac:link><br> | <br><ac:link><ri:user ri:userkey="8a890360543881050155719013cf00e8"></ri:user></ac:link>, <ac:link><ri:user ri:userkey="8a8903605438810501544e0a6c380004"></ri:user></ac:link><br> | <br> | 20mins | <br>**COMPLETE**<br> |
| 14 | <ac:link><ri:page ri:content-title="COPYRB E2E: CSA"></ri:page></ac:link> | <br><ac:link><ri:user ri:userkey="ff8080814adbc64a014af3428a37002e"></ri:user></ac:link>, <ac:link><ri:user ri:userkey="8a8903605214a9180153423432eb0055"></ri:user></ac:link>, <ac:link><ri:user ri:userkey="ff8080814affe0b1014b5a0454560057"></ri:user></ac:link><br> | <br><ac:link><ri:user ri:userkey="ff8080814adbc64a014af3428a37002e"></ri:user></ac:link>,  <ac:link><ri:user ri:userkey="8a8903605214a9180153423432eb0055"></ri:user></ac:link><br> | Input: Hired folks into Workday (flatfile: CSV/TXT) &gt; File dropped &gt; CSA Picks it up<br>Output:<br>Team Member Table with LO data is distributed to all systems: ~150 systems<br><ul style="list-style-type: square;"><li>CSA sends a SSIS package to all dependent system's tables</li></ul> | 120mins | <br>**COMPLETE**<br> |
| 15 | <ac:link><ri:page ri:content-title="COPYRB E2E: BLING-Licensing"></ri:page></ac:link> | <br><ac:link><ri:user ri:userkey="ff8080814bd81a96014befc6ba6c0034"></ri:user></ac:link>, <ac:link><ri:user ri:userkey="ff8080814adbc64a014adf36c5620003"></ri:user></ac:link><br> | Team Batman | Input: CSA provides TM Table is updated with new data (SSIS notifications)<br><br>Input: NMLS Data (nightly) &gt; Updated for bankers that are "hired" (this may take some time to "mock-up/fake the data")<br> | 90mins | <br>**COMPLETE**<br> |



