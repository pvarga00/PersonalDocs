
**<u>Executive Summary / Background:</u>**

It has been noted twice now, that both available scan engines become unresponsive for long scans – for the following apps:

    - [RM-BETA](https://appspider.rockfin.com/AppSpiderEnterprise/Client/Configs/Config60/b71d8876-b2d6-4bc8-b9ea-509bb9caf4a9) (config)
    - [QL-BETA](https://appspider.rockfin.com/AppSpiderEnterprise/Client/Configs/Config60/26006594-b8f9-4921-b243-d1a1f9200546) (config)

Note: These are weekly scheduled scans - so this issue will reoccur




When this occurs, we are alerted by the community that scans are being queued up, and pipelines are halted on the security scan security gate, as AppSpider is stuck awaiting results from the above apps.



We’ve had to log into each scan engine box: QL1APPSPIDER1 and QL1APPSPIDER2 – and then launch “Task Manager” to “End Task” the “Scan Engine” task – and then everything will be good again:

- On each box, once the task is ended/killed, the “Scan Engine” task will automatically restart
- In AppSpider Enterprise: the 2 apps (RM-BETA and QL-BETA) will be tagged with “Status” of “Vuln Load Failed”
- … And any queued app scans will resume




We’ll need to:

- Discuss this situation internally (CQ) – and discuss a plan of action + document our findings/resolution
- Discuss the idea of purchasing 2 addition scan engines (Cost: ~$10k per scan engine)
- Chat with IT Team Venture (who owns both apps: [RM.com](http://RM.com) and [QL.com](http://QL.com)) about the situation

