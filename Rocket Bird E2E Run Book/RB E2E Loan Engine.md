
## **RocketBird E2E (in BETA):**

[Rocket Professional Loan Officer (LO) Life Cycle Diagram](https://editor.signavio.com/p/hub-preview#model/ff04d56e3b8644cd880073bf5a6af3ab;diagram) (Overall)



**Process + Things To Test/Verify:**

- Triggers into processes (prerequisites)
- What testing is being done / how / by whom
- Detailed workflow processes using what data (sequential)
- Triggers/outputs from your processes (output)




**NOTE: Post Loan Numbers somewhere - allowing for downstream apps' usage**


| <br> | Process Steps / Things to Ensure:<br>(Function / System)<br> | Owner/Responsibility Conn (PO)<br><br>(Primary / Secondary)<br> | SME / Testing Conn<br><br>(Primary / Secondary)<br> | Input and Output Triggers / Notifications<br> | Estimated Duration<br> | Status<br><br>(Complete / Not Started)<br> | Notes / Issues<br> |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 1<br>9991239736 - Daffy Duck - Purchase<br><br>RMLoanId: c9afaa3d-2fb2-4ed0-8f20-87f6a1f36a95<br><br>9991239863 - Chuck Norris - Purchase<br><br>RMLoanId: d21cd800-6345-421b-b6f6-9016f01ceba3<br><br>9991239988 - Teddy Ruxpin - Purchase<br><br>RMLoanId: c44c6a9a-ae6b-4fae-9fc8-cd2ce26ffea5<br><br>9991240048 - Derpy Refi - Refinance<br><br>RMLoanId: e6b4a7ee-028f-4cdf-bded-91c00457a648<br><br>9991239962 - Sam Barber - Purchase<br><br>RMLoanId: 03fc6071-672c-42a8-8359-a9a3f88ff69c<br><br>9991240216 - Joan Jett - Refinance<br><br>RMLoanId: 6bf48197-c1e9-418a-a9ad-874f93ff7606<br> | LE: Loan Creation: Loan Number generated<br><br><br> | <br><ac:link><ri:user ri:userkey="ff8080814a27753d014a34de54be0019"></ri:user></ac:link><br> | <br><ac:link><ri:user ri:userkey="ff8080814b901f93014b98d4cf0f000b"></ri:user></ac:link><ac:link><ri:user ri:userkey="ff8080814b6bfbc5014b8363a6e4000e"></ri:user></ac:link><br><br><ac:link><ri:user ri:userkey="ff8080814a4b9bb3014acf5fa3870064"></ri:user></ac:link> <ac:link><ri:user ri:userkey="8a8903605d45dfb2015de58668960047"></ri:user></ac:link><br> | <ul><li>Input: RP after pull credit + Einstein recommended solution &gt; Send lead to LE</li><li>Output: QTweet to AMP + LOLA</li></ul> | <br> | **COMPLETE** | 1) RP Approval &gt; LE (Loan Creation) &gt; Passes to LOLA + AMP<ul><li>RP after pull credit + Einstein recommended solution &gt; Send lead to LE</li></ul><br>2) LE lets RP know the assigned<br> |
| 2 same above | LE: Loan Creation: GCID generated | <br><ac:link><ri:user ri:userkey="ff8080814a27753d014a34de54be0019"></ri:user></ac:link><br> | <br><ac:link><ri:user ri:userkey="ff8080814b901f93014b98d4cf0f000b"></ri:user></ac:link><ac:link><ri:user ri:userkey="ff8080814b6bfbc5014b8363a6e4000e"></ri:user></ac:link><br><br><ac:link><ri:user ri:userkey="ff8080814a4b9bb3014acf5fa3870064"></ri:user></ac:link> <ac:link><ri:user ri:userkey="8a8903605d45dfb2015de58668960047"></ri:user></ac:link><br> | <br> | <br> | **COMPLETE** | <br> |
| 3 same above | LE: Loan Creation: Assign Banker | <br><ac:link><ri:user ri:userkey="ff8080814a27753d014a34de54be0019"></ri:user></ac:link><br> | <br><ac:link><ri:user ri:userkey="ff8080814b901f93014b98d4cf0f000b"></ri:user></ac:link> <ac:link><ri:user ri:userkey="ff8080814b6bfbc5014b8363a6e4000e"></ri:user></ac:link><br><br><ac:link><ri:user ri:userkey="ff8080814a4b9bb3014acf5fa3870064"></ri:user></ac:link> <ac:link><ri:user ri:userkey="8a8903605d45dfb2015de58668960047"></ri:user></ac:link><br> | <br> | <br> | **COMPLETE** | <br> |
| 4 same above | LE: Loan Creation: Submit Lead Creation to AMP + Submission Engine (then to LOLA) | <br><ac:link><ri:user ri:userkey="ff8080814a27753d014a34de54be0019"></ri:user></ac:link><br> | <br><ac:link><ri:user ri:userkey="ff8080814b901f93014b98d4cf0f000b"></ri:user></ac:link> <ac:link><ri:user ri:userkey="ff8080814b6bfbc5014b8363a6e4000e"></ri:user></ac:link><br><br><ac:link><ri:user ri:userkey="ff8080814a4b9bb3014acf5fa3870064"></ri:user></ac:link> <ac:link><ri:user ri:userkey="8a8903605d45dfb2015de58668960047"></ri:user></ac:link><br> | <br> | <br> | **COMPLETE** | <br> |
| 5 same above | LE: Automated Underwriting: Run the "gatherers"<ul><li>Credit</li><li>Leo</li><li>Tax</li><li>Fees</li><li>Reggie</li><li>Einstein</li><li>Quqe V2</li><li>AVS</li><li>QM (qualified mortgage)</li></ul> | <br><ac:link><ri:user ri:userkey="ff8080814a27753d014a34de54be0019"></ri:user></ac:link><br> | <br><ac:link><ri:user ri:userkey="ff8080814b901f93014b98d4cf0f000b"></ri:user></ac:link> <ac:link><ri:user ri:userkey="ff8080814b6bfbc5014b8363a6e4000e"></ri:user></ac:link><br><br><ac:link><ri:user ri:userkey="ff8080814a4b9bb3014acf5fa3870064"></ri:user></ac:link> <ac:link><ri:user ri:userkey="8a8903605d45dfb2015de58668960047"></ri:user></ac:link><br> | Output Trigger: Return "Approved/Not Approved" to RocketPro | <br> | **COMPLETE** | Send results to AMP<br><br>NOTE: Things will just work - things should not fail<br> |
| 6<br><br>9991240216 - Joan Jett - Refinance<br><br>9991239863 - Chuck Norris - Purchase<br><br>9991240218 - Buddy Holly - Purchase<br> | LE: Automated Underwriting: Resubmits<br><ul><li>Purchase: Make sure only 1 AU resubmit can occur on an approved loan (not-rate-locked) - controlled on the RocketPro side</li></ul><ul><li>Refi: As many AUs as needed</li></ul> | <br><ac:link><ri:user ri:userkey="ff8080814a27753d014a34de54be0019"></ri:user></ac:link><br> | <br><ac:link><ri:user ri:userkey="ff8080814b901f93014b98d4cf0f000b"></ri:user></ac:link> <ac:link><ri:user ri:userkey="ff8080814b6bfbc5014b8363a6e4000e"></ri:user></ac:link><br><br><ac:link><ri:user ri:userkey="ff8080814a4b9bb3014acf5fa3870064"></ri:user></ac:link> <ac:link><ri:user ri:userkey="8a8903605d45dfb2015de58668960047"></ri:user></ac:link><br> | RP : AU requests (API call) | <br> | **COMPLETE** | RMA: Submits an AU: Automated resubmit |





