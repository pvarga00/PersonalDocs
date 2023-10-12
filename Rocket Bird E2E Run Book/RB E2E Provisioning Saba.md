
## **RocketBird E2E (in BETA):**

[Rocket Professional Loan Officer (LO) Life Cycle Diagram](https://editor.signavio.com/p/hub-preview#model/ff04d56e3b8644cd880073bf5a6af3ab;diagram) (Overall)



**Process + Things To Test/Verify**:

- Triggers into processes (prerequisites)
- What testing is being done / how / by whom
- Detailed workflow processes using what data (sequential)
- Integration Points (Other Apps/Etc.)
- Triggers/outputs from your processes (output)





| <br> | Process Steps / Things to Ensure:<br><br>(Function / System)<br> | Owner/Responsibility Conn (PO)<br><br>(Primary / Secondary)<br> | SME / Testing Conn<br><br>(Primary / Secondary)<br> | Input and Output Triggers / Notifications<br> | Estimated Duration<br> | Status<br><br>(Complete / Not Started)<br> | Notes / Issues<br> |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | LO data comes to Saba from Workday<br><ul style="list-style-type: square;"><li>Once per day: &quot;Person profile&quot; - kicks off at 3am</li></ul> | <ac:link><ri:user ri:userkey="ff8080814b6bfbc5014b846a6527000f"></ri:user></ac:link> | <br><ac:link><ri:user ri:userkey="8a8903605438810501550a90752f00ac"></ri:user></ac:link><br> | Input: LO authorized to attend training from Workday | 5mins | **COMPLETE** | <br> |
| 2 | LOs are assigned correct domain permissions:<br><ul style="list-style-type: square;"><li><span>(Admin process): Account Prefs: Which domains have access to</span></li></ul> | <ac:link><ri:user ri:userkey="ff8080814b6bfbc5014b846a6527000f"></ri:user></ac:link> | <br><ac:link><ri:user ri:userkey="8a8903605438810501550a90752f00ac"></ri:user></ac:link><br> | <br> | 5mins | **COMPLETE** | <br> |
| 3 | LOs can access their specific micro-site (and no others) | <ac:link><ri:user ri:userkey="ff8080814b6bfbc5014b846a6527000f"></ri:user></ac:link> | <br><ac:link><ri:user ri:userkey="8a8903605438810501550a90752f00ac"></ri:user></ac:link><br> | <br> | 5mins | **COMPLETE** | <br><br> |
| 4 | LOs can login to Saba, using PING & DUO | <ac:link><ri:user ri:userkey="ff8080814b6bfbc5014b846a6527000f"></ri:user></ac:link> | <br><ac:link><ri:user ri:userkey="8a8903605438810501550a90752f00ac"></ri:user></ac:link><br> | <br> | 5mins | **COMPLETE** | <br> |
| 5 | LOs can access training required (and no others) | <ac:link><ri:user ri:userkey="ff8080814b6bfbc5014b846a6527000f"></ri:user></ac:link> | <br><ac:link><ri:user ri:userkey="8a8903605438810501550a90752f00ac"></ri:user></ac:link><br> | <br> | 5mins | **COMPLETE** | <br><br> |
| 6 | If DUO is not enrolled/authorized: What happens (expected: hangs/timeouts until DUO is enrolled/authorized) | <ac:link><ri:user ri:userkey="ff8080814b6bfbc5014b846a6527000f"></ri:user></ac:link> | <br><ac:link><ri:user ri:userkey="8a8903605438810501550a90752f00ac"></ri:user></ac:link><br> | <br><br> | 5mins | **COMPLETE** | <br> |






<u><strong>Saba</strong></u>

**Conn**: <ac:link><ri:user ri:userkey="ff8080814b6bfbc5014b846a6527000f"></ri:user></ac:link>

For July release there will be a link in the RocketProfessional experience that will redirect to Saba.

In the future when the influencer logs in we will do a training check to make sure the influence has completed the required training. If not then we will lock out the loan origination features of rocketprofessional until the training is complete. This experience and integration into RocketProfessional isn’t happening to R3 and will be owned by Andrew Riley.


