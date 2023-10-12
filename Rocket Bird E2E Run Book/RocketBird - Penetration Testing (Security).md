
InfoSec: [Penetration Test Process & Requirements](https://confluence/pages/viewpage.action?pageId=76431538)

Request a Pen Test: [http://shorty/breakmystuff](http://shorty/breakmystuff)



GUMP SUMMARY: COMPLETED

We have completed the authentication related re-test of the R\*bird Desktop application, including the client application front-end, the licensing portal, and the signature application. This testing was specifically done to review the new Auth0 change. We only have two findings, both of which were reported during previous testing:

1. Loan applications registered to a given agent can be accessed by other agents if the GUID for the application is known or could be guessed. To test, log into the application as two different users in two different browsers. Copy the link address for the View Loan button for one user and paste it into the address bar for the second user. That will become the active loan for the second user despite it not being within the list of loans. This is against the desired access control model.
2. The Front End application uses an older, known-vulnerable version of the jQuery JavaScript library (2.2.4)




The access control issue should be fixed if we are expecting to deny access between agents’ applications. In general, ownership of each application should be recorded and this value checked against the logged in user of the application each time access is attempted. The risk is muted somewhat due to the nature of the identifier (a GUID) since it is rather hard to guess or brute-force valid/in-use identifiers.

This plan is changing/updating to accommodate new changes to authentication. All apps have been through pen testing already, and this updated plan reflects focus now on: authentication/authorization, session handling, access control, etc.



**NOTE:** We are tentatively scheduling this round of pen testing for the week of: **9/9/2019**.

## **RocketBird Pen Test Info:**

- What specifically is to be tested (server names, URLs, functions, etc.)
    - **RocketPro** : "Front-end" UI (RocketPro), all back-end systems in BETA: BETA URL: [https://beta.rocketprofessional.com/](https://beta.rocketprofessional.com/)
        - Arch/Business Flow diagrams:
            - [https://rockfin.sharepoint.com/sites/RedbirdProgram/Shared%20Documents/Rocket%20Bird/Process%20Flows/Redbird\_050219\_TechFlowForLegal.pdf](https://rockfin.sharepoint.com/sites/RedbirdProgram/Shared%20Documents/Rocket%20Bird/Process%20Flows/Redbird_050219_TechFlowForLegal.pdf)
        - RocketPro Login/User Accounts: <ac:link><ri:page ri:content-title="COPYRB E2E: Rocket Pro"></ri:page></ac:link>
    - **LicensePro:** [https://licenseproui.beta.licensepro-np.foc.zone/](https://licenseproui.beta.licensepro-np.foc.zone/)
    - **SignatureApp:** [https://beta.rocket-signature.com/](https://beta.rocket-signature.com/)
    - **Auth0**
- Why we are testing it
    - To ensure QL and client information is secure
    - To ensure that our platforms are secured
- When do we know we are finished
    - When all apps identified have been PenTested
- When does testing have to complete to meet deadlines
    - **9/18 Official GO LIVE date** (8/30 code complete)
- How the system/app works (and how it might break)
    - FrontEnd UI talks to a BFF - which calls into RMA's APIs - that coordinates numerous other API calls
- How we gain access to it:
    - RocketPro UI: (Web / iOS / Android / APIs) - See below for URLs
- Whether anything is happening with the system/app that would affect testing (and who to talk to if it does)
    - Currently under development - so feel free to poke around - Contacts: <ac:link><ri:user ri:userkey="ff8080814906e07101491ec208670015"></ri:user></ac:link> (coordinator) / <ac:link><ri:user ri:userkey="8a890360559efb1d0155c3f7ab1e000d"></ri:user></ac:link> / <ac:link><ri:user ri:userkey="ff8080814a4b9bb3014a53763c3e000c"></ri:user></ac:link> (RocketPro: RMA / Mobile) && <ac:link><ri:user ri:userkey="8a8903605d45dfb2015d555437a60008"></ri:user></ac:link> & Tim Feather (Detroit Labs: RocketPro: ClientList / Logins / Mobile)
- How should we tell you about any issues found
    - Email of summarized issues and necessary remediation (secured)
        - OR
    - Within this Confluence page (with a link to OneDrive: "Application Scorecard" Reports)




**NOTE:** TFS Pen Testing Work Progress Tracking: "[Feature 1552971](https://tfs.rockfin.com/QL/IT/_workitems/edit/1552971): Onboarding - Penetration Testing & Logging Analysis" (This should be updated, with what has been DONE/accomplished)

## Pre-requisites For Pen-Testing:

Current URLs: [https://github.com/detroit-labs/liftoff-documentation/blob/master/AppEnvironments.md](https://github.com/detroit-labs/liftoff-documentation/blob/master/AppEnvironments.md)


| Requirement<br> | Network/System<br> | Web Application<br> | Mobile Application<br> | Control Verification<br> |
| --- | --- | --- | --- | --- |
| <br>Adequately defined **scope** of the environment to be tested:<br><ac:task-list><ac:task><br><ac:task-id>-1</ac:task-id><br><ac:task-status>incomplete</ac:task-status><br><ac:task-body><ac:task-list><br><ac:task><br><ac:task-id>21</ac:task-id><br><ac:task-status>incomplete</ac:task-status><br><ac:task-body>RocketPro <ac:link><ri:user ri:userkey="8a8903605d45dfb2015d555437a60008"></ri:user></ac:link><ac:link><ri:user ri:userkey="8a890360559efb1d0155c3f7ab1e000d"></ri:user></ac:link></ac:task-body><br></ac:task><br><ac:task><br><ac:task-id>17</ac:task-id><br><ac:task-status>incomplete</ac:task-status><br><ac:task-body>LicensePro <ac:link><ri:user ri:userkey="ff8080814906e0710149098f0e270002"></ri:user></ac:link></ac:task-body><br></ac:task><br><ac:task><br><ac:task-id>18</ac:task-id><br><ac:task-status>incomplete</ac:task-status><br><ac:task-body>RocketSignatrure <ac:link><ri:user ri:userkey="ff8080814a03762b014a1ca4b7ec0020"></ri:user></ac:link></ac:task-body><br></ac:task><br><ac:task><br><ac:task-id>24</ac:task-id><br><ac:task-status>incomplete</ac:task-status><br><ac:task-body>Auth0 <ac:link><ri:user ri:userkey="ff8080814adbc64a014af354dd2f002f"></ri:user></ac:link></ac:task-body><br></ac:task><br></ac:task-list></ac:task-body><br></ac:task><br><ac:task><br><ac:task-id>-1</ac:task-id><br><ac:task-status>incomplete</ac:task-status><br><ac:task-body><br><span style="color: rgb(94,108,132);">&quot;Front-end&quot; UI, and any back-end dependent systems, as identified by the identified architectural diagrams</span><br><br><u>Previously Pen Tested Apps:</u><br><ac:task-list><br><ac:task><br><ac:task-id>10</ac:task-id><br><ac:task-status>complete</ac:task-status><br><ac:task-body>Qualtrics</ac:task-body><br></ac:task><br><ac:task><br><ac:task-id>11</ac:task-id><br><ac:task-status>complete</ac:task-status><br><ac:task-body>RocketPro UI: Web/Mobile</ac:task-body><br></ac:task><br><ac:task><br><ac:task-id>12</ac:task-id><br><ac:task-status>complete</ac:task-status><br><ac:task-body>Bling</ac:task-body><br></ac:task><br><ac:task><br><ac:task-id>13</ac:task-id><br><ac:task-status>complete</ac:task-status><br><ac:task-body>CSA</ac:task-body><br></ac:task><br><ac:task><br><ac:task-id>14</ac:task-id><br><ac:task-status>complete</ac:task-status><br><ac:task-body>Auth0/Ping/Duo/AzureAD, Office365</ac:task-body><br></ac:task><br><ac:task><br><ac:task-id>15</ac:task-id><br><ac:task-status>complete</ac:task-status><br><ac:task-body>Workday</ac:task-body><br></ac:task><br><ac:task><br><ac:task-id>16</ac:task-id><br><ac:task-status>complete</ac:task-status><br><ac:task-body>Saba<br><br></ac:task-body><br></ac:task><br></ac:task-list></ac:task-body><br></ac:task></ac:task-list><br> | X | X | X | X |
| **Specific goals for testing defined:**<br><ul><li>Why is testing being performed?<ul><li>To determine/resolve any &quot;client facing&quot; application security vulnerabilities :<ul><li>RocketPro</li><li>LicensePro</li><li>SignatureApp</li><li>Auth0</li></ul></li></ul></li><li>Does any specific standards/regulations need to be adhered to?<ul><li>N/A</li></ul></li><li>What does the requesting group want to do with the results?<ul><li>Email results (as per usual)</li></ul></li></ul> | X | X | X | X |
| **Timing and Deadlines Defined:**(Is there a specific date that needs to be hit in order to make deadlines? Are results needed for a specific audit?)<br><ul><li><p>9/18 Go Live PROD to clients (&quot;Drop-dead&quot; date)</p></li><li><p>8/30 is &quot;Code Complete&quot; ready in PROD</p></li></ul> | <br> | <br> | <br> | <br> |
| **Rules of Engagement:**<br><ul><li>Focusing on authentication/authorization, session handling, access control, etc. - and &quot;anything more&quot; as time permits</li></ul> | X | X | X | X |
| **Testing Scenario**:<br><ul><li>Whitebox where possible</li></ul> | X | X | X |   |
| **Testing Environment Defined:**<br><br><br><br>**Web Front-End (RocketPro):**<br><ul><li>TEST:&nbsp;<a href="https://test.rocketprofessional.com/" rel="nofollow">https://test.rocketprofessional.com</a></li><li>BETA:&nbsp;<a rel="nofollow" href="https://beta.rocketprofessional.com/">https://beta.rocketprofessional.com</a></li><li>PROD:&nbsp;<a rel="nofollow" href="https://rocketprofessional.com/">https://rocketprofessional.com</a></li></ul><br><br><br>**RMA WebSite (After redirects):**<br><br>BETA: [https://frontend.np.rocketprofessional.com](https://frontend.np.rocketprofessional.com/)<br><br>PROD: [https://frontend.rocketprofessional.com](https://frontend.rocketprofessional.com/)<br><br><br><br>BETA Testing Logins: <ac:link><ri:page ri:content-title="COPYRB E2E: Rocket Pro"></ri:page></ac:link><br> | X | X | X | X |
| **Success Criteria Defined:** (When do we know that we have "done enough"?)<br><ul><li><a href="https://confluence/pages/createpage.action?spaceKey=LO&amp;title=TBD&amp;linkCreation=true&amp;fromPageId=111026424" class="createlink">TBD</a></li></ul> | X | X | X | X |
| **Environment Stability Defined:**<br><ul><li>Are changes being made during testing?</li><li>How will changes affect the overall findings, stability of testing, etc.?</li><li>How will changes affect timing or deadlines?</li><li>How will changes be communicated and delays managed?</li><li>Walk-through of Environment Differences (if Prod is not tested)</li></ul> | X | X | X | X |
| Walk-through of Application Functions, Expected Usage, Complicated Operations, etc.:<br><ul><li><a href="https://rockfin.sharepoint.com/sites/RedbirdProgram/Shared%20Documents/Rocket%20Bird/Process%20Flows/Redbird_050219_TechFlowForLegal.pdf">Overall Business/App Flow</a></li></ul> |   | X | X |   |
| Integration Points with other systems or 3rd-parties Identified and Defined:<br><ul><li><ac:link><ri:page ri:space-key="RB" ri:content-title="TBD"></ri:page><ac:plain-text-link-body><![CDATA[TBD]]></ac:plain-text-link-body></ac:link></li></ul> | ? | X | X | ? |
| Roles and Access Control Model Defined (spreadsheet matching roles to allow/denied functions)<br><ul><li><a class="createlink" href="https://confluence/pages/createpage.action?spaceKey=LO&amp;title=TBD&amp;linkCreation=true&amp;fromPageId=111026424">TBD</a></li></ul> | ? | ? | ? | ? |
| Credentials or self-registration instructions created<br><ul><li><a href="https://confluence/pages/createpage.action?spaceKey=LO&amp;title=TBD&amp;linkCreation=true&amp;fromPageId=111026424" class="createlink">TBD</a></li></ul> | ? | X | X | ? |
| **Results Format Defined:** Email summary report or Confluence (this space) (with a link to OneDrive: "Application Scorecard" Reports) | X | X | X | X |
| **Results Frequency Defined:**<br><ul><li>As Discovered &amp; Severity Based</li></ul> | X | X | X | X |
| <br>**Contact Persons Defined:**<br><br>Primary Contact/Project Manager: <ac:link><ri:user ri:userkey="ff8080814affe0b1014b5a0454560057"></ri:user></ac:link> / <ac:link><ri:user ri:userkey="ff808081492af9aa014943e74f1a0011"></ri:user></ac:link> / <ac:link><ri:user ri:userkey="ff8080814906e07101491ec208670015"></ri:user></ac:link><br><br>Technical Contacts:<br><ul><li>Overall Architect:&nbsp;<ac:link><ri:user ri:userkey="ff8080814876fe4e01488f1a926f000d"></ri:user></ac:link></li><li>Emergency Contact:&nbsp;<ac:link><ri:user ri:userkey="ff8080814adbc64a014aefa53599002b"></ri:user></ac:link> : Overall Project / Stream Leader</li></ul><br> |






* * *

## What can we test currently?

As of this point, we can test the following things fully and competently:

- Internal, External, and Cloud network infrastructure and systems, either in isolation or holistically.
- Internal, External, and Cloud web applications (commercial, open source, or internally developed)
- Coverage or proper implementation of security controls, products, or methods.


We have some ability, but not complete, to test the following:

- Commercial or Internally Developed Mobile Applications (Android coverage better than iOS but not complete)




-----------



# <u><strong>Previous Pen Test Results:</strong></u>

This is a wrap up email of the Redbird / Rocket Pro security testing. We didn’t find any critical showstoppers, but did generate some findings to resolve before this environment goes live later this year. We will plan on testing Rocket Signature, License Pro, and LiftOff when those applications are ready later in the year.



At this time we have tested the following apps/systems:

- Rocket Pro – Website (results delivered to project team)
- Rocket Pro – Android and iOS Mobile Apps (results delivered to project team)
- Azure Active Directory
- Office 365
- Workday
- Auth0
- Saba




I won’t need to re-share the results of the Rocket Pro website/mobile testing since those have been sent to the necessary people. Below is a summary of findings and security considerations for everything else.



## <u>Azure Active Directory</u>

**Findings**

- No findings with Azure AD. Initial testing with my test account ([adamsolomon@rocketprofessional.com](mailto:adamsolomon@rocketprofessional.com)) allowed me to view AD users and groups, and did not require two-factor authentication (2FA) with Duo. However, I checked today and it appears that 2FA is setup properly and that I cannot view any AD information with my limited access. My account access is presumably setup like a standard @[rocketprofessional.com](http://rocketprofessional.com) user will be setup like in the future, so I have no concerns with this.




**Security Considerations**

- Ensure that 2FA controls are setup on all accounts upon provisioning.
- Forward Azure and Duo related logs to Splunk so InfoSec can monitor activity in this environment.




## <u>Office 365</u> 

**Findings**

- No findings with Office. I wasn’t able to share stuff via OneDrive / Office with my QL account, nor did any FoC-related Azure protection policies (e.g. Keep It In the Family) allow access to my Rocket Professional account. Additionally, 2FA controls were in place just like with the Azure portal.




**Security Considerations**

- Ensure that 2FA controls are setup on all accounts upon provisioning.
- Forward Office and Duo related logs to Splunk so InfoSec can monitor activity in this environment.




## <u>Workday</u>

**Findings**

- No findings with Workday. However, it appears that Workday shares the same tenant as the FoC, which allowed me to view FoC Team Member info with my Rocket Professional account. The business should determine if this is acceptable, as a malicious user or a compromised account could access a large amount of Team Member contact information.




**Security Considerations**

- Determine what FoC-related information should be accessible to Rocket Professional users through Workday.
- Consider enabling 2FA for accounts accessing Workday.




## <u>Auth0</u>

**Findings**

- Josh Little discovered that authenticated sessions via Auth0 did not expire during the duration of our testing of the Rocket Pro mobile applications. The appropriate people have been notified of this finding and are looking in to it.




## <u>Saba</u>

**Findings**

- No findings with Saba.




**Security Considerations**

- Consider enabling 2FA for accounts accessing Saba. While the risk is not great, we should protect access to Saba in case an account has a password compromised. 2FA will greatly reduce the risk of an account takeover.




## <u>RocketPro</u>

We have completed our testing of the Rocket Professional websites and mobile applications.



I have attached two reports:

1. RocketPro Website Application Scorecard – Includes testing results from [test.rocketprofessional.com](http://test.rocketprofessional.com), including the API and front-end website.
2. RocketPro Mobile Application Scorecard – Includes testing results from the Android and iOS applications, including relevant API endpoints that the mobile applications utilize.




In our findings documents you will find a Findings tab and a Scorecard tab. The Findings represent those elements we would like you to concentrate on addressing. The Scorecard breaks the application down in to specific controls and elements. It lets you know what was tested and how the application stands up. The Scorecard includes elements that may represent upcoming standards or requirements, hence why there may be a discrepancy between elements not rated as passing and those that become findings. The Scorecard is a newer addition to our reporting methodology, so we’d appreciate any feedback you have on it.



Here are some key findings that should be addressed before the applications are launched to production. The findings documents will go in to more detail, but this is a very quick summary:

1. Authenticated login sessions on mobile applications do not get invalidated by Auth0 after any noticeable period of time. It appears that once a user is logged in to the mobile application, a user stays logged in.
2. The PHPSESSID cookie on [frontend.np.rocketprofessional.com](http://frontend.np.rocketprofessional.com) gets reused for multiple users that use the same browser session. This could allow one user account to access loans related to another user account.
3. The Resources.arsc file on the Android mobile application contains a client\_id / client\_secret pair related to a Rocket Mortgage / Rocket Professional API. This should be reviewed to ensure this poses no risk. If it does, this information will need to be removed from this file.
4. The Android mobile application logs HTTP requests from the OkHttp library to a local file on the mobile device which contains the JWT authentication tokens.


<u><br></u>
