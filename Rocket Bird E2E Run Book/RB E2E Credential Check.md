
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
| 1 | Receive API call<br> | Integrations: <ac:link><ri:user ri:userkey="8a8903604c9fa921014ca40040271afe"></ri:user></ac:link><br><br>HRIS: Meghan Hayward<br> | <br>**Integrations**: <ac:link><ri:user ri:userkey="8a8903604c9fa921014ca400343a1784"></ri:user></ac:link> <ac:link><ri:user ri:userkey="ff8080814adbc64a014ae01e847d000a"></ri:user></ac:link> <ac:link><ri:user ri:userkey="8a890360620700f90162d2b1b131003a"></ri:user></ac:link><br><br><br><br>**HRIS**: <ac:link><ri:user ri:userkey="ff8080814c4551ed014c47fbf86c0003"></ri:user></ac:link>, <ac:link><ri:user ri:userkey="8a8903606b7d57f6016b89f6438b0003"></ri:user></ac:link><br> | Input: Background check triggered to Credential Check (API call) | <br> | **COMPLETE** | Skipped actual call to CC |
| 2 | Execute background check<br> | Integrations: <ac:link><ri:user ri:userkey="8a8903604c9fa921014ca40040271afe"></ri:user></ac:link><br><br>HRIS: Meghan Hayward<br> | <br>**Integrations**: <ac:link><ri:user ri:userkey="8a8903604c9fa921014ca400343a1784"></ri:user></ac:link> <ac:link><ri:user ri:userkey="ff8080814adbc64a014ae01e847d000a"></ri:user></ac:link> <ac:link><ri:user ri:userkey="8a890360620700f90162d2b1b131003a"></ri:user></ac:link><br><br><br><br>**HRIS**: <ac:link><ri:user ri:userkey="ff8080814c4551ed014c47fbf86c0003"></ri:user></ac:link><ac:link><ri:user ri:userkey="8a8903606b7d57f6016b89f6438b0003"></ri:user></ac:link><br> | Output: Pass/Fail (API)<ul><li>If FAIL:<ul><li>Receive a pre-adverse-action action from QL (Dispute)</li><li>Execute the &quot;dispute&quot; process</li><li>Send adverse action letter (email???)</li></ul></li><li>IF PASS:<ul><li>Trigger the API call to process to move candidate forward into &quot;<a href="https://confluence/display/RB/RB+E2E%3A+WorkDay%3A+Hiring">Hiring process / Contracting</a>&quot;</li></ul></li></ul> | <br> | **COMPLETE** | Testing with 2 users to fail BGCheck |





