
InfoSec: <ac:link><ri:page ri:space-key="BMS" ri:content-title="Penetration Test Process &amp; Requirements"></ri:page><ac:plain-text-link-body><![CDATA[Penetration Test Process & Requirements]]></ac:plain-text-link-body></ac:link>

Request a Pen Test: [http://shorty/breakmystuff](http://shorty/breakmystuff)



### Sample Testing Logins : <u><strong><em><a rel="nofollow" href="https://confluence/display/PlatformArchitecture/Auth0+Auth+Architecture+and+Setup">Auth0 Auth Architecture and Setup</a></em></strong></u>

**<u>Current URLs:&nbsp;<a href="https://git.rockfin.com/LiftOff/liftoff-documentation/blob/master/AppEnvironments.md">https://git.rockfin.com/LiftOff/liftoff-documentation/blob/master/AppEnvironments.md</a></u>**

Anyone can test login to an app with the credentials below:


| User Email<br> | Password<br> | CommonID<br> |
| --- | --- | --- |
| [joeredbird@testauthjo.onmicrosoft.com](mailto:joeredbird@testauthjo.onmicrosoft.com) | SomethingReallyComplex!  | 123456 |
| lisaredbird[@testauthjo.onmicrosoft.com](mailto:joeredbird@testauthjo.onmicrosoft.com) | SomethingReallyComplex!  | 999000 |
| amyredbird[@testauthjo.onmicrosoft.com](mailto:joeredbird@testauthjo.onmicrosoft.com) | SomethingReallyComplex!  | 1005430 |
| johnredbird[@testauthjo.onmicrosoft.com](mailto:joeredbird@testauthjo.onmicrosoft.com) | SomethingReallyComplex!  | 1002460<br> |




Username: Testing$.idetdpci@[mailosaur.io](http://mailosaur.io/) (where $ is a number 2-7) – typically use: 7, 6, 5... etc. (Note: you may kick another use out / invalidate their token - if you login with the same creds)
Pass: Test1234!

## 


## **LiftOff Pen Test Info:**

- What specifically is to be tested (server names, URLs, functions, etc.)
    - All of LiftOff : "Front-end" UI (RocketPro), all back-end systems
        - Arch diagrams:
            - [Arch Diagram Links](https://confluence/display/LO/Architecture+Diagram+Links)
            - [“Unofficial” Component diagrams](https://confluence/pages/viewpage.action?pageId=125735910)
- Why we are testing it
    - To ensure QL and client information is secured
    - To ensure that our platforms are secured
- When do we know we are finished
    - When all apps identified have been PenTested
- When does testing have to complete to meet deadlines
    - N/A - Delivery date for RocketPro "powered by LiftOff" is speculative
- How the system/app works (and how it might break)
    - FrontEnd UI talks to a BFF - which calls a "human-interaction-manager" API - that coordinates numerous other API calls
- How we gain access to it:
    - RocketPro UI: (Web / iOS / Android / APIs) - See below for URLs
    - [Swaggers!](https://confluence/display/LO/Swaggers)
        - Note: For access, you’ll need the “x-api-keys” in secretserver (links are provided)
    - [LiftOff Apps](https://confluence/display/LO/LiftOff+Applications)
    - [AWS Resource List](https://confluence/display/LO/AWS+Resource+List)
- Whether anything is happening with the system/app that would affect testing (and who to talk to if it does)
    - Current in-development - so feel free to poke around - Typically every other Friday morning has a "formalized demo" of new features for the sprint (in BETA) - so that might be a good time to **not** test
- How should we tell you about any issues found
    - Email of summarized issues and necessary remediation
        - OR
    - Within this Confluence page (with a link to OneDrive: "Application Scorecard" Reports)




## Pre-requisites For Pen-Testing:


| Requirement<br> | Network/System<br> | Web Application<br> | Mobile Application<br> | Control Verification<br> |
| --- | --- | --- | --- | --- |
| Adequately defined **scope** of the environment to be tested:<br><ul style="list-style-type: square;"><li>All of LiftOff : &quot;Front-end&quot; UI (RocketPro), all back-end systems, as identified by the following architectural diagrams<br><ul><li><a href="https://confluence/display/LO/Architecture+Diagram+Links">Arch Diagram Links</a></li><li><a href="https://confluence/pages/viewpage.action?pageId=125735910">&ldquo;Unofficial&rdquo; Component diagrams</a></li></ul></li></ul> | X | X | X | X |
| Specific goals for testing defined:<br><ul style="list-style-type: square;"><li>Why is testing being performed?</li><li>Does any specific standards/regulations need to be adhered to?</li><li>What does the requesting group want to do with the results?</li></ul> | X | X | X | X |
| **Timing and Deadlines Defined:**(Is there a specific date that needs to be hit in order to make deadlines? Are results needed for a specific audit?)<br><ul style="list-style-type: square;"><li><ac:link><ri:page ri:space-key="LO" ri:content-title="TBD"></ri:page><ac:plain-text-link-body><![CDATA[TBD]]></ac:plain-text-link-body></ac:link></li></ul> | <br> | <br> | <br> | <br> |
| **Rules of Engagement:**<br><ul style="list-style-type: square;"><li><strong><ac:link><ri:page ri:space-key="LO" ri:content-title="TBD"></ri:page><ac:plain-text-link-body><![CDATA[TBD]]></ac:plain-text-link-body></ac:link></strong></li></ul> | X | X | X | X |
| **Testing Scenario**:<br><ul style="list-style-type: square;"><li>Whitebox where possible</li></ul> | X | X | X |   |
| **Testing Environment Defined:**<br><br>Lastest URLs: [https://git.rockfin.com/LiftOff/liftoff-documentation/blob/master/AppEnvironments.md](https://git.rockfin.com/LiftOff/liftoff-documentation/blob/master/AppEnvironments.md)<br><ul style="list-style-type: square;"><li>TEST: <a rel="nofollow" class="external-link" href="https://rocketprohim-test.docker.foc.zone/">https://rocketprohim-test.docker.foc.zone</a></li><li>BETA: <a class="external-link" rel="nofollow" href="https://rocketprohim-beta.docker.foc.zone/">https://rocketprohim-beta.docker.foc.zone</a></li><li>PROD: <ac:link><ri:page ri:space-key="LO" ri:content-title="TBD"></ri:page><ac:plain-text-link-body><![CDATA[TBD]]></ac:plain-text-link-body></ac:link></li></ul> | X | X | X | X |
| **Success Criteria Defined:** (When do we know that we have "done enough"?)<br><ul style="list-style-type: square;"><li><ac:link><ri:page ri:space-key="LO" ri:content-title="TBD"></ri:page><ac:plain-text-link-body><![CDATA[TBD]]></ac:plain-text-link-body></ac:link></li></ul> | X | X | X | X |
| **Environment Stability Defined:**<br><ul style="list-style-type: square;"><li>Are changes being made during testing?<ul style="list-style-type: square;"><li>Yes</li></ul></li><li>How will changes affect the overall findings, stability of testing, etc.?<ul style="list-style-type: square;"><li>Unknown / <ac:link><ri:page ri:space-key="LO" ri:content-title="TBD"></ri:page><ac:plain-text-link-body><![CDATA[TBD]]></ac:plain-text-link-body></ac:link></li></ul></li><li>How will changes affect timing or deadlines?<ul style="list-style-type: square;"><li>N/A</li></ul></li><li>How will changes be communicated and delays managed?<ul style="list-style-type: square;"><li><ac:link><ri:page ri:space-key="LO" ri:content-title="TBD"></ri:page><ac:plain-text-link-body><![CDATA[TBD]]></ac:plain-text-link-body></ac:link></li></ul></li><li><span>Walk-through of Environment Differences (if Prod is not tested)</span><span><br></span><ul style="list-style-type: square;"><li><span>N/A</span></li></ul></li></ul> | X | X | X | X |
| Walk-through of Application Functions, Expected Usage, Complicated Operations, etc.:<br><ul style="list-style-type: square;"><li><ac:link><ri:page ri:space-key="LO" ri:content-title="Influencer Experience Flow"></ri:page><ac:plain-text-link-body><![CDATA["Client Flow" (business process)]]></ac:plain-text-link-body></ac:link></li></ul> |   | X | X |   |
| Integration Points with other systems or 3rd-parties Identified and Defined:<br><ul style="list-style-type: square;"><li><ac:link><ri:page ri:space-key="LO" ri:content-title="System"></ri:page><ac:plain-text-link-body><![CDATA[System Documentation]]></ac:plain-text-link-body></ac:link></li></ul> | ? | X | X | ? |
| Roles and Access Control Model Defined (spreadsheet matching roles to allow/denied functions)<br><ul style="list-style-type: square;"><li><ac:link><ri:page ri:space-key="LO" ri:content-title="TBD"></ri:page><ac:plain-text-link-body><![CDATA[TBD]]></ac:plain-text-link-body></ac:link></li></ul> | ? | ? | ? | ? |
| Credentials or self-registration instructions created<br><ul style="list-style-type: square;"><li><ac:link><ri:page ri:space-key="LO" ri:content-title="TBD"></ri:page><ac:plain-text-link-body><![CDATA[TBD]]></ac:plain-text-link-body></ac:link></li></ul> | ? | X | X | ? |
| **Results Format Defined:** Email summary report or Confluence (this space) | X | X | X | X |
| **Results Frequency Defined:**<br><ul style="list-style-type: square;"><li>As Discovered &amp; Severity Based</li></ul> | X | X | X | X |
| <br>**Contact Persons Defined:**<br><br>Primary Contact/Project Manager: <ac:link><ri:user ri:userkey="ff8080814906e07101491ec208670015"></ri:user></ac:link> / <ac:link><ri:user ri:userkey="8a89036066fbfe6c01671408d2860003"></ri:user></ac:link><br><br>Technical Contacts:<br><ul style="list-style-type: square;"><li><span>Overall Architect: <ac:link><ri:user ri:userkey="ff8080814876fe4e01488f1a926f000d"></ri:user></ac:link> </span></li><li><span>LO Solution Architect: <ac:link><ri:user ri:userkey="8a89036066fbfe6c01671408d2860003"></ri:user></ac:link> <br class="_mce_tagged_br"></span></li><li>LO Overall: <ac:link><ri:page ri:space-key="LO" ri:content-title="Roles &amp; Responsibilities"></ri:page><ac:plain-text-link-body><![CDATA[Roles & Responsibilities]]></ac:plain-text-link-body></ac:link><ul style="list-style-type: square;"><li>Addendum: <ac:link><ri:page ri:space-key="LO" ri:content-title="Technology Org Chart"></ri:page></ac:link> (with pictures)</li></ul></li></ul><br>Emergency Contact: <ac:link><ri:user ri:userkey="ff8080814adbc64a014af3425c4f002d"></ri:user></ac:link>  : Overall Project / Stream Leader<br> |






* * *

## What can we test currently?

As of this point, we can test the following things fully and competently:

- Internal, External, and Cloud network infrastructure and systems, either in isolation or holistically.
- Internal, External, and Cloud web applications (commercial, open source, or internally developed)
- Coverage or proper implementation of security controls, products, or methods.


We have some ability, but not complete, to test the following:

- Commercial or Internally Developed Mobile Applications (Android coverage better than iOS but not complete)

