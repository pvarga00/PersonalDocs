<ac:layout><ac:layout-section ac:type="single"><ac:layout-cell><p><br></p><p><br></p><p>This space is dedicated to gathering and measuring various, informational metrics about our applications and teams.</p><p>Metrics provide the data that teams need to continuously improve and to test whether new functionality and processes have provided value.</p><p>Clients will view a web page for their application, viewing various collected metrics/information at-a-glance.</p><p>&nbsp;</p><h2>What are the metrics that teams/leaders want to see?</h2><p class="with-breadcrumbs"><strong><u>Proof-Of-Concept Target Applications</u>:</strong></p><p class="with-breadcrumbs">We are choosing to target initial POC to tracking metrics for Client Platform applications</p><ul><li class="with-breadcrumbs">MyQL Origination</li><li class="with-breadcrumbs">MyQL Servicing</li><li class="with-breadcrumbs">Rocket Mortgage</li><li class="with-breadcrumbs"><a href="http://ql.com/">QL.com</a></li><li class="with-breadcrumbs">Mobile (**stretch goal / if possible)</li></ul><p class="with-breadcrumbs"><u><br></u></p><p class="with-breadcrumbs"><strong><u><u>Proof-Of-Concept&nbsp;</u>Metrics to Gather/Track:</u></strong></p><ol><li>Application Name (and CoreID)</li><li>Application Availability / Uptime (time)</li><li>Tech Debt (time)</li><li>Test Coverage:<ol><li>Unit Test (Code) Coverage %</li><li>Integration Coverage %</li><li>Functional Coverage</li></ol></li><li><p class="p1">Test Status:</p><ol><li>Unit Tests (Total Number of Tests / Number of Failing Tests / Test Pass %)</li><li>Integration Tests (Total Number of Tests / Number of Failing Tests /&nbsp;Test Pass %)</li><li>Functional Tests (Total Number of Tests / Number of Failing Tests /&nbsp;Test Pass %)</li></ol></li><li>Change Related Incidents (CRIs)</li><li>Known Bugs/Issues (stretch goal)</li><li>Date/Time Stamp (for each run / metrics collection)</li></ol><h2><strong><br></strong></h2><h2><strong>Application Example (Name) : CoreID</strong></h2><p><strong><strong>Application Availability / Uptime (hours)&nbsp;</strong>:&nbsp;</strong>22h (99.99%) Uptime</p><p><strong>Tech Debt (days) :&nbsp;</strong>93d</p><p><strong>Current Major Incidents (Current / Month Total) :</strong>&nbsp;1 Current / 3 Month</p><p><strong>Known Bugs/Issues : </strong>24</p><p><strong>Test Status:</strong></p><table class="relative-table wrapped" style="width: 77.5357%;"><colgroup><col style="width: 18.4287%;"><col style="width: 8.24442%;"><col style="width: 10.7662%;"><col style="width: 17.5558%;"><col style="width: 13.4821%;"><col style="width: 31.5228%;"></colgroup><tbody><tr><th style="text-align: center;">Automated Test Types</th><th style="text-align: center;">Coverage</th><th style="text-align: center;">Total # Tests</th><th style="text-align: center;" colspan="1">Number of Failing Tests</th><th style="text-align: center;" colspan="1">Test Pass %</th><th colspan="1">Date / Time (Last Run)**</th></tr><tr><td style="text-align: center;">Unit</td><td style="text-align: center;">90%</td><td style="text-align: center;">25</td><td style="text-align: center;" colspan="1">1</td><td style="text-align: center;" colspan="1">96%</td><td colspan="1"><br></td></tr><tr><td style="text-align: center;" colspan="1">Integration</td><td style="text-align: center;" colspan="1">20%</td><td style="text-align: center;" colspan="1">125</td><td style="text-align: center;" colspan="1">3</td><td style="text-align: center;" colspan="1">97.6%</td><td colspan="1"><br></td></tr><tr><td style="text-align: center;" colspan="1">Functional</td><td style="text-align: center;" colspan="1">50%</td><td style="text-align: center;" colspan="1">100</td><td style="text-align: center;" colspan="1">25</td><td style="text-align: center;" colspan="1">75%</td><td colspan="1"><br></td></tr></tbody></table><p>**Note: These metrics will be tracked for each run, and viewed as historical trends showing deltas over time.</p><p>&nbsp;</p></ac:layout-cell></ac:layout-section><ac:layout-section ac:type="single"><ac:layout-cell><h1>POC Metrics Defined + Explained:</h1><p>&nbsp;</p><p><strong>Application Name&nbsp;</strong>: The name of the application or system. Also necessary, is to have CoreID - for correlating data across differing metric collections systems.</p><p>&nbsp;</p><p><strong>Application Availability / Uptime (seconds)</strong>&nbsp;:&nbsp;The percentage of time that a system is available and usable by clients.<ac:inline-comment-marker ac:ref="bc690b71-4d05-4d9a-a71f-b8f6987f0471">&nbsp;</ac:inline-comment-marker>[No client impact / application is functioning as expected]</p><p><u>Why this is important to QL:</u>&nbsp;&nbsp;<span>Availability is usually expressed as a percentage of uptime in a given year. This is measured in &quot;9s&quot; (see&nbsp;</span><a href="https://en.wikipedia.org/wiki/High_availability">&quot;High Availability&quot;</a><span>&nbsp;in Wikipedia).</span></p><table class="wrapped" style="text-align: right;"><colgroup><col><col><col><col><col></colgroup><thead><tr><th style="text-align: center;">Availability&nbsp;%</th><th style="text-align: center;">Downtime per year</th><th style="text-align: center;">Downtime per month</th><th style="text-align: center;">Downtime per week</th><th style="text-align: center;">Downtime per day</th></tr></thead><tbody><tr><td style="text-align: center;">90% (&quot;one nine&quot;)</td><td style="text-align: center;">36.5 days</td><td style="text-align: center;">72 hours</td><td style="text-align: center;">16.8 hours</td><td style="text-align: center;">2.4 hours</td></tr><tr><td style="text-align: center;">95% (&quot;one and a half nines&quot;)</td><td style="text-align: center;">18.25 days</td><td style="text-align: center;">36 hours</td><td style="text-align: center;">8.4 hours</td><td style="text-align: center;">1.2 hours</td></tr><tr><td style="text-align: center;">99% (&quot;two nines&quot;)</td><td style="text-align: center;">3.65 days</td><td style="text-align: center;">7.20 hours</td><td style="text-align: center;">1.68 hours</td><td style="text-align: center;">14.4 minutes</td></tr><tr><td style="text-align: center;">99.9% (&quot;three nines&quot;)</td><td style="text-align: center;">8.76 hours</td><td style="text-align: center;">43.8 minutes</td><td style="text-align: center;">10.1 minutes</td><td style="text-align: center;">1.44 minutes</td></tr><tr><td style="text-align: center;">99.99% (&quot;four nines&quot;)</td><td style="text-align: center;">52.56 minutes</td><td style="text-align: center;">4.38 minutes</td><td style="text-align: center;">1.01 minutes</td><td style="text-align: center;">8.64 seconds</td></tr><tr><td style="text-align: center;">99.999% (&quot;five nines&quot;)</td><td style="text-align: center;">5.26 minutes</td><td style="text-align: center;">25.9 seconds</td><td style="text-align: center;">6.05 seconds</td><td style="text-align: center;">864.3 milliseconds</td></tr><tr><td style="text-align: center;">99.9999% (&quot;six nines&quot;)</td><td style="text-align: center;">31.5 seconds</td><td style="text-align: center;">2.59 seconds</td><td style="text-align: center;">604.8 milliseconds</td><td style="text-align: center;">86.4 milliseconds</td></tr><tr><td style="text-align: center;">99.9999999% (&quot;nine nines&quot;)</td><td style="text-align: center;">31.5569 milliseconds</td><td style="text-align: center;">2.6297 milliseconds</td><td style="text-align: center;">0.6048 milliseconds</td><td style="text-align: center;">0.0864 milliseconds</td></tr></tbody></table><p><ac:inline-comment-marker ac:ref="4a773b5e-e37e-4b1c-a734-08dd0c70f098"><br></ac:inline-comment-marker></p><p>&nbsp;</p><p><strong>Tech Debt (time)</strong> : The estimated time it will take to resolve (fix) - <ac:inline-comment-marker ac:ref="eedc8e88-7fea-4109-a9ae-a51085b5e8ca">all the issues in the application's code (identified by: design decisions, deferred work, static/dynamic analysis tools, etc.)</ac:inline-comment-marker></p><p>Each issue is assigned an estimated time to resolve, (in minutes). The total time for all of the issues are added up, and then reported as the &quot;Technical Debt&quot; for an application</p><p><u>Why this is important to QL: </u>These issues are identified problems in our application code. By resolving the known problems in our code, we will have more stable, higher quality applications -- leading to less downtime, safer data, more security, and more business efficiency</p><p>&nbsp;</p><p><strong>Test Coverage&nbsp;(%)&nbsp;</strong>: Percentage of&nbsp;the source code has been covered by various tests</p><p style="margin-left: 30.0px;"><strong>Unit Test (Code) Coverage <strong>(%)</strong>&nbsp;</strong>:&nbsp;Percentage of&nbsp;the source code has been covered by unit tests&nbsp;(based on lines of code). Unit tests are code, that functionally tests application code</p><p style="margin-left: 30.0px;"><strong>Integration Coverage<strong>&nbsp;(%)</strong>&nbsp;</strong>: Percentage of&nbsp;the application integrations that have been covered by tests. Integrations are any connections and messages transferring between boundaries, from one thing&nbsp;to another. Examples are between classes, internal modules, API endpoints, other applications, vendor applications, etc.</p><p style="margin-left: 30.0px;"><strong>Functional Coverage<strong>&nbsp;(%)&nbsp;</strong></strong>:&nbsp;Percentage of&nbsp;the application's features that have been covered by tests (based on functional &quot;areas&quot; or requirements of the application)</p><p><u>Why this is important to QL:</u>&nbsp;The higher the Test Coverage, the more confidently we can release our software, with less fear that any new changes will inadvertently cause unintended failures</p><p class="p1">&nbsp;</p><p class="p1"><strong>Test Status</strong> : Summary of all test runs: unit, integration, and functional. Based on the number of passing tests, total number of tests,&nbsp;and the percentage of passing tests</p><p style="margin-left: 30.0px;"><strong>Unit Tests (Total Number of Tests / Number of Failing Tests / Test Pass %)</strong>&nbsp;: The total number of unit tests for an application, including the overall test run passing percentage</p><p style="margin-left: 30.0px;"><strong>Integration Tests (Total Number of Tests / <strong>Number of Failing Tests /&nbsp;</strong>Test Pass %)</strong>&nbsp;:&nbsp;The total number of integration tests for an application, including the overall test run passing percentage</p><p style="margin-left: 30.0px;"><strong>Functional Tests (Total Number of Tests / <strong>Number of Failing Tests /&nbsp;</strong>Test Pass %)</strong>&nbsp;:&nbsp;The total number of functional tests for an application, including the overall test run passing percentage</p><p><u>Why this is important to QL:</u>&nbsp;Our tests are critical to ensuring that the application code is working as expected. These tests also ensure that any changes to the code, do not cause unintended consequences</p><p>&nbsp;</p><p><strong>Current Change Related Incidents :</strong>&nbsp;This metric tracks the current number of problems associated with any new changes to an application</p><p><u>Why this is important to QL:</u>&nbsp;If an application is currently experiencing a &quot;change related incident&quot;, (and the historical tracking of this number over a time period, ie. a &quot;sprint cycle&quot;), allows teams to focus on and reduce the amount of change related incidents, leading towards continuous improvement, and increased uptime/availability</p><p><br></p><p>&nbsp;</p><p><strong>Known Bugs/Issues</strong>&nbsp;: <ac:inline-comment-marker ac:ref="58ac813e-c462-49e2-ba0a-e9ae3345da99">These are the known&nbsp;bugs, issues, and/or defects in the application software, identified in any environment</ac:inline-comment-marker></p><p><u>Why this is important to QL:</u>&nbsp;By resolving the known problems in our applications, we will have&nbsp;more stable,&nbsp;higher quality applications -- leading to less downtime, safer data, more security, and more business efficiency</p><p>&nbsp;</p></ac:layout-cell></ac:layout-section><ac:layout-section ac:type="single"><ac:layout-cell><p>&nbsp;</p></ac:layout-cell></ac:layout-section><ac:layout-section ac:type="single"><ac:layout-cell><h2>Metadata Information For Metrics</h2><p>Metrics are essentially a number value and a unit of measurement:</p><p>Metric = [Numeric VALUE]&nbsp;[Unit of Measure]&nbsp;</p><p>Examples: 130 seconds / 34 oz / 23 miles, etc.</p><ul><li><strong>Data Sources</strong>&nbsp;(where is the information coming from: databases, APIs, etc.)</li><li><strong>Number and Unit of Measure</strong>&nbsp;([Numeric VALUE]&nbsp;[Unit of Measure] )</li><li><strong>Metric Thresholds</strong>&nbsp;(are there any grades/levels to the number)<ul><li><span style="color: rgb(51,153,102);">Healthy</span>&nbsp;(green) /&nbsp;<span style="color: rgb(255,204,0);">Warning</span>&nbsp;(yellow) /&nbsp;<span style="color: rgb(255,0,0);">Error</span>&nbsp;(red)</li></ul></li><li><strong>Organization</strong>&nbsp;(parent/child relationships)<ul><li><p class="p1">Considering &quot;tagging&quot; parent/child and group on tags - hung on apps (need to respond to change / often)</p></li><li>Platforms/Hierarchy/Owners/Teams changes often: Applications don't change as much</li></ul></li><li><strong>Historical Trend</strong>&nbsp;(since the previous measure - spark lined)</li><li><strong>Data Polling Interval</strong>&nbsp;(how often / at what interval of time, do we want to refresh/update the data)</li><li><strong>Security / Level Of Detail</strong>&nbsp;: Customizable : Team members, Team Leaders, Platform Leaders, VP, (buckets of parent/child) - etc. - All view different roll-up, teams/views, and types of metrics<ul><li><p class="p1">Security : LOD + Least privileges + Restrict access based on AD/LDAP (consider: client secrets / groups)</p></li></ul></li></ul></ac:layout-cell></ac:layout-section></ac:layout>