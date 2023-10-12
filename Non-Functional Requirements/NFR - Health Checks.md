
[https://git.rockfin.com/tech-standards/rfcs/blob/PRitchie-health-check-api-rfc/10172-health-endpoint-rfc.md](https://git.rockfin.com/tech-standards/rfcs/blob/PRitchie-health-check-api-rfc/10172-health-endpoint-rfc.md)

- [TrueRocket HealthChecks Docs](TRU-HealthcheckEndpointsForApps-221221-1509-215.pdf)

## TO DO: Health Check QuGet Package

- Health checks should be able to be developed as a consumable and configurable package for LiftOff using the patterns
- Customized output via "ResponseWriter" to expose more than status of "Health/Unhealthy/Degraded"


## Endpoint: /health/basic (GET - application/json)

- Status: Health/Unhealthy/Degraded


## Endpoint: /health/extended (GET - application/json)

(Included the response of /health/basic plus additional information

- DB Connection Status
- Dependency Connectivity
    - Queues
    - Topics
    - Service dependencies


## Sources

<ac:link><ri:page ri:space-key="~pvarga" ri:content-title="Generic Healthcheck Information"></ri:page></ac:link>

[https://docs.microsoft.com/en-us/aspnet/core/host-and-deploy/health-checks?view=aspnetcore-2.2](https://docs.microsoft.com/en-us/aspnet/core/host-and-deploy/health-checks?view=aspnetcore-2.2)



**Fantastic Four Inventory**

The following are apps that should be monitored via healthcheck endpoints for the Lift Off:


| App Name<br> | CoreID | TEST HC Url(s)<br> | BETA HC Url(s)<br> |  PROD HC Url(s) | Conn (if needed)<br> |
| --- | --- | --- | --- | --- | --- |
| <br> | <br> | <br> | <br><br><br> | <br> | <br><br> |



