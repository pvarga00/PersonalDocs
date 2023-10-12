![](./images/AppSpiderLogo.png)

## AppSpider is QL's recommended tool for DAST (Dynamic Application Security Testing)
DAST is black-box security testing methodology in which an application is tested automatically. A team member using AppSpider examines their application for security vulnerabilities, while it is running (deployed). AppSpider runs multiple types of attacks and processes, and tries to hack an application just like an attacker would.

You can also add AppSpider scanning into your deployment pipeline, for automated scanning every time you make a code change or deploy your application.

### AppSpider Enterprise Console
http://shorty/appspider

### API
https://appspider.rockfin.com/AppSpiderEnterprise/rest/v1/

## AppSpider Overview
While today’s malicious attackers pursue a variety of goals, they share a preferred channel of attack—the millions of custom web, mobile, and cloud applications companies deploy to serve their customers. AppSpider dynamically assesses these applications for vulnerabilities across all modern technologies, provides tools that speed remediation, and monitors applications for changes.

AppSpider automatically finds vulnerabilities across a wide range of applications. It includes unique capabilities and integrations that enable teams to automate more of the security testing program across the entire software development lifecycle (SDLC), from creation through production.

Coverage is the first step to scanner accuracy. Scanners were originally built with a crawl and attack architecture, but crawling doesn’t work for web services and other dynamic technologies. AppSpider can still crawl traditional name=value pair formats like HTML, but it also has a Universal Translator that can interpret the new technologies being used in today’s web and mobile applications (AJAX, GWT, REST, JSON, etc.).

How AppSpider Scans work
AppSpider requires basic information about their target applications, such as the name and the base URL. AppSpider then visits the target application and performs the following actions:

- Crawls the application - The first phase of the test makes an inventory of pages, links, directories, and parameters in the application. This process is called "Crawling". AppSpider can’t test what it can’t crawl or understand. In order to understand the web front-end of the application, AppSpider conducts a comprehensive crawl (HTML, Javascript) and analyzes this information to understand expected inputs for each URL in the application.
- Records the traffic - There may be some modern technologies used in the app that AppSpider cannot crawl. In order to understand the “un-crawl-able” sections of the application like web services and REST APIs, AppSpider requires users to record the network traffic generated while using these sections of the application. This traffic can be recorded by tools like Burp, Paros, or AppSpider's Traffic Recorder. AppSpider consumes the recorded traffic and uses this information to identify variables/parameters in these faceless portions of the application.
- Translates the data - AppSpider normalizes all of the data obtained in the Crawl and Record stages into atomic web requests of a common schema called the Universal Request Object.
- Launches attacks - AppSpider analyzes each universal request object and launches over 45 different simulated attack types that penetrate the back-end systems where vulnerabilities and threats exist.

### Note: Crawling all possible pages on a real world app would involve a lot of redundancy, and be extremely time consuming. 
### For example, after crawling the id=1001 and id=1002 pages, crawling page id=1003 would produce little value. Hence, AppSpider crawls a sample of pages that provide a good representation of the website functionality.


Now that you have a high-level understanding of AppSpider, you can use it to scan your system!

### GIT Repo for the "AppSpider Scanner Script": 
https://git.rockfin.com/QAPOW/CICD-Scripts

### TFS AppSpider Example:
http://tfs/tfs/QL/IT/QAPOW/_apps/hub/ms.vss-releaseManagement-web.cd-workflow-hub?definitionId=579&_a=definition-tasks&environmentId=1534

### CircleCI AppSpider Example: 
https://git.rockfin.com/LiftOff/question-trails-content-api/blob/master/.circleci/config.yml
