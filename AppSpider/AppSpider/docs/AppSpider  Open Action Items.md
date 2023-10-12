
## AppSpider Open Action Items:
<ac:task-list><ac:task>
<ac:task-id>573</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body>Go LIVE with new PROD:&nbsp;<ac:task-list>
<ac:task>
<ac:task-id>574</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body>Firewalls opened for new servers:&nbsp;QL1APPSPIDER1&nbsp;-&nbsp;QL1APPSPIDER2 - QL2APPSPIDER1 - QL2APPSPIDER2 - Behind the F5 - Should be opened</ac:task-body>
</ac:task>
<ac:task>
<ac:task-id>576</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body>API Gateway config changes<ac:task-list>
<ac:task>
<ac:task-id>615</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body><span style="color: rgb(0,0,0);"><span style="color: rgb(0,0,0);">Change baseuri in the Raml:&nbsp;</span></span><a title="https://git.rockfin.com/Mule/AppSpider-proxy/blob/master/src/main/resources/assets/api.raml" href="https://git.rockfin.com/Mule/AppSpider-proxy/blob/master/src/main/resources/assets/api.raml">https://git.rockfin.com/Mule/AppSpider-proxy/blob/master/src/main/resources/assets/api.raml</a></ac:task-body>
</ac:task>
<ac:task>
<ac:task-id>616</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body><span style="color: rgb(0,0,0);"><span style="color: rgb(0,0,0);">Update the implementation host in the properties file:&nbsp;</span></span><a title="https://git.rockfin.com/Mule/AppSpider-proxy/blob/master/src/main/resources/config.dev.corp.properties" href="https://git.rockfin.com/Mule/AppSpider-proxy/blob/master/src/main/resources/config.dev.corp.properties">https://git.rockfin.com/Mule/AppSpider-proxy/blob/master/src/main/resources/config.dev.corp.properties</a></ac:task-body>
</ac:task>
<ac:task>
<ac:task-id>617</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body>Make a PR for both changes and submit it to Nexus</ac:task-body>
</ac:task>
<ac:task>
<ac:task-id>666</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body>Open firewalls for the API GW / ensure working</ac:task-body>
</ac:task>
<ac:task>
<ac:task-id>667</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body>Test out our HighCost CCI pipeline</ac:task-body>
</ac:task>
</ac:task-list></ac:task-body>
</ac:task>
<ac:task>
<ac:task-id>577</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body>Update python scripts / deployment pipeline / docker images:<ac:task-list>
<ac:task>
<ac:task-id>668</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body>TFS (specialized script)</ac:task-body>
</ac:task>
<ac:task>
<ac:task-id>669</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body>CCI: DONE</ac:task-body>
</ac:task>
</ac:task-list></ac:task-body>
</ac:task>
<ac:task>
<ac:task-id>652</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body>Whitelist AppSpider in CircleCI:&nbsp;<ac:link><ri:page ri:space-key="circleci" ri:content-title="Circle CI Networking and Firewalls"></ri:page></ac:link></ac:task-body>
</ac:task>
<ac:task>
<ac:task-id>605</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body>Switch the PROD services:<br><ac:task-list>
<ac:task>
<ac:task-id>618</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body>QL1AppSpider1 &gt; Services &gt; AppSpiderScheduler2 (Need to make it automatic and start it back up again)&nbsp;</ac:task-body>
</ac:task>
<ac:task>
<ac:task-id>575</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body>Turn off current prod QL2WebScan2 service back to Manual and Stopped</ac:task-body>
</ac:task>
</ac:task-list></ac:task-body>
</ac:task>
<ac:task>
<ac:task-id>619</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body>In AppSpider: Turn off&nbsp;QL2WEBSCAN2&nbsp;+&nbsp;QL1WEBSCAN1 scan engines</ac:task-body>
</ac:task>
<ac:task>
<ac:task-id>653</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body><span>IDP Stuff:&nbsp;</span><ac:task-list>
<ac:task>
<ac:task-id>670</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body><span>Add new cert for PROD</span></ac:task-body>
</ac:task>
<ac:task>
<ac:task-id>671</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body><span>Configure samlproviders for PROD IDP:</span><ac:task-list>
<ac:task>
<ac:task-id>672</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body><p>entityID=&quot;<a>https://sso.ss.foc.zone&quot;</a></p></ac:task-body>
</ac:task>
<ac:task>
<ac:task-id>673</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body><p>Location=&quot;<a href="https://sso.ss.foc.zone/idp/SSO.saml2%22">https://sso.ss.foc.zone/idp/SSO.saml2&quot;</a></p></ac:task-body>
</ac:task>
</ac:task-list></ac:task-body>
</ac:task>
</ac:task-list></ac:task-body>
</ac:task>
<ac:task>
<ac:task-id>620</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body>Test PROD</ac:task-body>
</ac:task>
<ac:task>
<ac:task-id>674</ac:task-id>
<ac:task-status>incomplete</ac:task-status>
<ac:task-body>Relinquish licenses back to AppSpider<br><br></ac:task-body>
</ac:task>
</ac:task-list></ac:task-body>
</ac:task>
<ac:task>
<ac:task-id>578</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body>QL Security Certificate needed:&nbsp;<ac:link><ri:user ri:userkey="8a8903605438810501552988f0c700cd"></ri:user></ac:link>/&nbsp;<ac:link><ri:user ri:userkey="8a8903605438810501559acc91cc00f9"></ri:user></ac:link><ac:task-list>
<ac:task>
<ac:task-id>579</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body><p>Certs needed:</p><ul><li>like this cert: <a title="https://ql2webscan2/appspiderenterprise/" href="https://ql2webscan2/AppSpiderEnterprise/">https://ql2webscan2/AppSpiderEnterprise/</a></li><li>want to now trust: <a href="https://ql1appspider1/AppSpiderEnterprise/" title="https://ql1appspider1/appspiderenterprise/">https://ql1appspider1/AppSpiderEnterprise/</a></li></ul></ac:task-body>
</ac:task>
<ac:task>
<ac:task-id>646</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body>UPDATE: Certs are already on the F5 Pool:&nbsp;<a title="https://appspider.rockfin.com/appspiderenterprise/account/login" rel="nofollow" href="https://appspider.rockfin.com/AppSpiderEnterprise/Account/Login">https://appspider.rockfin.com/AppSpiderEnterprise/Account/Login</a>&nbsp;- not on the individual boxes</ac:task-body>
</ac:task>
</ac:task-list><span><br></span></ac:task-body>
</ac:task>
<ac:task>
<ac:task-id>621</ac:task-id>
<ac:task-status>incomplete</ac:task-status>
<ac:task-body><span>TEST Environment</span><ac:task-list>
<ac:task>
<ac:task-id>637</ac:task-id>
<ac:task-status>incomplete</ac:task-status>
<ac:task-body><span>Setup TEST Database</span></ac:task-body>
</ac:task>
<ac:task>
<ac:task-id>638</ac:task-id>
<ac:task-status>incomplete</ac:task-status>
<ac:task-body><span>Setup TEST Enterprise Portal</span></ac:task-body>
</ac:task>
<ac:task>
<ac:task-id>639</ac:task-id>
<ac:task-status>incomplete</ac:task-status>
<ac:task-body><span>Setup TEST Scan Engine(s)</span></ac:task-body>
</ac:task>
<ac:task>
<ac:task-id>640</ac:task-id>
<ac:task-status>incomplete</ac:task-status>
<ac:task-body><span>Document everything</span></ac:task-body>
</ac:task>
</ac:task-list></ac:task-body>
</ac:task></ac:task-list>

