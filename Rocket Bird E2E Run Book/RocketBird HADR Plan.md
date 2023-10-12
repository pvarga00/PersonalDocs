
This space is dedicated to tracking the Disaster Recovery / Failover information for RocketBird.



1. Determine your application tier based on name or business requirement below.<ac:task-list><ac:task>
<ac:task-id>8</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body><a href="https://rockfin.sharepoint.com/sites/BCP/SitePages/System,%20Applications%20%26%20RTOs.aspx">DEFINED SYSTEM RTOs&nbsp;</a>&nbsp;&nbsp;or&nbsp;&nbsp;<a href="https://rockfin.sharepoint.com/sites/BCP/SitePages/Business%20Processes%20and%20RTOs.aspx">BUSINESS PROCESS SUPPORTED RTO's</a><ol><li><em>(Still not sure - <a href="mailto:teamhaikili@quickenloans.com">Contact Us</a> : Team Haikili)</em></li></ol></ac:task-body>
</ac:task></ac:task-list>
2. Complete the Application DR Plan using the template below adding any information that pertains to the exercise.<ac:task-list><ac:task>
<ac:task-id>9</ac:task-id>
<ac:task-status>incomplete</ac:task-status>
<ac:task-body><a style="letter-spacing: 0.0px;" href="https://rockfin.sharepoint.com/sites/BCP/DisasterRecovery/SiteAssets/SitePages/DISASTERRECOVERY/Sample%20Application%20Disaster%20Recovery%20Plan.doc"><ac:image ac:class="ms-asset-icon ms-rtePosition-4" ac:alt="Sample Application Disaster Recovery Plan.doc"><ri:url ri:value="https://rockfin.sharepoint.com/sites/BCP/DisasterRecovery/_layouts/images/icdoc.png"></ri:url></ac:image>Sample Application Disaster Recovery Plan.doc</a></ac:task-body>
</ac:task>
<ac:task>
<ac:task-id>10</ac:task-id>
<ac:task-status>incomplete</ac:task-status>
<ac:task-body><em>LINK TO ROCKETBIRD DR PLAN&nbsp;<ac:link><ri:page ri:space-key="RB" ri:content-title="TBD"></ri:page><ac:plain-text-link-body><![CDATA[TBD]]></ac:plain-text-link-body></ac:link></em></ac:task-body>
</ac:task></ac:task-list>
3. Reach out to the DR team and coordinating a meeting with resources needed for the failover.<ac:task-list><ac:task>
<ac:task-id>11</ac:task-id>
<ac:task-status>incomplete</ac:task-status>
<ac:task-body><a style="letter-spacing: 0.0px;" href="https://rockfin.sharepoint.com/sites/BCP/DisasterRecovery/SiteAssets/SitePages/DISASTER%20RECOVERY/D.R.%20Final%20Checklist%20V.4.docx"><ac:image ac:class="ms-asset-icon ms-rtePosition-4" ac:height="16" ac:width="16"><ri:url ri:value="https://rockfin.sharepoint.com/_layouts/15/images/icdocx.png"></ri:url></ac:image>D.R. Final Checklist V.4.doc</a></ac:task-body>
</ac:task></ac:task-list>
4. The App Owner in conjunction with the DR Team should identify a test date and open a Change Ticket.<ac:task-list><ac:task>
<ac:task-id>12</ac:task-id>
<ac:task-status>incomplete</ac:task-status>
<ac:task-body><a href="https://rockfin.sharepoint.com/sites/BCP/DisasterRecovery/SiteAssets/SitePages/DISASTERRECOVERY/-Failover%20Change%20Ticket%20Guidelines%20for%20Disaster%20Recovery%20and%20Audit%20Requirements%20V2.3%20(Application%20Owners).docx"><ac:image ac:class="ms-asset-icon ms-rtePosition-4"><ri:url ri:value="https://rockfin.sharepoint.com/_layouts/15/images/icdocx.png"></ri:url></ac:image>-Failover Change Ticket Guidelines for Disaster Recovery and Audit Requirements V2.3 docx</a></ac:task-body>
</ac:task></ac:task-list>
5. Perform the DR exercise<ac:task-list><ac:task>
<ac:task-id>13</ac:task-id>
<ac:task-status>incomplete</ac:task-status>
<ac:task-body>DO IT!</ac:task-body>
</ac:task></ac:task-list>
6. After the exercise, the DR team will conduct an after-action meeting and gather an overview and ensure issues encountered are addressed. <ac:task-list><ac:task>
<ac:task-id>14</ac:task-id>
<ac:task-status>incomplete</ac:task-status>
<ac:task-body><span class="ms-rteThemeFontFace-1">Retro Meeting&nbsp;<ac:link><ri:page ri:space-key="RB" ri:content-title="TBD"></ri:page><ac:plain-text-link-body><![CDATA[TBD]]></ac:plain-text-link-body></ac:link></span></ac:task-body>
</ac:task></ac:task-list>




