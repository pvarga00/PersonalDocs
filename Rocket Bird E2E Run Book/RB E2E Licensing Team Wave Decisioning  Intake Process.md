
## **RocketBird E2E (in BETA):**

[Rocket Professional Loan Officer (LO) Life Cycle Diagram](https://editor.signavio.com/p/hub-preview#model/ff04d56e3b8644cd880073bf5a6af3ab;diagram) (Overall)

[Divide LO Candidates into Waves](https://editor.signavio.com/p/hub-preview#model/39c48e4f92254bfca93fc7bb3dd460ce;diagram)



**Process + Things To Test/Verify:**

- Triggers into processes (prerequisites)
- What testing is being done / how / by whom
- Detailed workflow processes using what data (sequential)
- Integration Points (Other Apps/Etc.)
- Triggers/outputs from your processes (output)





| <br> | Process Steps / Things to Ensure:<br><br>(Function / System)<br> | Owner/Responsibility Conn (PO)<br><br>(Primary / Secondary)<br> | SME / Testing Conn<br><br>(Primary / Secondary)<br> | Input and Output Triggers / Notifications<br> | Estimated Duration<br> | Status<br><br>(Complete / Not Started)<br> | Notes / Issues<br> |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | Ingest Qualtrics .CSV<br> | <br><ac:link><ri:user ri:userkey="8a8903604c9fa921014ca4003dff1a5d"></ri:user></ac:link><br> | <br><ac:link><ri:user ri:userkey="8a8903604c9fa921014ca4003dff1a5d"></ri:user></ac:link><br> | <ul><li>Prerequisite: Downloaded (.CSV) for candidates to process (from Qualtrics)</li></ul> | <br> | **COMPLETE** | <br> |
| 2 | Ensure RedBird ID provided corresponds to a real RedBird agent | <br><ac:link><ri:user ri:userkey="8a8903604c9fa921014ca4003dff1a5d"></ri:user></ac:link><br> | <br><ac:link><ri:user ri:userkey="8a8903604c9fa921014ca4003dff1a5d"></ri:user></ac:link><br> | <br> | <br> | **COMPLETE** | <br> |
| 3 | Sort it into LO Candidate Waves (1, 1A 1B, etc.)<br> | <br><ac:link><ri:user ri:userkey="8a8903604c9fa921014ca4003dff1a5d"></ri:user></ac:link><br> | <br><ac:link><ri:user ri:userkey="8a8903604c9fa921014ca4003dff1a5d"></ri:user></ac:link><br> | <br> | <br> | **COMPLETE** | <br> |
| 4 | Clean-up data/format (according to Workday specifications) | <br><ac:link><ri:user ri:userkey="8a8903604c9fa921014ca4003dff1a5d"></ri:user></ac:link><br> | <br><ac:link><ri:user ri:userkey="8a8903604c9fa921014ca4003dff1a5d"></ri:user></ac:link><br> | <br> | <br> | **COMPLETE** | <br> |
| 5 | Generate and ensure each waves' .CSV | <br><ac:link><ri:user ri:userkey="8a8903604c9fa921014ca4003dff1a5d"></ri:user></ac:link><br> | <br><ac:link><ri:user ri:userkey="8a8903604c9fa921014ca4003dff1a5d"></ri:user></ac:link> / Licensing Team<br><br><ac:link><ri:user ri:userkey="8a8903604c9fa921014ca400343a1784"></ri:user></ac:link> , <ac:link><ri:user ri:userkey="8a890360620700f90162d2b1b131003a"></ri:user></ac:link> , <ac:link><ri:user ri:userkey="ff8080814adbc64a014ae01e847d000a"></ri:user></ac:link><br> | <br> | <br> | **COMPLETE** | Format: <br>FName, LName, Email, Phone, Address1, Addrtess 2, City, State, Zip |
| 6 | Upload to the Workday secure FTP server for Workday ingestion (weekly?) | <br><ac:link><ri:user ri:userkey="8a8903604c9fa921014ca4003dff1a5d"></ri:user></ac:link> <ac:link><ri:user ri:userkey="ff8080814973405c0149a99a19260046"></ri:user></ac:link><br> | <br>Cantina Crew<br><br><ac:link><ri:user ri:userkey="8a8903604c9fa921014ca400343a1784"></ri:user></ac:link> , <ac:link><ri:user ri:userkey="8a890360620700f90162d2b1b131003a"></ri:user></ac:link>, <ac:link><ri:user ri:userkey="ff8080814adbc64a014ae01e847d000a"></ri:user></ac:link><br> | Clean .CSVs - sorted into specific "Waves" - and uploaded to the FTP server | <br> | **COMPLETE** | <br> |






**<u>Licensing Team: Wave Decisioning</u>**

**Conn**: <ac:link><ri:user ri:userkey="8a8903604c9fa921014ca4002aec1477"></ri:user></ac:link>

- Triggers into processes (prerequisites)
    - Prerequisite: Current WAVE (.csv) for candidates to process
- What testing is being done / how / by whom
- Detailed workflow processes using what data (sequential)
    - Banker Licensing Team &gt; Asks RedBird if the candidates are "OK" to license (RedBird ID?) - eligible for the program? (MANUAL PROCESS: Phone, Email, Etc?)
    - Kristie's team sorts data into "Waves" for upload - Cleaning up the exported .CSV
    - **Removal of Duplicated entries?? &gt;&gt; Workday to resolve based on email as primary key**
    - CSV is manually cleaned-up and sent to FTP server (.CSN is correctly formatted to be ingested by Workday)
- Triggers/outputs from your processes (output)
    - Output: Confirmed .CSV (for a particular WAVE)

