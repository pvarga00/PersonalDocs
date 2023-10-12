
## Deployment Preference - ECS

## Authorization

Within the same ECS cluster, API Header Keys are acceptable for authorization of access between endpoints.

Docker EE components must have an API Gateway to expose their endpoints to the ECS clusters and use OAuth for authorization, not API Keys

If an ECS instance accesses a different cluster, it must follow the Docker EE requirement of API Gateways and OAuth

## Network Communication Encryption - TLS

Use HTTPS and TLS 1.2+ for all communications between components, even within the sample cluster.

(Note: This is to ensure using a TLS encrypted communication, not to use TLS Client Certificates)



For additional information on securing the data in transit, see <ac:link><ri:page ri:space-key="~pvarga" ri:content-title="NFR - Data Security"></ri:page></ac:link>



Sources:

<ac:link><ri:space ri:space-key="theplaybook"></ri:space></ac:link>
