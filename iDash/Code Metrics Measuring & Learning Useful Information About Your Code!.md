
<s>WHAT</s>:

WHY:

WHO:

<s>HOW</s>:

## **OVERVIEW:**

## LOREM IPSUM DOLORET

## LOREM IPSUM DOLORET



## As we deliver software, we want to know some information about our application code health, and how **well** we're developing and delivering our software. 

## Leadership and Application Development Teams want to track their application's code health, in order to gain visibility into the areas that need focus and improvements.

## But we may not know where to start, or what to measure, and how often.



# **Visi****on**

## In order to gain visibility of our code base in areas of quality and others, we XXXXXX

## To provide a single place for team members to gain information about a team, and the quality of their applications

##  ... by viewing a dashboard, which displays measurements/metrics, key performance indicators, etc. (Code Coverage, Change Related Incidents, Bug Counts, etc.)

## ... data is aggregated from multiple sources

# 


# **Why iDash (WIIFM)?**



## Our enterprise needs to understand how to objectively measure and analyze software development projects. Reliance on anecdotal evidence reduces the effectiveness of continuous improvement practices.

## Metrics are a primary source of feedback. Development teams that collect and analyze metrics better understand successes, failures and opportunities for improvement. The things that we focus on and measure, get better.



## Baselines are controls that point to metric's data from a specific time or during a specific time interval. Effective development teams actively monitor metrics data and compare results with the original baseline.

## To accurately understand their progress, successful development teams collect metrics from many aspects of the development process, including project business value, culture, processes, infrastructure, architecture, and development and test. 

# 


# **How We Will Accomplish This**?

## iDash is a web-based solution that displays metrics and historical trends. iDash will track enterprise level default measurements; however, team's can also configure iDash to display the metrics that they care about.

# 


# **WHAT**:

## Metrics give you visibility into enterprise critical processes and needs. You'll know exactly where to focus – and when you make changes, you'll have confidence from constant feedback, allowing you to continuously improve, and watch those improvements over time.

##  

## *"A useful <u><strong>measurement</strong></u> should reflect values that align with our organization, business, and team goals, be agile and adaptable, respond quickly to changes, and contain information that is actionable and meaningful." - Peter Varga*

## LOREM IPSUM DOLORET





# **HOW:**

## LOREM IPSUM DOLORET



<ac:structured-macro ac:name="gliffy" ac:schema-version="1" ac:macro-id="ea9f8b2f-318e-473e-8513-b27ded37c1a1"><ac:parameter ac:name="name">iDash-Flow Copy</ac:parameter><ac:parameter ac:name="pagePin">1</ac:parameter></ac:structured-macro>



## **Collect**: Accumulate, normalize, and aggregate metrics from various sources

## **Analyze**: Investigate, correlate, and manage time series data

## **Decide**: Make informed decisions based on visualized trends, detected events in a time series, and find focused areas to improve

## **Act**: Make changes to your team/application/processes, and watch the metrics in real-time change based on your choices

## **Profit**: Make changes iteratively, and benefit from valued metrics based feedback



-----



Metrics provide the data that teams need to continuously improve and to test whether new functionality and processes have provided value.

Clients will view a web page for their application, viewing various collected metrics/information at-a-glance.



## What are the metrics that teams/leaders want to see?

**<u><u>Proof-Of-Concept&nbsp;</u>Metrics to Gather/Track:</u>**

1. Application Name
2. Application Availability / Uptime (time)
3. Tech Debt (time)
4. Test Coverage:
    1. Unit Test (Code) Coverage %
    2. Integration Coverage %
    3. Functional Coverage
5. Test Status:

    1. Unit Tests (Total Number of Tests / Number of Failing Tests / Test Pass %)
    2. Integration Tests (Total Number of Tests / Number of Failing Tests / Test Pass %)
    3. Functional Tests (Total Number of Tests / Number of Failing Tests / Test Pass %)
6. Change Related Incidents (CRIs)
7. Known Bugs/Issues (stretch goal)


## 


## **Application Example (Name)**

**Application Availability / Uptime (hours) :**22h (99.99%) Uptime

**Tech Debt (days) :**93d

**Current Major Incidents (Current / Month Total) :** 1 Current / 3 Month

**Known Bugs/Issues :**24

**Test Status:**


| Automated Test Types<br> | Coverage<br> | Total # Tests<br> | Number of Failing Tests<br> | Test Pass %<br> |
| --- | --- | --- | --- | --- |
| Unit | 90% | 25 | 1 | 96% |
| Integration | 20% | 125 | 3 | 97.6% |
| Functional | 50% | 100 | 25 | 75% |






# POC Metrics Defined + Explained:



**Application Name**: The name of the application or system



**Application Availability / Uptime (seconds)** : The percentage of time that a system is available and usable by clients. [No client impact / application is functioning as expected]

