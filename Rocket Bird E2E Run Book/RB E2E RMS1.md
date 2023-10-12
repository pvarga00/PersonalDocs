
## **RocketBird E2E (in BETA):**

[Rocket Professional Loan Officer (LO) Life Cycle Diagram](https://editor.signavio.com/p/hub-preview#model/ff04d56e3b8644cd880073bf5a6af3ab;diagram) (Overall)



**Process + Things To Test/Verify:**

- Triggers into processes (prerequisites)
- What testing is being done / how / by whom
- Detailed workflow processes using what data (sequential)
- Triggers/outputs from your processes (output)





| <br> | Process Steps / Things to Ensure:<br>(Function / System)<br> | Owner/Responsibility Conn (PO)<br><br>(Primary / Secondary)<br> | SME / Testing Conn<br><br>(Primary / Secondary)<br> | Input and Output Triggers / Notifications<br> | Estimated Duration<br> | Status<br><br>(Complete / Not Started)<br> | Notes / Issues<br> |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | PreWork: RMO needs to trigger a loan status to "Servicing" (Status 60) | <br><ac:link><ri:user ri:userkey="ff8080814973405c0149a48ecab60040"></ri:user></ac:link><br> | <br><ac:link><ri:user ri:userkey="ff8080814973405c0149a48ecab60040"></ri:user></ac:link><br> | RMO &gt; RMS (Status changed) | ~ | **COMPLETE** | <br> |
| 2 | Ensure RocketBird loans are present - and "ok" (same as existing loans)<br> | <br><ac:link><ri:user ri:userkey="ff8080814973405c0149a48ecab60040"></ri:user></ac:link><br> | <br><ac:link><ri:user ri:userkey="ff8080814973405c0149a48ecab60040"></ri:user></ac:link><br> | Input: LoanServicerEvent (qtweet)<br> | 10mins | **COMPLETE** | Ensure "normal boarding" |
| 3 | BDE cycle, scheduled at 3:00 PM (usually ends ~4:30 PM)<br> | <br><ac:link><ri:user ri:userkey="ff8080814973405c0149a48ecab60040"></ri:user></ac:link><br> | <br><ac:link><ri:user ri:userkey="ff8080814973405c0149a48ecab60040"></ri:user></ac:link><br> | <br> | <br> | **COMPLETE** | <br> |
| 4 | CSA database job, scheduled at 5:00 PM, but which I believe we can have a DBE run on-demand (I don't know which BDEs have access to do this, though) | <br><ac:link><ri:user ri:userkey="ff8080814973405c0149a48ecab60040"></ri:user></ac:link><br> | <br><ac:link><ri:user ri:userkey="ff8080814973405c0149a48ecab60040"></ri:user></ac:link><br> | <br> | <br> | **COMPLETE** | <br> |
| 5 | Get the NOC to run the **BDEService** scheduled task on **BETA1MIDWARE1**<br><br>(manual kick-off)<br><br>(regularly scheduled at 8:00 PM)<br> | <br><ac:link><ri:user ri:userkey="ff8080814973405c0149a48ecab60040"></ri:user></ac:link><br> | Carter, Brian / Kassees, John / Lee Duhl<br> | (In Beta) The BDE process runs at 4pm and takes ~30 minutes (on a normal day).  The GCID job then runs at 5pm<br> | 60mins | **COMPLETE** | The NOC can run this on-demand |




<u><strong>Beta Loans ready for servicing:</strong></u>


| 3426341404 |
| 3428044650 |
| 3428093254 |
| 3428480096 |
| 3428862418 |
| 3428879466 |
| 3428904323 |







