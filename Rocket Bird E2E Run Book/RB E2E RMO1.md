
## **RocketBird E2E (in BETA):**

[Rocket Professional Loan Officer (LO) Life Cycle Diagram](https://editor.signavio.com/p/hub-preview#model/ff04d56e3b8644cd880073bf5a6af3ab;diagram) (Overall)



**Process + Things To Test/Verify:**

- Triggers into processes (prerequisites)
- What testing is being done / how / by whom
- Detailed workflow processes using what data (sequential)
- Triggers/outputs from your processes (output)





| Process Steps / Things to Ensure:<br>(Function / System)<br> | Owner/Responsibility Conn (PO)<br><br>(Primary / Secondary)<br> | SME / Testing Conn<br><br>(Primary / Secondary)<br> | Input and Output Triggers / Notifications<br> | Estimated Duration<br> | Status<br><br>(Complete / Not Started)<br> | Notes / Issues<br> |
| --- | --- | --- | --- | --- | --- | --- |
| RMO: Account Creation:<br><ul><li>Auto-generated email is sent to client (to create account)<br><ul><li>Client creates account (Rocket Mortgage)</li><li>Dashboard + same processes</li></ul></li><li>Clients need to provide SSN verification (check in the UI - once during registration)</li></ul> | <br><ac:link><ri:user ri:userkey="ff8080814756a301014769cc2b950005"></ri:user></ac:link> <ac:link><ri:user ri:userkey="ff808081489ad5100148a07c63fb000d"></ri:user></ac:link><br> | <br><ac:link><ri:user ri:userkey="8a890360559efb1d0156114401cd0033"></ri:user></ac:link><br> | Input: Once LO has solution approved from Einstein &gt; LOLA &gt; AMP &gt; RMO triggered : "Application Setup" message (quismo)<br><br>Output:<br><ul><li>Auto-generated email is sent to client (to create account)<br><ul><li>Client creates account (Rocket Mortgage)</li><li>Dashboard + same processes</li></ul></li><li>Clients need to provide SSN verification (check in the UI - once during registration)</li></ul> | 15mins | **COMPLETE** | All features already in PROD + Ready for testing esp. in BETA |
| RMO: Co-Branding : (Redbird "Phone Number" - no change - same number as "Mass Mutual" loans):<br><ul><li>&quot;Talk to Us&quot; page</li></ul> | <ac:link><ri:user ri:userkey="ff8080814756a301014769cc2b950005"></ri:user></ac:link> <ac:link><ri:user ri:userkey="ff808081489ad5100148a07c63fb000d"></ri:user></ac:link><br> | <br><ac:link><ri:user ri:userkey="ff8080814756a301014769cc2b950005"></ri:user></ac:link><br> | <br><br> | 2mins | **COMPLETE** | Verify same phone number: 800-603-1955<br> |
| RMS Needs: RMO needs to trigger a loan status to "Servicing" (Status 60) | <br><ac:link><ri:user ri:userkey="ff8080814756a301014769cc2b950005"></ri:user></ac:link> <ac:link><ri:user ri:userkey="ff808081489ad5100148a07c63fb000d"></ri:user></ac:link><br> | <br><ac:link><ri:user ri:userkey="ff8080814756a301014769cc2b950005"></ri:user></ac:link> <ac:link><ri:user ri:userkey="ff808081489ad5100148a07c63fb000d"></ri:user></ac:link><br> | Ensure that RMS picks up the loan as expected | 2mins | **COMPLETE** | <br> |
| RMO: Automation suites run | <ac:link><ri:user ri:userkey="ff8080814756a301014769cc2b950005"></ri:user></ac:link> <ac:link><ri:user ri:userkey="ff808081489ad5100148a07c63fb000d"></ri:user></ac:link> | <br><ac:link><ri:user ri:userkey="ff8080814973405c0149aaac642a004a"></ri:user></ac:link><br> | <br>Manual kickoff<br> | 10mins | **COMPLETE** | <br> |
| RMO: Manual Exploratory Testing:<br><ul><li>Navigation</li><li>Message Boards</li><li>Dashboard</li></ul> | <ac:link><ri:user ri:userkey="ff8080814756a301014769cc2b950005"></ri:user></ac:link> <ac:link><ri:user ri:userkey="ff808081489ad5100148a07c63fb000d"></ri:user></ac:link><br> | <br><ac:link><ri:user ri:userkey="ff8080814756a301014769cc2b950005"></ri:user></ac:link> <ac:link><ri:user ri:userkey="ff808081489ad5100148a07c63fb000d"></ri:user></ac:link><br> | <br><br> | 20mins | **COMPLETE** | <br> |







