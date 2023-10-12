# AppSpider FAQ

Original Content from here: https://appspider.help.rapid7.com/docs/common-crawling-issues

## What order does AppSpider use to scan my URLs?
Any URLs that are on the on the lower part of the crawler restrictions page will overwrite the ones that are listed higher up. You can edit your scan configuration to target what you want to scan. The URL list of the scan configuration page lists all the URLs that the scan targets. You can use the Up and Down arrows to modify the position of the URL in the list.

If there is still an issue, please create a support ticket and upload the following:

The scan configuration, named ScanName.scfg, which is generally located in MyDocuments\rapid7\Scans\ScanName.

A screen capture of the all links report with the link that has mistakenly been crawled, with highlights if possible.



## How Can I Increase Scan Speed?
In many cases, AppSpider will scan duplicate content to avoid missing anything. In some cases, this can create scans that are long. You can modify the following advanced settings can reduce scan times.

### Crawl Configuration
- MaxPerDirCrawlResults = 100
- MaxPerLinkCrawlResults = 10
- MaxPerDirChildNodes = 100
- MaxAttackFeedbackLinksCount = 10
- MaxPerFileNameCrawlResults = 100

### Attacker Configuration
- ParameterToAttackBeforeLimitingAttacks = 1
- LinksToAttackBeforLimitingAttacks = 1
- MaxSameNameParameterAttackPoints = 5
- MaxSameCookieParameterAttackPoints = 5
- MaxSameNameParameterAttackPointsPerLink = 1

## Will AppSpider test pages that are linked to from the website being tested?
No, it will not. AppSpider follows the guidelines set in the Crawl Restrictions and will not test any pages that you do not configure it to test.

## When should I deselect the "Import Cookies From Traffic?" option?
When you are importing proxy logs, you will need to leave the Import Cookies from Traffic option selected unless:

- You are using different authentication method in the web application. This typically means that you use traffic logs to increase the crawl coverage, but you perform authentication via other methods.
- The traffic log was recorded a long time, so all cookies in the log have become obsolete.

## How do I record specific sequences and execute them in the same order?
Let's say that you want to record an exact sequence of events, such as filling out the shipping page during the checkout process, and attack that sequence. You can use the Sequence option that is available in macros to record and replay events in sequential order.

The Sequence option allows you to attack the last pages within a sequence. However, if you enable this option, it can cause the scan to progress more slowly. It is advisable that you limit the scan to the macro only.

## How do I scan certain parts of a web application, but exclude others?
AppSpider has extensive capabilities to allow users to crawl certain parts of an application and not others. You can use whitelists and blacklists to control the parts of the application that you scan. This includes capabilities with wildcards and regular expressions.

## What are the limitations on scanning REST interfaces?
Here are some key things we currently support:
- Formats - We support most of the popular formats used by REST interfaces, including Classic Name=Value, XML, JSON, CSV, and GwT.
- Authentication and session management - We support HTTP_AUTH, Cookies, and OAuth. We also provide interfaces for custom solutions.
- Discovery - To understand what methods and inputs are available, you must provide recorded traffic between a client of the REST interface and the REST interface. We support Swagger Documents and URLs.

Here are a couple key limitations when performing large scale scanning:
- Authentication and session management - If you are using a scheme we currently do not support, then code must be written for each scheme.
- Discovery - Although we can automatically scan Swagger based Documents and URLs, we do not have support for RAML and API Blueprint for discovery. These technologies rely on the manual process of generating and recording traffic between the client and REST interface.

## What browsers are supported for macros?
AppSpider macros are currently only supported on Microsoft Internet Explorer and Chrome.

## What is the difference between the acme.com/* literal match and acme.com/* wildcard?
* is a wildcard but, it only works as a wildcard if the match type is wildcard, otherwise it is literal.

## What is the difference between the browser macro and recorded traffic?
The Browser Macro records user actions and can be replayed over and over. For example, if you enter "John" in a form field and hit enter, the requests are generated from these actions at runtime. Whereas recorded traffic records raw requests and the traffic is used as is unless session cookies are replaced.

Both have their advantages, except that macros have the potential of failing on each step, so the fewer steps there are, the less likely you are to run into issues. It is recommended that macros do not contain more than 10 steps. If you intend to perform longer recordings, you should use a traffic recording.

Traffic recording works well when there isn't any special functionality implemented on the website to prevent traffic replay, such as one time tokens. It is impossible to replay a request that has one time token. Flash is also not supported in macros, so if you want to test AMF traffic, you need to create traffic recording.

## What level of failed requests is a cause for concern?
5% or more is a good rule of thumb. AppSpider monitors server responsiveness and slows down or increases its speeds if it looks like AppSpider is DOSsing the site.

You can manually change AppSpider concurrent threads and delays between requests in the GUI while a scan is running to slow AppSpider down.

Sometimes, sections of a website, such as database queries, can be slower than other sections of a website which will be more CPU intensive for the server hosting the website. So AppSpider may be able to scan one section of a site with no problems, but then encounter an area of the site that is slower and causes more failed requests.

## Does AppSpider Crawl SWF/Flash Files?
Yes, AppSpider can test the client and server traffic crated by Flash. You'll need to record the traffic in the AppSpider traffic recorder or through a 3rd party tool. AppSpider supports the following formats:
- AppSec toolkit Traffic Files (*.trec)
- Burp Files (*.xml)
- Paros Files (*.txt)
- WebScarab Files (conversationlog)
- HAR (HTTP Archive) Files (*.har)
- Fiddler Files (*.saz)

You can upload a traffic file to AppSpider by going to Tools > Traffic Recorder > Add File.
