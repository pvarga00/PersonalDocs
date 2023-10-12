
## **RocketBird E2E (in BETA): Qualtrics Survey**

[Rocket Professional Loan Officer (LO) Life Cycle Diagram](https://editor.signavio.com/p/hub-preview#model/ff04d56e3b8644cd880073bf5a6af3ab;diagram) (Overall)

[Express Interest in Rocket Professional Program](https://editor.signavio.com/p/hub-preview#model/49b8e99c20ba48c4ad5c59ee1dd8679d;diagram)



**Process + Things To Test/Verify:**

- Triggers into processes (prerequisites)
- What testing is being done / how / by whom
- Detailed workflow processes using what data (sequential)
- Integration Points (Other Apps/Etc.)
- Triggers/outputs from your processes (output)





| <br> | Process Steps / Things to Ensure:<br><br>(Function / System)<br> | Owner/Responsibility Conn (PO)<br><br>(Primary / Secondary)<br> | SME / Testing Conn<br><br>(Primary / Secondary)<br> | Input & Output Triggers / Notifications<br> | Estimated Duration<br> | Status<br><br>(Complete / Not Started)<br> | Notes / Issues<br> |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | <s>Notify Redbird Agents of Rocket Professional Program:</s><br><ac:task-list><ac:task><br><ac:task-id>2</ac:task-id><br><ac:task-status>complete</ac:task-status><br><ac:task-body><s><span>RedBird Email - Sent out to RedBird agents</span></s></ac:task-body><br></ac:task></ac:task-list> | RedBird | <br><ac:link><ri:user ri:userkey="8a8903604c9fa921014ca4003dff1a5d"></ri:user></ac:link><br> | RedBird Email | ~ | **COMPLETE** | Completed 7/18/2019 |
| 2 | Receive notification of RocketPro Program<br> | RedBird | <br><ac:link><ri:user ri:userkey="8a8903604c9fa921014ca4003dff1a5d"></ri:user></ac:link><br> | <br> | ~ | **COMPLETE** | <br> |
| 3 | Fill out Qualtrics survey | <br><ac:link><ri:user ri:userkey="8a8903604c9fa921014ca4003dff1a5d"></ri:user></ac:link><br> | <br><ac:link><ri:user ri:userkey="8a8903604c9fa921014ca4003dff1a5d"></ri:user></ac:link><br> | Email sent out to RedBird LOs to fill out Qualtrics survey<br> | 5mins x #accounts needed | **COMPLETE** | <ul style="list-style-type: square;"><li><a href="https://quicken.co1.qualtrics.com/jfe/form/SV_2gB7Y1TNa5YnKzH">https://quicken.co1.qualtrics.com/jfe/form/SV_2gB7Y1TNa5YnKzH</a></li></ul><br>**Live (PROD):** [https://www.myrocketcareer.com/Rocket-Professional#qualtrics](https://www.myrocketcareer.com/Rocket-Professional#qualtrics)<br> |
| 4 | LOs enter their data into Qualtrics<br> | <br><ac:link><ri:user ri:userkey="8a8903604c9fa921014ca4003dff1a5d"></ri:user></ac:link><br> | <br><ac:link><ri:user ri:userkey="8a8903604c9fa921014ca4003dff1a5d"></ri:user></ac:link><br> | <br> | 30mins | **COMPLETE** | Format: <br>FName, LName, Email, Phone, Address1, Addrtess 2, City, State, Zip |
| 5 | Qualtrics can be filled out correctly, saved, and exported -&gt; and info sent to Licensing Team (.CSV) | <br><ac:link><ri:user ri:userkey="8a8903604c9fa921014ca4003dff1a5d"></ri:user></ac:link><br> | <br><ac:link><ri:user ri:userkey="8a8903604c9fa921014ca4003dff1a5d"></ri:user></ac:link><br> | Qualtrics .CSV | 10mins | **COMPLETE** | <br> |
| 6 | Qualtrics data is exported (nightly/weekly?) into a .CSV to a secured location<br> | <br><ac:link><ri:user ri:userkey="8a8903604c9fa921014ca4003dff1a5d"></ri:user></ac:link><br> | <br><ac:link><ri:user ri:userkey="8a8903604c9fa921014ca4003dff1a5d"></ri:user></ac:link><br> | Compiled Qualtrics .CSV | ~ | **COMPLETE** | Note: Working with the PROD data .XLS : ~660 agents, and we're updating/parsing the data |







