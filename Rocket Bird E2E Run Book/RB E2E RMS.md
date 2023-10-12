
## **RocketBird E2E (in BETA):**

[Rocket Professional Loan Officer (LO) Life Cycle Diagram](https://editor.signavio.com/p/hub-preview#model/ff04d56e3b8644cd880073bf5a6af3ab;diagram) (Overall)



**Process + Things To Test/Verify:**

- Triggers into processes (prerequisites)
- What testing is being done / how / by whom
- Detailed workflow processes using what data (sequential)
- Triggers/outputs from your processes (output)





| <br> | Process Steps / Things to Ensure:<br>(Function / System)<br> | Owner/Responsibility Conn (PO)<br><br>(Primary / Secondary)<br> | SME / Testing Conn<br><br>(Primary / Secondary)<br> | Input and Output Triggers / Notifications<br> | Estimated Duration<br> | Status<br><br>(Complete / Not Started)<br> | Notes / Issues<br> |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | PreWork: RMO needs to trigger a loan status to "Servicing" (Status 60) | <br><ac:link><ri:user ri:userkey="ff8080814973405c0149a48ecab60040"></ri:user></ac:link><br> | <br><ac:link><ri:user ri:userkey="ff8080814973405c0149a48ecab60040"></ri:user></ac:link><br> | RMO &gt; RMS (Status changed) | ~ | **INCOMPLETE** | <br> |
| 2 | Ensure RocketBird loans are present - and "ok" (same as existing loans)<br> | <br><ac:link><ri:user ri:userkey="ff8080814973405c0149a48ecab60040"></ri:user></ac:link><br> | <br><ac:link><ri:user ri:userkey="ff8080814973405c0149a48ecab60040"></ri:user></ac:link><br> | Input: LoanServicerEvent (qtweet)<br> | 10mins | **INCOMPLETE** | Ensure "normal boarding" |