For Failover Testing (RocketBird): We focusing on the "new apps"

- **RocketPro**: East/West availability
    - Kyle Robertson is the System Engineer in charge of RocketPro infrastructure
    - Failover Process Documentation: <ac:link><ri:page ri:content-title="COPYRocketBird Failover Process"></ri:page></ac:link>
    - FAILOVER TESTING COMPLETED <time datetime="2019-09-12"></time>
- **SigApp**: East (Ohio) only 
    - Team hasn't worked with multi region with lambdas/SPAs before + the API effectively is destroyed after some indeterminate amount of time, and rebuilt on the next request
- **LicPro**: East only : 
    - Terraforms for UI still need to be done.  Kasey Miller is completing them, the team is stuck until it is done






**RocketBird System Dependencies:**


| **Application**<br> | Owners | **Definition**<br> | Dependencies / Owners |
| --- | --- | --- | --- |
| RocketPro | <br>Login / CLient List:<ac:link><ri:user ri:userkey="8a8903605d45dfb2015d555437a60008"></ri:user></ac:link><br><br>RocketPro Process:<ac:link><ri:user ri:userkey="8a890360559efb1d0155c3f7ab1e000d"></ri:user></ac:link><br> | Loan Origination System | <br><ul style="list-style-type: square;"><li>RMA API</li><li>AMP</li><li>LOLA</li><li>Loan Engine</li><li>Submission Engine</li><li>Loan Hub</li><li>Credit Service</li><li>AVS</li><li>Signature App</li><li>LicensePro</li><li>Saba</li><li>Workday</li><li>Auth0</li><li>AzureAD</li><li>BLING//CLOE (Licensing)</li><li>Identity Mapper Service</li></ul><br> |
| Signature App | <br><ac:link><ri:user ri:userkey="ff8080814a03762b014a1ca4b7ec0020"></ri:user></ac:link><br> | <br> | <br> |
| LicensePro | <br><ac:link><ri:user ri:userkey="ff8080814906e0710149098f0e270002"></ri:user></ac:link><br> | <br> | <br><br> |
| CSA / CLOE | <br><ac:link><ri:user ri:userkey="ff8080814adbc64a014af3428a37002e"></ri:user></ac:link> <ac:link><ri:user ri:userkey="8a8903605214a9180153423432eb0055"></ri:user></ac:link><br> | System used to track and maintain the licenses required by the company | <br> |
| BLING/Licensing | <br><ac:link><ri:user ri:userkey="ff8080814bd81a96014befc6ba6c0034"></ri:user></ac:link> <ac:link><ri:user ri:userkey="ff8080814adbc64a014adf36c5620003"></ri:user></ac:link><br> | System used to track and maintain banker's licenses | <ul><li>CSA</li><li>CLOE</li></ul> |
| Qualtrics / Smashfly | <br><ac:link><ri:user ri:userkey="8a8903604c9fa921014ca4003dff1a5d"></ri:user></ac:link><br> | Survey system used to gather Redbird agent interest info | <br> |
| Workday | <br><ac:link><ri:user ri:userkey="ff8080814affe0b1014b5a0454560057"></ri:user></ac:link> <ac:link><ri:user ri:userkey="8a8903604c9fa921014ca40040271afe"></ri:user></ac:link><br> | <br> | <ul style="list-style-type: square;"><li>Credential Check</li></ul> |
| Azure Active Directory<br> | <br><ac:link><ri:user ri:userkey="ff8080814affe0b1014b5a0454560057"></ri:user></ac:link> <ac:link><ri:user ri:userkey="8a8903604c9fa921014ca4003983191d"></ri:user></ac:link><br> | System used to identify contact information of system owners<br> | <br> |
| Outlook Exchange<br> | <br><ac:link><ri:user ri:userkey="ff8080814adbc64a014ae9c45e76001d"></ri:user></ac:link><br> | Office365: Email system used to notify loan agents to review and update documentation<br> | <br> |
| PING & DUO | <br><ac:link><ri:user ri:userkey="8a8903604c9fa921014ca4003983191d"></ri:user></ac:link><br> | <br> | <br> |
| Auth0 | <br><ac:link><ri:user ri:userkey="ff8080814adbc64a014af354dd2f002f"></ri:user></ac:link><br> | <br> | <br> |
| MIM | <br><ac:link><ri:user ri:userkey="8a8903604c9fa921014ca4003983191d"></ri:user></ac:link><br> | Microsoft Identity Manager | <br> |
| Saba | <br><ac:link><ri:user ri:userkey="ff8080814affe0b1014b5beb82b5005e"></ri:user></ac:link><br><br><ac:link><ri:user ri:userkey="8a8903605438810501550a90752f00ac"></ri:user></ac:link><br> | Training System for loan agents | <ul style="list-style-type: square;"><li>DUO</li><li>Workday</li><li>Auth0</li></ul> |
| Loan Engine | <br><ac:link><ri:user ri:userkey="ff8080814a27753d014a34de54be0019"></ri:user></ac:link><br> | <br> | <br> |
| Submission Engine | <br><ac:link><ri:user ri:userkey="ff8080814a27753d014a3053cf430012"></ri:user></ac:link><br> | <br> | <br> |
| Loan Hub | <br><ac:link><ri:user ri:userkey="ff80808149bb8a940149c33d7f350008"></ri:user></ac:link><br> | <br> | <br> |
| AMP | <br><ac:link><ri:user ri:userkey="ff8080814a03762b014a1bb944d9001d"></ri:user></ac:link><br> | <br> | <br> |
| LOLA | <br><ac:link><ri:user ri:userkey="ff808081494f015e0149662c555a0012"></ri:user></ac:link><br><br><ac:link><ri:user ri:userkey="8a8903605214a9180152c31e41290030"></ri:user></ac:link><br> | <br> | <br> |
| RMO | <br><ac:link><ri:user ri:userkey="8a8903605dec852c015fb9d520ae00ea"></ri:user></ac:link><br> | <br> | <br> |
| RMS | <br><ac:link><ri:user ri:userkey="8a89036059850d4c0159b6a77bbb0021"></ri:user></ac:link><br><br><ac:link><ri:user ri:userkey="ff8080814973405c0149a48ecab60040"></ri:user></ac:link><br> | <br> | <br> |




