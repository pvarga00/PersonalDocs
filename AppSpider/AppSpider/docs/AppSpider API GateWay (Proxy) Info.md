
[https://services.foc.zone/appspider-proxy/](https://services.foc.zone/appspider-proxy/ "https://services.foc.zone/appspider-proxy/") needs to be able to proxy to [https://apicorp.rockfin.com/appspider-proxy](https://apicorp.rockfin.com/appspider-proxy "https://apicorp.rockfin.com/appspider-proxy")

FYI: For further installation details/info: <ac:link><ri:page ri:content-title="AppSpider Installation Details"></ri:page></ac:link>

<ac:structured-macro ac:name="gliffy" ac:schema-version="1" ac:macro-id="63a4aea6-9e88-423c-94e5-453fed8b4a1e"><ac:parameter ac:name="name">AppSpiderAPIGW</ac:parameter><ac:parameter ac:name="pagePin">4</ac:parameter></ac:structured-macro>



MuleSoft API GateWay: [AppSpider-proxy](https://git.rockfin.com/Mule/AppSpider-proxy) (GIT)

Configuration Code for the API GW:

Main Code: (Java/Spring) to build in HAL: [https://git.rockfin.com/Mule/AppSpider-proxy/blob/master/pom.xml](https://git.rockfin.com/Mule/AppSpider-proxy/blob/master/pom.xml)

[Config Code](https://git.rockfin.com/Mule/AppSpider-proxy/tree/master/src/main/resources): Note: We currently only have PROD - but change **ALL** configs, if you change the endpoints

DEV: [config.dev.corp.properties](https://git.rockfin.com/Mule/AppSpider-proxy/blob/master/src/main/resources/config.dev.corp.properties "config.dev.corp.properties")
TEST: [config.test.corp.properties](https://git.rockfin.com/Mule/AppSpider-proxy/blob/master/src/main/resources/config.test.corp.properties "config.test.corp.properties")
BETA: [config.beta.corp.properties](https://git.rockfin.com/Mule/AppSpider-proxy/blob/master/src/main/resources/config.beta.corp.properties "config.beta.corp.properties")

PROD: [config.prod.corp.properties](https://git.rockfin.com/Mule/AppSpider-proxy/blob/master/src/main/resources/config.prod.corp.properties "config.prod.corp.properties")



API Gateway (Corp/Onprem) - **Gateway s****ervers behind these F5s listen on port 8081 only : <ac:link><ri:page ri:space-key="NEX" ri:content-title="Nexus F5 &amp; Load Balancer Cheat Sheet"></ri:page><ac:plain-text-link-body><![CDATA[Nexus F5 & Load Balancer Cheat Sheet]]></ac:plain-text-link-body></ac:link>**

- <u><a title="https://apicorpdev.rockfin.com/" href="https://apicorpdev.rockfin.com/">https://apicorpdev.rockfin.com</a></u>
- [https://apicorptest.rockfin.com](https://apicorptest.rockfin.com/ "https://apicorptest.rockfin.com/")
- [https://apicorpbeta.rockfin.com](https://apicorpbeta.rockfin.com "https://apicorpbeta.rockfin.com")
- [https://apicorp.rockfin.com](https://apicorp.rockfin.com/ "https://apicorp.rockfin.com/")




HAL (To deploy API GW): "<u><strong>AppSpider proxy (GW)</strong></u>"

App Dashboard: [https://hal9000.rockfin.com/applications/917/dashboard](https://hal9000.rockfin.com/applications/917/dashboard)

[https://hal9000.rockfin.com/applications/917/pushes](https://hal9000.rockfin.com/applications/917/pushes)



CircleCI Whitelisting: <ac:link><ri:page ri:space-key="circleci" ri:content-title="Circle CI Networking and Firewalls"></ri:page></ac:link>


| Host | IPs | Notes |
| --- | --- | --- |
| services.foc.zone/appspider-proxy | <ul><li><span style="color: rgb(37,36,36);">69.221.85.131 </span></li><li><span style="color: rgb(37,36,36);">63.151.90.131</span></li></ul> | Currently does not ping: Unknown host |
| [appspider.rockfin.com](http://appspider.rockfin.com)<br> | <ul style="list-style-type: square;"><li><p class="p1"><span class="s1">10.2.17.244</span></p></li></ul> | <br> |






Mulesoft : API Gateway configuration: [http://shorty/anypoint](http://shorty/anypoint)

Navigate to "Exchange" &gt; "My Applications" (You may need to request access to the following 2 apps: [CiTool](https://anypoint.mulesoft.com/exchange/applications/260171/) and [AppSpider](https://anypoint.mulesoft.com/exchange/applications/160909/)) : Email these folks for access: [itteamnexussupport@quickenloans.com](mailto:itteamnexussupport@quickenloans.com)

<ac:image ac:thumbnail="true" ac:height="150"><ri:attachment ri:filename="MuleExchange.gif"></ri:attachment></ac:image>

CiTool: [https://anypoint.mulesoft.com/exchange/applications/260171/](https://anypoint.mulesoft.com/exchange/applications/260171/)

AppSpider: [https://anypoint.mulesoft.com/exchange/applications/160909/](https://anypoint.mulesoft.com/exchange/applications/160909/)



Example Pipeline to Test AppSpider Changes:

CircleCI: [https://circleci.foc.zone/gh/QAPOW/workflows/HighCostService](https://circleci.foc.zone/gh/QAPOW/workflows/HighCostService)

TFS: [https://tfs.rockfin.com/QL/IT/QAPOW/\_apps/hub/ms.vss-releaseManagement-web.cd-workflow-hub?definitionId=668&\_a=definition-pipeline](https://tfs.rockfin.com/QL/IT/QAPOW/_apps/hub/ms.vss-releaseManagement-web.cd-workflow-hub?definitionId=668&amp;_a=definition-pipeline)


