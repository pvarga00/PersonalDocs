
**What is this?**

In order to properly monitor the health of our services and applications, we should be putting healthcheck endpoints into each and every deployable that can be targeted by outside apps. These should be simple endpoints accessible by HTTP GET calls which return information about the currently running app.



**How should this be implemented?**

These health checks should be present in each app:

1. **Basic**: This reports the very basic up/down status of the app. Start reporting the basic information first...
2. **Extended Info:**This reports in greater detail the current status of the app and environment. Ultimately, this information will be added on top of the basic implementation


Any data returned in a response body should be JSON formatted.



**The Basic Healthcheck (Start by implementing this first)**

The basic healthcheck will be monitored constantly, and as such should not invoke any complexity that could potentially encumber the app itself. No downstream services or dependencies should be monitored or relied upon to manage this endpoint, only static information that can be readily served by the app.



**Do not invoke any service calls or other components outside of the application server itself to complete this request.**

Basic healthchecks can be used to take **automated actions** such load balancing



Examples of information that could be provided are:

- Up/Down (simple HTTP 200 response would suffice)
- Currently running version number or git SHA
- Last deployment time
- Uptime
- Environment information (ex PHP or .NET runtime versions, configuration options, non-secret environment variables): **note**be extremely careful with what is exposed here. If you're afraid this endpoint could be targeted by the general public err on the side of caution when choosing to provide details.




**The Extended Healthcheck (Add more information to your Healthchecks!)**

The extended healthcheck should give greater detail than the basic healthcheck above, and tell the consumer enough information to be reasonably sure that this application can fulfill it's full range of responsibilities.



**Do not use extended healthchecks to control load balancing or automated instance health.**

Extended healthchecks should be used to provide metrics and monitoring abilities to team members (e.g. [statuspage.io](http://statuspage.io/), Grafana, or other dashboard systems).



Examples of information that could be provided are:

- Status of connectivity to data stores and other software dependencies (ex. Dynamo DB, queues/topics, SQL Server instances, cache servers, etc.).
- Status of connectivity to critical downstream services (ex. app specific midwares, QKS, Submission Engine)


**Information that probably doesn't belong in the HCs:**

The following should be monitored and measured by other tools, such as AppDynamics, StatsD, AWS XRay, Splunk, or not at all (secrets).

- Performance metrics and data
- Server resource information (memory, disk space, etc.)
- Log data
- Secret or privileged information (don't expose app keys, ids, or usernames)
- Any counters or aggregated time-series information. Stateless only