**Overall System Availability:**

RocketBird is being considered as a Cloud Tier 1A ("Active-Active" across East/West Availability Zones, Multi-Region data replication)

- RTO = 1 Hours (Maximum Time the system will be unavailable)
- RPO = 1 hour (Maximum Amount of Data Loss)




**RocketBird Over All Architecture Diagram:**<ac:link><ri:page ri:space-key="RB" ri:content-title="TBD"></ri:page><ac:plain-text-link-body><![CDATA[TBD]]></ac:plain-text-link-body></ac:link>





**Hardware/Infrastructure:**<ac:link><ri:page ri:space-key="RB" ri:content-title="TBD"></ri:page><ac:plain-text-link-body><![CDATA[TBD]]></ac:plain-text-link-body></ac:link>

1. *Provide a table with details (i.e. name, hw info, ip address, etc.)*
2. *Ensure all information is up to date in Cherwell and make a note of here*





| System/Server Name | Description | IP Address | URL | Resource |
| --- | --- | --- | --- | --- |
| Ex: RocketPro FE UI | Ex: East UI for Active-Active | <br> | <br> | Ex: SDKFJS DLFI- Instance-Name-East |
| <br> | <br> | <br> | <br> | <br> |
| <br> | <br> | <br> | <br> | <br> |




**Restore/Failover Process:**<ac:link><ri:page ri:space-key="RB" ri:content-title="TBD"></ri:page><ac:plain-text-link-body><![CDATA[TBD]]></ac:plain-text-link-body></ac:link>


