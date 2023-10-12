
## **RocketBird E2E (in BETA):**

[Rocket Professional Loan Officer (LO) Life Cycle Diagram](https://editor.signavio.com/p/hub-preview#model/ff04d56e3b8644cd880073bf5a6af3ab;diagram) (Overall)



**Process + Things To Test/Verify:**

- Triggers into processes (prerequisites)
- What testing is being done / how / by whom
- Detailed workflow processes using what data (sequential)
- Triggers/outputs from your processes (output)





| <br> | Process Steps / Things to Ensure:<br>(Function / System)<br> | Owner/Responsibility Conn (PO)<br><br>(Primary / Secondary)<br> | SME / Testing Conn<br><br>(Primary / Secondary)<br> | Input and Output Triggers / Notifications<br> | Estimated Duration<br> | Status<br><br>(Complete / Not Started)<br> | Notes / Issues<br> |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | RMS places a call to Loan Hub for data (qtweets: "partner name") - 4 qtweets triggered:<br><ul><li>Lead Snapshot (LOLA)</li><li>Loan Indicator changed event (AMP)</li><li>Lead creation event (LOLA)</li><li>Mobius Loan creation event (AMP)</li></ul> | <br><ac:link><ri:user ri:userkey="ff80808149bb8a940149c33d7f350008"></ri:user></ac:link><br> | <br><ac:link><ri:user ri:userkey="ff8080814bd81a96014bdb6268050001"></ri:user></ac:link>, <ac:link><ri:user ri:userkey="ff8080814a4b9bb3014a977ce2580041"></ri:user></ac:link>, <ac:link><ri:user ri:userkey="8a89036068ac94970168c80dcc170002"></ri:user></ac:link><br> | RMS consumes <u>partner name</u>(Lisa Boudreau) &gt; Pass it to logos for co-branding<br><ul><li>Lisa B will be testing ensure consumed qtweets are fine</li></ul> | 20mins | **COMPLETE** | Pass through typically:<br><ul><li>Need get data from LOLA/AMP</li><li>Data is persisted properly</li></ul><br>NOTE: Peter to reach out when LOLA/AMP are ready to verify the qtweets<br><ul><li>Add calendar reminders during the time slots... to be on stand-by - for verification</li></ul><br>Question: Who from Mortgage Exp. will be consuming - need to ensure - work with ErinS to figure out who to contact<br><br>Lead creation event (LOLA) &gt; Mortgage Experience : New lead type code &gt; Calcs new mortgage &gt; Posted to API<br><br>"Boomerang clients" &gt; back to a banker and back again...<br>Need testcases setup for E2E - to ensure things are working as planned... (further up the chain)<br><ul><li>Ask Daniel Bosh / Rob Costello / Karlee Pilarski</li></ul><br>Dependencies: RMS &gt; Loan Hub &gt; AMP & LOLA<br> |