<u>Why this is important to QL:</u>  Availability is usually expressed as a percentage of uptime in a given year. This is measured in "9s" (see ["High Availability"](https://en.wikipedia.org/wiki/High_availability) in Wikipedia).


| Availability %<br> | Downtime per year<br> | Downtime per month<br> | Downtime per week<br> | Downtime per day<br> |
| --- | --- | --- | --- | --- |
| 90% ("one nine") | 36.5 days | 72 hours | 16.8 hours | 2.4 hours |
| 95% ("one and a half nines") | 18.25 days | 36 hours | 8.4 hours | 1.2 hours |
| 99% ("two nines") | 3.65 days | 7.20 hours | 1.68 hours | 14.4 minutes |
| 99.9% ("three nines") | 8.76 hours | 43.8 minutes | 10.1 minutes | 1.44 minutes |
| 99.99% ("four nines") | 52.56 minutes | 4.38 minutes | 1.01 minutes | 8.64 seconds |
| 99.999% ("five nines") | 5.26 minutes | 25.9 seconds | 6.05 seconds | 864.3 milliseconds |
| 99.9999% ("six nines") | 31.5 seconds | 2.59 seconds | 604.8 milliseconds | 86.4 milliseconds |
| 99.9999999% ("nine nines") | 31.5569 milliseconds | 2.6297 milliseconds | 0.6048 milliseconds | 0.0864 milliseconds |






**Tech Debt (time)** : The estimated time it will take to resolve (fix) - all the issues in the application's code (identified by: design decisions, deferred work, static/dynamic analysis tools, etc.)

Each issue is assigned an estimated time to resolve, (in minutes). The total time for all of the issues are added up, and then reported as the "Technical Debt" for an application

<u>Why this is important to QL:&nbsp;</u>These issues are identified problems in our application code. By resolving the known problems in our code, we will have more stable, higher quality applications -- leading to less downtime, safer data, more security, and more business efficiency



**Test Coverage (%)**: Percentage of the source code has been covered by various tests

**Unit Test (Code) Coverage (%)**: Percentage of the source code has been covered by unit tests (based on lines of code). Unit tests are code, that functionally tests application code

**Integration Coverage (%)**: Percentage of the application integrations that have been covered by tests. Integrations are any connections and messages transferring between boundaries, from one thing to another. Examples are between classes, internal modules, API endpoints, other applications, vendor applications, etc.

**Functional Coverage (%)**: Percentage of the application's features that have been covered by tests (based on functional "areas" or requirements of the application)

<u>Why this is important to QL:</u> The higher the Test Coverage, the more confidently we can release our software, with less fear that any new changes will inadvertently cause unintended failures



**Test Status** : Summary of all test runs: unit, integration, and functional. Based on the number of passing tests, total number of tests, and the percentage of passing tests

**Unit Tests (Total Number of Tests / Number of Failing Tests / Test Pass %)** : The total number of unit tests for an application, including the overall test run passing percentage

**Integration Tests (Total Number of Tests / Number of Failing Tests / Test Pass %)** : The total number of integration tests for an application, including the overall test run passing percentage

**Functional Tests (Total Number of Tests / Number of Failing Tests / Test Pass %)** : The total number of functional tests for an application, including the overall test run passing percentage

<u>Why this is important to QL:</u> Our tests are critical to ensuring that the application code is working as expected. These tests also ensure that any changes to the code, do not cause unintended consequences



**Current Change Related Incidents :** This metric tracks the current number of problems associated with any new changes to an application

<u>Why this is important to QL:</u> If an application is currently experiencing a "change related incident", (and the historical tracking of this number over a time period, ie. a "sprint cycle"), allows teams to focus on and reduce the amount of change related incidents, leading towards continuous improvement, and increased uptime/availability





**Known Bugs/Issues** : These are the known bugs, issues, and/or defects in the application software, identified in any environment

<u>Why this is important to QL:</u> By resolving the known problems in our applications, we will have more stable, higher quality applications -- leading to less downtime, safer data, more security, and more business efficiency





## Metadata Information For Metrics

Metrics are essentially a number value and a unit of measurement:

Metric = [Numeric VALUE] [Unit of Measure]

Examples: 130 seconds / 34 oz / 23 miles, etc.

- **Data Sources** (where is the information coming from: databases, APIs, etc.)
- **Number and Unit of Measure** ([Numeric VALUE] [Unit of Measure] )
- **Metric Thresholds** (are there any grades/levels to the number)
    - Healthy (green) / Warning (yellow) / Error (red)
- **Organization** (parent/child relationships)
    - Considering "tagging" parent/child and group on tags - hung on apps (need to respond to change / often)
    - Platforms/Hierarchy/Owners/Teams changes often: Applications don't change as much
- **Historical Trend** (since the previous measure - spark lined)
- **Data Polling Interval** (how often / at what interval of time, do we want to refresh/update the data)
- **Security / Level Of Detail** : Customizable : Team members, Team Leaders, Platform Leaders, VP, (buckets of parent/child) - etc. - All view different roll-up, teams/views, and types of metrics
    - Security : LOD + Least privileges + Restrict access based on AD/LDAP (consider: client secrets / groups)

