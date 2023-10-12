


## Problem

Data required for centralized visibility is dispersed across various applications (Cherwell, AppDynamics, SonarQube, etc). In order to get a centralized view we must understand the naming conventions across all data sources from both an endpoint perspective and naming perspective.

## Proposed Solution

1. Find a source that will be held as the source of truth for "Naming" - This application should have the most mature repository of our IT application
2. Create a Middleware that aggregates all names for a particular API source and it's endpoint
    1. So if we wanted to include an data source like Sonar we would identify the endpoint which







|   | APP NAME | Core | SonarQube | Cherwell | Splunk | AppDynamics | DCRum |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | ALMDemo2015 | X |   | X |   |   |   |
| 2 | MyQL Origin | XXX | XXX | XX<br> |   |   |   |
| 3 |   |   |   |   |   |   |   |
| 4 |   |   |   |   |   |   |   |

