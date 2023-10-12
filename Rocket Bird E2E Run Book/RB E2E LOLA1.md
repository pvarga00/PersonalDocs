
## **RocketBird E2E (in BETA):**

[Rocket Professional Loan Officer (LO) Life Cycle Diagram](https://editor.signavio.com/p/hub-preview#model/ff04d56e3b8644cd880073bf5a6af3ab;diagram) (Overall)



**Process + Things To Test/Verify:**

- Triggers into processes (prerequisites)
- What testing is being done / how / by whom
- Detailed workflow processes using what data (sequential)
- Integration Points (Other Apps/Etc.)
- Triggers/outputs from your processes (output)




# **LOLA**

**Conn:  <ac:link><ri:user ri:userkey="ff808081494f015e0149662c555a0012"></ri:user></ac:link> <ac:link><ri:user ri:userkey="8a8903605214a9180152c31e41290030"></ri:user></ac:link>**

1. Will have a QL bankers name on the lead, but will also list the influencer’s name as well for reference
2. BLING normally passes banker data to LOLA through XML, but for Redbird bankers we will exclude them from this feed. LOLA will process licensing as normal







| Process Steps / Things to Ensure:<br><br>(Function / System)<br> | Owner/Responsibility Conn (PO)<br><br>(Primary / Secondary)<br> | SME / Testing Conn<br><br>(Primary / Secondary)<br> | Input and Output Triggers / Notifications<br> | Estimated Duration<br> | Status<br><br>(Complete / Not Started)<br> | Notes / Issues<br> |
| --- | --- | --- | --- | --- | --- | --- |
| LOLA: Lead Creation: "Happy Path"<br><ul style="list-style-type: square;"><li>Lead create event: quismo/qtweet created</li><li>Verify correct data points on lead &gt; Displayed + Stored data is correct</li><li>Ensure &quot;on-line lead&quot;</li><li>Ensure &quot;Lead confirmation&quot; email does NOT fire</li></ul> | <br><ac:link><ri:user ri:userkey="8a8903605214a9180152c31e41290030"></ri:user></ac:link> / <ac:link><ri:user ri:userkey="ff808081494f015e0149662c555a0012"></ri:user></ac:link><br> | <br><ac:link><ri:user ri:userkey="8a8903605214a9180152c31e41290030"></ri:user></ac:link> / <ac:link><ri:user ri:userkey="ff808081494f015e0149662c555a0012"></ri:user></ac:link><br> | Input: LE &gt; SE &gt; Passes LOLA a lead (qtweet):<br><ul style="list-style-type: square;"><li>Influencer data: (CommonID, etc.)</li><li>Lead (qtweet)</li><li>Banker assignment (LE path / if a pitstop path: this is not assigned)</li></ul><br>Output:<br><ul style="list-style-type: square;"><li>Lead creation qtweet/quismo (to: LoanHub consumer)</li><li>Artifact exists in LOLA</li></ul> | 5mins | **COMPLETE** | Note: Need to verify that on LE leads, we did not pass lead to AMP<br><br><br><br>Dependency: Submission Engine<br><br><br><br>Note: Influencer data is not being passed / issue<br><br><br><br>Note: Issue with credit (code not pushed yet)<br> |
| LOLA: Lead Snapshot: "Happy Path"<ul style="list-style-type: square;"><li>Name change (any client data)</li><li>Address change</li><li>Credit pull</li></ul> | <br><ac:link><ri:user ri:userkey="8a8903605214a9180152c31e41290030"></ri:user></ac:link> / <ac:link><ri:user ri:userkey="ff808081494f015e0149662c555a0012"></ri:user></ac:link><br> | <br><ac:link><ri:user ri:userkey="8a8903605214a9180152c31e41290030"></ri:user></ac:link> / <ac:link><ri:user ri:userkey="ff808081494f015e0149662c555a0012"></ri:user></ac:link><br> | Input: Client data change from RocketPro or manually in LOLA<br><br>Output: Lead Snapshot qtweet &gt; LoanHub<br> | 1min | **COMPLETE** | Note: LoanHub needs to verify receipt of LeadSnapshot qtweet<br><br><br><br>Dependency: LoanHub<br> |
| LOLA: Lead Creation: "Unhappy": Pitstop<br><ul style="list-style-type: square;"><li>Update data with pitstop reason (notify a banker)</li><li>Alert in LOLA (new lead)</li><li>Assign a banker</li><li>Ensure &quot;off-line&quot; lead visibility</li><li><span>Ensure &quot;Lead confirmation&quot; email does NOT fire</span></li></ul> | <br><ac:link><ri:user ri:userkey="8a8903605214a9180152c31e41290030"></ri:user></ac:link> / <ac:link><ri:user ri:userkey="ff808081494f015e0149662c555a0012"></ri:user></ac:link><br> | <br><ac:link><ri:user ri:userkey="8a8903605214a9180152c31e41290030"></ri:user></ac:link> / <ac:link><ri:user ri:userkey="ff808081494f015e0149662c555a0012"></ri:user></ac:link><br> | Note: No banker is assigned<br><ul style="list-style-type: square;"><li>AMP Transfer XML: (All &quot;Lead data&quot;)</li><li>Influencer CommonID</li><li>&quot;Partner Data&quot; (Ex: &quot;Redbird&quot; or others)</li></ul><br>Input: Pitstop(s) : "Pitstop event" qtweet<br><br><br> | 5mins | **COMPLETE** | <br>Note: AMP transfer is no longer stopped<br><br>Pitstop: (<ac:link><ri:user ri:userkey="ff808081492af9aa014943e74f1a0011"></ri:user></ac:link> - ask about certain pitstop scenarios):<br><ul style="list-style-type: square;"><li>Hard deny</li><li>Withdrawl</li><li>Banker intervenes (to push loan forward)<ul style="list-style-type: square;"><li>Unique scenarios to &quot;auto-approve&quot;</li><li>&quot;Specialties&quot; ... Commandeered</li></ul></li></ul><br>Dependency: RocketPro & Submission Engine<br> |
| LOLA: Updates: Mortgage Experience changed event (qtweet):<br><ul style="list-style-type: square;"><li>Change loan to &quot;off-line&quot; / &quot;on-line&quot; - based on &quot;ME code&quot;</li><li>Banker can see/not see the leads</li></ul> | <br><ac:link><ri:user ri:userkey="8a8903605214a9180152c31e41290030"></ri:user></ac:link> / <ac:link><ri:user ri:userkey="ff808081494f015e0149662c555a0012"></ri:user></ac:link><br> | <br><ac:link><ri:user ri:userkey="8a8903605214a9180152c31e41290030"></ri:user></ac:link> / <ac:link><ri:user ri:userkey="ff808081494f015e0149662c555a0012"></ri:user></ac:link><br> | Input: LoanHub fires a "Mortgage Experience changed event" | 1min | **COMPLETE** | <br>Not sure how this gets generated (pitstops perhaps?) - <ac:link><ri:user ri:userkey="ff808081492af9aa014943e74f1a0011"></ri:user></ac:link> - Ask LoanHub for which triggers generate this (~40 triggers) for a 'ME changed event" qtweet<br><br><br><br>Dependency: LoanHub<br> |
| LOLA: Flip "Lead type code" (to Influencer lead)<br><br>Verify:<br><ul><li>Lead source category changed</li><li>Lead type code changed</li></ul> | <br><ac:link><ri:user ri:userkey="8a8903605214a9180152c31e41290030"></ri:user></ac:link> / <ac:link><ri:user ri:userkey="ff808081494f015e0149662c555a0012"></ri:user></ac:link><br> | <br><ac:link><ri:user ri:userkey="8a8903605214a9180152c31e41290030"></ri:user></ac:link> / <ac:link><ri:user ri:userkey="ff808081494f015e0149662c555a0012"></ri:user></ac:link><br> | Input: Manually created lead &gt; switching to an influencer lead | 1min | **COMPLETE** | <br><br> |
| LOLA: Flip "Lead type code" (away from Influencer lead)<br><br>Verify:<br><ul style="list-style-type: square;"><li>Lead source category changed</li><li>Lead type code changed</li></ul> | <br><ac:link><ri:user ri:userkey="8a8903605214a9180152c31e41290030"></ri:user></ac:link> / <ac:link><ri:user ri:userkey="ff808081494f015e0149662c555a0012"></ri:user></ac:link><br> | <br><ac:link><ri:user ri:userkey="8a8903605214a9180152c31e41290030"></ri:user></ac:link> / <ac:link><ri:user ri:userkey="ff808081494f015e0149662c555a0012"></ri:user></ac:link><br> | Input: "Specialty group" ("Schwab", etc.)<br><ul style="list-style-type: square;"><li>Pricing discounts, etc.</li></ul> | 1min | **COMPLETE** | <br> |
| LOLA: Escalations<br><br>Excluded things:<br><ul style="list-style-type: square;"><li>Global Exclusion (Influencer leads are NOT picked up by the overnight job)</li></ul> | <br><ac:link><ri:user ri:userkey="8a8903605214a9180152c31e41290030"></ri:user></ac:link> / <ac:link><ri:user ri:userkey="ff808081494f015e0149662c555a0012"></ri:user></ac:link><br> | <br><ac:link><ri:user ri:userkey="8a8903605214a9180152c31e41290030"></ri:user></ac:link> / <ac:link><ri:user ri:userkey="ff808081494f015e0149662c555a0012"></ri:user></ac:link><br> | <br> | 2mins | **COMPLETE** | <br> |
| LOLA: Appointment Confirmation:<br><ul style="list-style-type: square;"><li>Ensure &quot;Appointment Confirmation&quot; email does not fire for all Influencer leads</li></ul> | <br><ac:link><ri:user ri:userkey="8a8903605214a9180152c31e41290030"></ri:user></ac:link> / <ac:link><ri:user ri:userkey="ff808081494f015e0149662c555a0012"></ri:user></ac:link><br> | <br><ac:link><ri:user ri:userkey="8a8903605214a9180152c31e41290030"></ri:user></ac:link> / <ac:link><ri:user ri:userkey="ff808081494f015e0149662c555a0012"></ri:user></ac:link><br> | Banker manually sets an appointment on a lead | 2mins | **COMPLETE** | <br> |



