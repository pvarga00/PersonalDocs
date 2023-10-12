
We have conducted load testing for the new RocketBird applications, tracking load testing results for these 3 apps (and ensure that we're ready for "GoLive" on <time datetime="2019-09-18"></time>:

- RocketPro
- LicensePro
- SignatureApp




**Summary: Based on the Load Testing Results, we are within the identified SLAs for each of the applications, and we are ready for "Go-Live" on <time datetime="2019-09-18"></time>**



<u><strong>RocketPro Load Test Results Summaries:</strong></u>

- <time datetime="2019-09-12"></time> <ac:link><ri:page ri:space-key="TI" ri:content-title="RocketPro_loginloadtest_with_sso-beta tenant"></ri:page></ac:link>

    - We performed a load test for  Rocket Pro login against sso-beta tenant with 325 test accounts and below are the results, The test went well  we did on **avg, 636  logins per minute (TPM)** ,  we had few errors but comparing to the passed transactions the error rate was also very low 0.02%
    - Total logins 39,362  , Total logout 39,301
    - #of failed transactions  39
- <time datetime="2019-08-28"></time><ac:link><ri:page ri:space-key="TI" ri:content-title="Rocket Pro UI cloud beta load test with 329 test accounts 08282019"></ri:page></ac:link>
    - In one hour test we did 27,527  successful transactions i.e. on  Avg. 458 transactions per minute ( TPM)
    - # of failed transactions  39
    - 7 failures on login , 4 on logout  and rest were on the RMA pages.
    - 19 errors were http 500 (internal server errors) , 3 was http 502 bad gateway error, 1 404 errors  and rest were  connection timeout
    - Response time for most of the transactions were under 5 seconds except for  RMA Credit/solutions page
    - In one hour test
    - Total logins 2982 , Referral leads **295** , Application **717** , credit & solutions **697** , Approval/submission **695**
- <time datetime="2019-08-22"></time><ac:link><ri:page ri:space-key="TI" ri:content-title="RocketPro UI load test with 21 concurrent users 08222019"></ri:page></ac:link>
    - In one hour test we did 6,499  successful transactions
    - Total failed transactions 12, out of which 8 failed on the RMA  pages , 1 on login , 2 logout,  1 on homepage
    - 5 errors were http 500 (internal server errors) , 1 was http 502 bad gateway error and rest were  connection timeout
    - Response time for most of the transactions were under 5 seconds except for  RMA Credit/solutions page  and  Rocket pro Login
    - In one hour test
    - Total logins 487 , Referral leads 122 , Application 362 , credit & solutions 353 , Approval/submission 352






<u><strong>RocketSignature<u><strong>&nbsp;Load Test Results Summaries</strong></u>:</strong></u>

We performed a load test for rocket signature APIs against cloud beta - and the results are analyzed. Based on the load test we were able to meet both the goals (throughput and response time).

**Run time:**20 minutes

<u>Observations:</u>

Throughput: Exceeded the expected throughput for all the 3 end points


| **Transaction Name**<br> | **Avg. TPM**<br> | **Total**<br> |
| --- | --- | --- |
| Signature status    **( SLA 1000 TPM)**<br> | 1344<br> | 27,018<br> |
| File creation           **( SLA 20 TPM)**<br> | 40<br> | 789<br> |
| Signature saving    **( SLA  50 TPM)**<br> | 96<br> | 1982<br> |




Response time: Average and 90<sup style="letter-spacing: 0.0px;">th</sup> percentile  for all the end points were under the defined SLA


| **Transaction Name**<br> | **Average (seconds)**<br> | **90 Percent (seconds)**<br> |
| Signature status   **( SLA &lt; 1 s)**<br> | 0.16<br> | 0.17<br> |
| File creation          **( SLA &lt; 5 s)**<br> | 0.23<br> | 0.38<br> |
| Signature saving   **( SLA &lt; 5 s)**<br> | 0.71<br> | 0.82<br> |




Errors: There were 1 http 404 error  , error rate 0%



<u><strong>LicensePro&nbsp;&nbsp;Load Test Results Summaries:</strong></u>

<u><strong>TBD</strong></u>
