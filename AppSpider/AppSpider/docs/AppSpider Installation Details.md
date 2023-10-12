
Pre-deployment guide - <ac:link><ri:attachment ri:filename="Pre-Deployment Info-ASE-1.0.pdf"></ri:attachment><ac:link-body><span class="confluence-link">Pre-Deployment Info-ASE-1.0.pdf</span> </ac:link-body></ac:link>

Download link for ASP:[https://www.rapid7.com/products/appspider/download/thank-you/](https://www.rapid7.com/products/appspider/download/thank-you/)

ASE installation guide:[https://appspider.help.rapid7.com/v1.2/docs/installing-appspider-enterprise](https://appspider.help.rapid7.com/v1.2/docs/installing-appspider-enterprise)



## Requirements for Server Info:

- **Needed Technical Reqs**: Win Server / 8GB RAM / 4 Virt CPU / 500GB HD space / IE Browser
- **Provided Virtual Machine**: QL(1/2)WEBSCAN(1/2): Win Server 2012 R2 / 20GB / 4 Virtual CPU / 170GB Free


## AppSpider Servers (PROD): 

[https://appspider.rockfin.com/AppSpiderEnterprise/Account/Login](https://appspider.rockfin.com/AppSpiderEnterprise/Account/Login "https://appspider.rockfin.com/appspiderenterprise/account/login") - F5 load balanced


| Server Name | Installed | **Reference Code** | **License Key** | Notes |
| --- | --- | --- | --- | --- |
| QL1APPSPIDER1 | AppSpider Enterprise & Pro Engine | **0869-1967-4000-0086-6616-7023**<br><br><br><br>old: 0869-1967-4000-0086-1546-7085<br> | **Enterprise: 9648-5157-5602-3140-9818-2818-4962-4292-3534-9462 4C9R-692D-C1SD-S2G1**<br><br>**Engine: 9648-5157-5602-3140-9818-2818-4962-4292-3534-9462**<br><br><br><br>*Old/Expired: 3475-6866-0517-7683-4623-1303-9971-3181-2249-5937*<br> | Main scanning server for QA and scan management + scan engine / Licensed<br><br>Service URL: [https://ql1appspider1/AppSpiderEntScanEngine/default.asmx](https://ql1appspider1/AppSpiderEntScanEngine/default.asmx)<br><br>UserName: AppSpider / Password is in SecretServer: [https://secretserver/SecretView.aspx?secretid=57915](https://secretserver/SecretView.aspx?secretid=57915)<br> |
| QL1APPSPIDER2 | Pro Engine | 0476-1240-6300-0086-4641-4295 | **4716-7977-0345-0411-2901-9181-0849-7929-3136-7654** | Additional scan engine / Licensed<br><br>Service URL: [http://QL1APPSPIDER2/AppSpiderEntScanEngine/default.asmx](http://QL1APPSPIDER2/AppSpiderEntScanEngine/default.asmx)<br><br>UserName: AppSpider / Password is in SecretServer: [https://secretserver/SecretView.aspx?secretid=57916](https://secretserver/SecretView.aspx?secretid=57916)<br> |
| QL2APPSPIDER1 | AppSpider Enterprise & Pro Engine | 0476-1240-6300-0086-3608-4280 | N/A | Not licensed - until we need to / at time of failover |
| QL2APPSPIDER2 | Pro Engine | 0476-1240-6300-0086-4203-4276 | N/A | Not licensed - until we need to / at time of failover |


***Note:** A single scan can occur per each engine, in serial, one at a time. We purchased 2 scan engines, so we can run 2 scans concurrently (across the entire enterprise / all deployment pipelines). Additional new scans launched will queue up, and dequeue automatically as in-progress scans complete.*

## PROD Database Info:

- Server: QL2SPIDRDB1
- Database: appspider-db
- Service Account: [mi\ws-appspider](https://secretserver/SecretView.aspx?secretid=24911) (Links to Secret Server credentials)


## Installation Notes:

- AppSpider Enterprise is setup on QL1APPSPIDER1. The IIS app pool is run by the mi\ws-appspider service account, which has full system admin privileges on the server. This is required to run AppSpider properly and to access the database.


**NOTE:** When launching <u>AppSpider Pro</u> - remember to launch using "**Run as Administrator**"



## AppSpider Servers (TEST):


| Server Name | Installed | **Reference Code** | **License Key** | Notes |
| --- | --- | --- | --- | --- |
| QL2APPSPIDERTEST<br> | AppSpider Enterprise & Pro Scan Engine | <br> | <br> | (QAPOW) Main scanning server for QA and scan management |
| XXX | Pro Engine | N/A | N/A | (InfoSec) AppSpider Pro Scan Engine |


## Test Database Info:

- Server: QL2APPSPIDERTEST
- Database: ql2appspidertestdb
- Service Account: [mi\ws-appspider](https://secretserver/SecretView.aspx?secretid=24911) (Links to Secret Server credentials)