<ac:task-list><ac:task>
<ac:task-id>641</ac:task-id>
<ac:task-status>incomplete</ac:task-status>
<ac:task-body><span>Get More scan engines</span><ac:task-list>
<ac:task>
<ac:task-id>622</ac:task-id>
<ac:task-status>incomplete</ac:task-status>
<ac:task-body><span>Currently we only have 2 licensed scan engines, able to concurrently perform security scans</span></ac:task-body>
</ac:task>
</ac:task-list><span style="color: rgb(94,108,132);"><br></span></ac:task-body>
</ac:task>
<ac:task>
<ac:task-id>623</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body><span style="color: rgb(94,108,132);">SSO:</span><ac:task-list>
<ac:task>
<ac:task-id>581</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body><ac:link><ri:user ri:userkey="8a8903604c9fa921014ca4002200120a"></ri:user></ac:link><ac:link><ri:user ri:userkey="8a8903605dec852c015f398d2ff000b9"></ri:user></ac:link></ac:task-body>
</ac:task>
<ac:task>
<ac:task-id>582</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body>Configure SAML Integration:&nbsp;<ac:task-list>
<ac:task>
<ac:task-id>583</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body>C:\Program Files (x86)\Rapid 7\AppSpider Enterprise 3.8\IIS.NET\samlProviders.config</ac:task-body>
</ac:task>
</ac:task-list></ac:task-body>
</ac:task>
</ac:task-list></ac:task-body>
</ac:task></ac:task-list>
&lt;samlProviders enabled="true"&gt;

