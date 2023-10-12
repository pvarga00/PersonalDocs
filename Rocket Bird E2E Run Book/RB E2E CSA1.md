
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
| 1 | Ensure LO data is pushed to CSA from Workday, nightly<br> | <br><ac:link><ri:user ri:userkey="ff8080814adbc64a014af3428a37002e"></ri:user></ac:link>, <ac:link><ri:user ri:userkey="8a8903605214a9180153423432eb0055"></ri:user></ac:link><br> | <br><ac:link><ri:user ri:userkey="ff8080814adbc64a014af3428a37002e"></ri:user></ac:link>, <ac:link><ri:user ri:userkey="8a8903605214a9180153423432eb0055"></ri:user></ac:link><br> | Input: Hired folks into Workday (flatfile: CSV/TXT) &gt; File dropped &gt; CSA Picks it up | 20mins | **COMPLETE** | CSA polls every 15mins for new file(s) |
| 2 | Ensure LO data is present in "Team Member Table"<br><ac:task-list><ac:task><br><ac:task-id>16</ac:task-id><br><ac:task-status>complete</ac:task-status><br><ac:task-body>Ensure Work Addresses come from TM record, not the building they are assigned to (from Workday)</ac:task-body><br></ac:task><br><ac:task><br><ac:task-id>17</ac:task-id><br><ac:task-status>complete</ac:task-status><br><ac:task-body>Ensure telephone numbers come over</ac:task-body><br></ac:task><br><ac:task><br><ac:task-id>18</ac:task-id><br><ac:task-status>complete</ac:task-status><br><ac:task-body>etc.</ac:task-body><br></ac:task></ac:task-list> | <br><ac:link><ri:user ri:userkey="ff8080814adbc64a014af3428a37002e"></ri:user></ac:link>, <ac:link><ri:user ri:userkey="8a8903605214a9180153423432eb0055"></ri:user></ac:link><br> | <br><ac:link><ri:user ri:userkey="ff8080814adbc64a014af3428a37002e"></ri:user></ac:link>, <ac:link><ri:user ri:userkey="8a8903605214a9180153423432eb0055"></ri:user></ac:link><br> | <br> | 40mins | **COMPLETE** | Querying CSA for data |
| 3 | <br>Team Member Table with LO data is distributed to all systems: ~150 systems:<br><ac:task-list><ac:task><br><ac:task-id>19</ac:task-id><br><ac:task-status>complete</ac:task-status><br><ac:task-body>BLING <ac:link><ri:user ri:userkey="ff8080814adbc64a014af3428a37002e"></ri:user></ac:link> / <ac:link><ri:user ri:userkey="ff8080814bd81a96014befc6ba6c0034"></ri:user></ac:link></ac:task-body><br></ac:task><br><ac:task><br><ac:task-id>20</ac:task-id><br><ac:task-status>complete</ac:task-status><br><ac:task-body>AMP - <ac:link><ri:user ri:userkey="ff808081489ad5100148cd2f52b2002c"></ri:user></ac:link> - no lower env integration</ac:task-body><br></ac:task><br><ac:task><br><ac:task-id>21</ac:task-id><br><ac:task-status>complete</ac:task-status><br><ac:task-body>LOLA - <ac:link><ri:user ri:userkey="ff8080814bd81a96014bdfdcbe59000a"></ri:user></ac:link><span> - no lower env integration - manually pushed</span></ac:task-body><br></ac:task><br><ac:task><br><ac:task-id>22</ac:task-id><br><ac:task-status>complete</ac:task-status><br><ac:task-body>RMO - <ac:link><ri:user ri:userkey="ff808081492af9aa014943e74f1a0011"></ri:user></ac:link></ac:task-body><br></ac:task></ac:task-list><br> | <br><ac:link><ri:user ri:userkey="ff8080814adbc64a014af3428a37002e"></ri:user></ac:link>, <ac:link><ri:user ri:userkey="8a8903605214a9180153423432eb0055"></ri:user></ac:link><br> | <br><ac:link><ri:user ri:userkey="ff8080814adbc64a014af3428a37002e"></ri:user></ac:link>, <ac:link><ri:user ri:userkey="8a8903605214a9180153423432eb0055"></ri:user></ac:link><br> | Team Member Table with LO data is distributed to all systems: ~150 systems<br><br>CSA sends a SSIS package to all dependent system's tables<br> | 60mins | **COMPLETE** | To propagate to all dependent systems:<br><ac:task-list><ac:task><br><ac:task-id>5</ac:task-id><br><ac:task-status>incomplete</ac:task-status><br><ac:task-body>Bling</ac:task-body><br></ac:task><br><ac:task><br><ac:task-id>6</ac:task-id><br><ac:task-status>incomplete</ac:task-status><br><ac:task-body>RMO</ac:task-body><br></ac:task><br><ac:task><br><ac:task-id>7</ac:task-id><br><ac:task-status>incomplete</ac:task-status><br><ac:task-body>Message Board</ac:task-body><br></ac:task><br><ac:task><br><ac:task-id>8</ac:task-id><br><ac:task-status>incomplete</ac:task-status><br><ac:task-body>QLMS</ac:task-body><br></ac:task></ac:task-list> |
| 4 | **Quicken Loans** (Licensing &gt; CommonID &gt; CSA &gt; Bling &gt; TM Tables) &gt; Send file to AMP BETA<br> | <br><ac:link><ri:user ri:userkey="ff8080814adbc64a014af3428a37002e"></ri:user></ac:link>, <ac:link><ri:user ri:userkey="8a8903605214a9180153423432eb0055"></ri:user></ac:link><br> | <br><ac:link><ri:user ri:userkey="ff8080814adbc64a014af3428a37002e"></ri:user></ac:link>, <ac:link><ri:user ri:userkey="8a8903605214a9180153423432eb0055"></ri:user></ac:link><br> | Output: File to AMP | ~ | **COMPLETE** | <br>Integration with BLING with proper NMLS data<br> |








<u><strong>CSA&nbsp;<strong>- Central Staging Area (ETL jobs / loading employee data)</strong></strong></u>

**Conn**: <ac:link><ri:user ri:userkey="ff8080814adbc64a014af3428a37002e"></ri:user></ac:link>, <ac:link><ri:user ri:userkey="8a8903605214a9180153423432eb0055"></ri:user></ac:link>, <ac:link><ri:user ri:userkey="ff8080814affe0b1014b5a0454560057"></ri:user></ac:link>


