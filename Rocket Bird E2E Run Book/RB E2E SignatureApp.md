
## **RocketBird E2E (in BETA):**

[Rocket Professional Loan Officer (LO) Life Cycle Diagram](https://editor.signavio.com/p/hub-preview#model/ff04d56e3b8644cd880073bf5a6af3ab;diagram) (Overall)

[SignatureAPp MockUps/Wireframe Example](https://quickenloans.invisionapp.com/share/CNSXO454RH2#/screens/373379206_Redbird_-_Signature_Blank)



**Process + Things To Test/Verify:**

- Triggers into processes (prerequisites)
- What testing is being done / how / by whom
- Detailed workflow processes using what data (sequential)
- Triggers/outputs from your processes (output)





| <br> | Process Steps / Things to Ensure:<br>(Function / System)<br> | Owner/Responsibility Conn (PO)<br><br>(Primary / Secondary)<br> | SME / Testing Conn<br><br>(Primary / Secondary)<br> | Input and Output Triggers / Notifications<br> | Estimated Duration<br> | Status<br><br>(Complete / Not Started)<br> | Notes / Issues<br> |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | Either an "Email" or "Workday Task" &gt; Direct them to the Signature App | <br><ac:link><ri:user ri:userkey="ff8080814a03762b014a1ca4b7ec0020"></ri:user></ac:link><br> | <br><ac:link><ri:user ri:userkey="ff8080814a03762b014a1ca4b7ec0020"></ri:user></ac:link><br> | During OnBoarding | 5mins | **INCOMPLETE** | Note: Must a CommonID in order to use the system / Signed into their Azure account at least 1x |
| 2 | Login into Rocket Pro &gt; API call to check if signature is on file &gt; See that it fires/redirects (or link) to SignatureApp<br> | <br><ac:link><ri:user ri:userkey="ff8080814a03762b014a1ca4b7ec0020"></ri:user></ac:link><br> | <br><ac:link><ri:user ri:userkey="ff8080814a03762b014a1ca4b7ec0020"></ri:user></ac:link><br> | RocketPro login &gt; Redirects to SigApp &gt; With no signature on file (lockout-call in API call)<br><br>API checks if signature is on file:<br><ul style="list-style-type: square;"><li>FName, LName, CommonID<br><br></li><li>API Returns:<ul style="list-style-type: square;"><li>HasSignature (bool)</li><li>CreateDate (date/time)</li><li>Reason (why no signature)</li></ul></li></ul> | 5mins | **INCOMPLETE** | <br>Note: Will be available by 8/12 E2E (checks with <ac:link><ri:user ri:userkey="8a890360559efb1d0155c3f7ab1e000d"></ri:user></ac:link> )<br><br>Note: May not be ready by 7/22<br> |
| 3 | Signature App &gt; Make a new signature (brand new) &gt; Save | <br><ac:link><ri:user ri:userkey="ff8080814a03762b014a1ca4b7ec0020"></ri:user></ac:link><br> | <br><ac:link><ri:user ri:userkey="ff8080814a03762b014a1ca4b7ec0020"></ri:user></ac:link><br> | <br> | 5mins | **INCOMPLETE** | <br> |
| 4 | Signature App &gt; Make a new signature (over-write) &gt; Save | <br><ac:link><ri:user ri:userkey="ff8080814a03762b014a1ca4b7ec0020"></ri:user></ac:link><br> | <br><ac:link><ri:user ri:userkey="ff8080814a03762b014a1ca4b7ec0020"></ri:user></ac:link><br> | <br> | 5mins | **INCOMPLETE** | <br> |
| 5 | PreWork: Workday &gt; Change a LO's name | <br><ac:link><ri:user ri:userkey="ff8080814affe0b1014b5a0454560057"></ri:user></ac:link><br> | <br><ac:link><ri:user ri:userkey="ff8080814affe0b1014b5a0454560057"></ri:user></ac:link><br> | <br> | <br> | **INCOMPLETE** | <br> |
| 6 | PreWork: Sync AzureAD for the name change to take effect | <br><ac:link><ri:user ri:userkey="8a8903604c9fa921014ca3ffc39e0039"></ri:user></ac:link><br> | <br><ac:link><ri:user ri:userkey="8a8903604c9fa921014ca3ffc39e0039"></ri:user></ac:link><br> | <br> | <br> | **INCOMPLETE** | <br> |
| 7 | Name Change: Recreate signature (existing/update)<ul style="list-style-type: square;"><li>Delete original signature</li><li>Prompts to recreate</li></ul> | <br><ac:link><ri:user ri:userkey="ff8080814a03762b014a1ca4b7ec0020"></ri:user></ac:link><br> | <br><ac:link><ri:user ri:userkey="ff8080814a03762b014a1ca4b7ec0020"></ri:user></ac:link><br> | 1) Upon Login into RocketPro<br><br>2) Upon login into SignatureApp<br> | 15mins | **INCOMPLETE** | Note: Login into either RocketPro or SingatureApp - always check if a signature is needing attention (new, or recreate) |
| 8 | Signature Service:<ul style="list-style-type: square;"><li>Saves signatures to AMP:<ul style="list-style-type: square;"><li>If a signature is saved in SignatureApp - they get pulled from SigApp and pushed to AMP and DocServices folders</li></ul></li></ul> | <br><ac:link><ri:user ri:userkey="8a8903605865ecf901590770dbd9004f"></ri:user></ac:link><br> | ??? | <br> | <br> | **INCOMPLETE** | Note: May not be ready by 7/22 |







