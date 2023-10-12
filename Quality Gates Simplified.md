

| <br>Quality Gates<br> | <br>Error Thresholds<br> |
| --- | --- |
| Compile + Build process | <ul><li>No errors</li></ul> |
| Static code analysis: Code<br> | <ul><li>Added Technical Debt does not increase 20% more than last build</li><li>Cyclomatic Complexity does not increase above 25</li><li>No new &quot;Blocker&quot; or &quot;Critical&quot; issues</li></ul> |
| Static code analysis: Security (SAST)\*\* | <ul><li>No new issues/vulnerabilities</li></ul> |
| Unit Tests : Code Coverage | <br><br>| <br>Quality Standard<br> | Code Coverage % |<br>| --- | --- |<br>| Bronze | 0 - 50% |<br>| Silver | 50 - 75% |<br>| Gold | 75%+ |<br><br> |
| --- | --- |
| Code Review:<br><ul><li>Automatic assignment of Code Reviewer(s)</li><li>&nbsp;Requires branch condition(s) to be met</li></ul> | <ul><li>Major rework/refactoring is needed - No &quot;critical/high&quot;, or &quot;medium&quot; code review bugs (subject to the choice of code review tool the type of code review findings and categorization may vary)</li></ul> |
| Integration / Acceptance Tests<br> | <ul><li>Pass Rate = 100%</li><li>Feature Coverage = 100% (no automated way to measure it yet)</li></ul> |
| Security Tests\*\*:<br><ul><li>Dynamic Application Security Testing (DAST)<a class="external-link" href="https://www.whitehatsec.com/products/dynamic-application-security-testing/" rel="nofollow"></a></li><li>Penetration/Hardening/Red Teaming Testing</li></ul> | <ul><li>Critical/High vulnerabilities = 0</li><li>New Medium vulnerabilities = 0</li></ul> |
| Performance Tests:<br><ul><li>Load Testing</li><li>Stress Testing</li><li>Soak/Endurance Testing</li><li>Spike Testing</li><li>Etc.</li></ul> | <ul><li>No degradation in speed / load metrics beyond 20% thresholds, from prior baseline<br><ul><li><span style="color: rgb(0,0,0);">Number of transactions per second (#) :&nbsp;</span><span style="color: rgb(0,0,0);">10% difference vs. prior (for responses over 1s in duration)</span></li><li><span style="color: rgb(0,0,0);">Page load time (sec): T</span>ime +1s vs. prior</li><li><span style="color: rgb(0,0,0);">Failure responses (%): 1</span><span style="color: rgb(0,0,0);">% failures (denial responses: 4xx / 5xx errors)</span></li></ul></li></ul> |


***NOTE: \*\* denotes optional thresholds (for now)***