&lt;providers&gt;

&lt;provider signOnUrl="[https://SSOBeta.rockfin.com/idp/SSO.saml2](https://SSOBeta.rockfin.com/idp/SSO.saml2)" issuer="[https://SSOBeta.rockfin.com](https://SSOBeta.rockfin.com)" title="QL"&gt;

&lt;certificate findValue="AppSpider" storeLocation="LocalMachine" storeName="My" findBy="FindBySubjectName" /&gt;

&lt;providerConfiguration autoAttachToClient="Quicken Loans" autoAttachSysAdmins="" autoAttachGroups="QL Reporter" /&gt;

&lt;samlRequestParams  ID="[appspider.rapid7.com](http://appspider.rapid7.com)"  AssertionConsumerServiceURL="[https://appspider.rockfin.com/AppSpiderEnterprise/Account/SamlLogin](https://appspider.rockfin.com/AppSpiderEnterprise/Account/SamlLogin)" Issuer="[appspider.rapid7.com](http://appspider.rapid7.com)" NameIdFormat="unspecified"/&gt;

&lt;/provider&gt;

&lt;/providers&gt;

&lt;/samlProviders&gt;



<u><strong>Powershell Commands for SSO:</strong></u>

$store = New-Object System.Security.Cryptography.X509Certificates.X509Store("My", "LocalMachine”)

$store.Open("ReadOnly")

$store.Certificates.Find("FindBySubjectName", "AppSpider", "false")


<ac:task-list><ac:task>
<ac:task-id>585</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body>Email Integration</ac:task-body>
</ac:task></ac:task-list>
<ac:task-list><ac:task>
<ac:task-id>586</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body><s>Encryption of &ldquo;clear case&rdquo; config variables (NTOE)&nbsp;&mdash; NOT NEEDED</s><ac:task-list>
<ac:task>
<ac:task-id>628</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body><s><span style="color: rgb(94,108,132);">&nbsp;C:\Program Files (x86)\Rapid 7\AppSpider Enterprise 3.8\IIS.NET\bin &gt;&gt; NTOE Password Encrypter&nbsp;</span></s></ac:task-body>
</ac:task>
</ac:task-list></ac:task-body>
</ac:task>
<ac:task>
<ac:task-id>629</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body>Follow the documentation <a href="https://confluence/display/WSS/AppSpider%3A+Email+Configuration">here</a></ac:task-body>
</ac:task>
<ac:task>
<ac:task-id>630</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body>COMPLETED &amp; TESTED!!<ac:task-list>
<ac:task>
<ac:task-id>631</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body>Both QL2WebScan2 and QL1AppSpider1 config changes made (Note:&nbsp;<span style="color: rgb(66,82,110);">QL1AppSpider1 service needs to be started in order for changes to effect)</span></ac:task-body>
</ac:task>
</ac:task-list></ac:task-body>
</ac:task></ac:task-list>



<u><strong>General To Do's:</strong></u>
<ac:task-list><ac:task>
<ac:task-id>587</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body>Adding Targets (automatically from deployment pipelines &gt;&gt; API?)</ac:task-body>
</ac:task></ac:task-list>
<ac:task-list><ac:task>
<ac:task-id>588</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body>Auth/Auth: Adding Targets / Configs - for &ldquo;general team members&rdquo; &gt;&gt; But not ADMINS</ac:task-body>
</ac:task>
<ac:task>
<ac:task-id>675</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body>Added the * to &quot;Targets&quot; - which allows for automagic addition/approval of all targets</ac:task-body>
</ac:task></ac:task-list>
<ac:task-list><ac:task>
<ac:task-id>589</ac:task-id>
<ac:task-status>incomplete</ac:task-status>
<ac:task-body>Figure out who needs AppSpider outside of QL (other FOCs)</ac:task-body>
</ac:task>
<ac:task>
<ac:task-id>590</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body>How to view/kill/restart engines &ldquo;Busy&rdquo; scan engines? (Hung Processes?)</ac:task-body>
</ac:task>
<ac:task>
<ac:task-id>591</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body>Demo to team QAPOW</ac:task-body>
</ac:task>
<ac:task>
<ac:task-id>592</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body>Add Sec101 to shorty/appspiderdocs (I&rsquo;ve scanned, got some vulnerabilities &hellip; Now what? &gt;&gt; Next Steps)</ac:task-body>
</ac:task>
<ac:task>
<ac:task-id>593</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body>Bug in &ldquo;special chars&rdquo;:</ac:task-body>
</ac:task></ac:task-list>
<ac:task-list><ac:task>
<ac:task-id>594</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body><a href="https://bigbeta.rockfin.com/#/analysis">https://bigbeta.rockfin.com:443/#/analysis</a></ac:task-body>
</ac:task>
<ac:task>
<ac:task-id>595</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body><a href="https://bigbeta.rockfin.com/#/runreport/*">https://bigbeta.rockfin.com:443/#/runreport/*</a></ac:task-body>
</ac:task></ac:task-list>
<ac:task-list><ac:task>
<ac:task-id>647</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body>Fix all ADMIN logins / remove non-admins</ac:task-body>
</ac:task>
<ac:task>
<ac:task-id>648</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body>Deep scan/crawling issue - not finding deeper links - need to add each URL manually? Setting the URL/* doesn't seem to work:&nbsp;<ac:task-list>
<ac:task>
<ac:task-id>649</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body>Ex:&nbsp;<span style="color: rgb(51,51,51);">RMA_Web,&nbsp;<span style="color: rgb(51,51,51);">Rocket-Origination-Midware-NonProd,&nbsp;<span style="color: rgb(51,51,51);">LoanCreation</span></span></span></ac:task-body>
</ac:task>
</ac:task-list></ac:task-body>
</ac:task></ac:task-list>

<ac:task-list><ac:task>
<ac:task-id>655</ac:task-id>
<ac:task-status>incomplete</ac:task-status>
<ac:task-body><span>Implement a Terraform script to install AppSpider on EC2 AWS</span></ac:task-body>
</ac:task></ac:task-list>


Old/Resolved Stuff:
<ac:task-list><ac:task>
<ac:task-id>596</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body>Regular updates / upgrades &gt; Need to reinstall + reconfigure? Or is there an upgrade path? - ENGINES YES</ac:task-body>
</ac:task>
<ac:task>
<ac:task-id>597</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body>Cleaning up &ldquo;old scan results&rdquo; (only delete from &ldquo;local saves&rdquo; folder) - YES / MANUAL DELETE FROM FOLDER</ac:task-body>
</ac:task>
<ac:task>
<ac:task-id>598</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body>Scan Engines &gt; Upgrade?? (Failed to load vulnerabilities : &ldquo;Vuln Load Failed&rdquo; &amp; &ldquo;Hanged&rdquo;) :: VulerabilitySummary.xml not found. (NTOE issue?)<br><br></ac:task-body>
</ac:task></ac:task-list><ac:task-list><ac:task>
<ac:task-id>599</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body>Ask about number of concurrent scans that can be run / how to configure it appropriately&nbsp;<ac:task-list>
<ac:task>
<ac:task-id>600</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body>Automatic - Based on the number of scan engines purchased/licensed : Currently 2x&nbsp;<br><br></ac:task-body>
</ac:task>
</ac:task-list></ac:task-body>
</ac:task></ac:task-list><ac:task-list><ac:task>
<ac:task-id>601</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body>FlightPath: (With/Without Creds)<ac:task-list>
<ac:task>
<ac:task-id>602</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body><a href="http://camundadevpoc.rockfin.com/camunda/" style="letter-spacing: 0.0px;">http://camundadevpoc.rockfin.com/camunda/</a></ac:task-body>
</ac:task>
<ac:task>
<ac:task-id>603</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body>FIXED by deleting the Monitoring ON ones - and recreated new ScanConfigs with it Monitoring OFF</ac:task-body>
</ac:task>
</ac:task-list></ac:task-body>
</ac:task></ac:task-list>

