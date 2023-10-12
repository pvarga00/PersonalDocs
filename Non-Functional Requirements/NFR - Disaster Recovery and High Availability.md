
## Infrastructure Implementation

### Components

All components should be deployed using the following pattern in particular region

1. ECS Cluster with an auto scaling group set to at least 2 availability zones
2. Each service must have a elastic load balancer as the entry point for the multiple instances of the service
3. API Gateway is configured for authorization into the service


When applicable, Route 53 can be used for load balancing across publicly available endpoints.

### Databases

For production, databases are key to achieving disaster recovery goals and high availability. With Aurora Global and Multi-Master Dynamo, achieving a cross region database implementation is easier than ever. However, these are relatively new breakthroughs.

## Retry & Circuit Breakers

The purpose of a retry is to maintain resilience with intermittent issues. These issues can be caused by network faults, instances being spun up / spun down, and even faults inside of a dependency that has not yet reported bad health. To mitigate these issues, retry and circuit breaker patterns can be used to attempt recovery.

A Retry pattern repeats logic after a slight delay when the dependency does not confirm success or an expected failure code (e.g. HTTP response code 400). Retry logic used with an increasing sleep cycle is a good pattern to follow assuming that most transient issues are brief and can be recovered quickly. Some protocol technologies can handle the retry logic for some cases but not all and it is a good practice to implement the retry explicitly even if it's never needed. I suggest either 3 retries at 500ms/2s sleep or 5 retries at 250ms, 500ms, 1s, 2s sleep durations.

A circuit breaker can also be used if there is a mechanism in place to "retry later" or a fallback endpoint that will maintain the integrity of the system. If it is a cyclical process then usually a circuit breaker pattern will automatically recover after the "timeout period" or health check success on a subsequent run. With a service endpoint fail over, one option A has a circuit breaker tripped the system uses option B until it determines that option A is available again. However, this does not handle the case when option B is also problematic. Therefore it is always good to have a retry/recover approach around any circuit breaker implementation.

## Cross-Region Approach

Cross-region support is vital to maintaining good response times to end users that are in different regions but it is more important for disaster recovery. The goal is to limit the downtime if a failure happens in a given region. Active-Active and Active-Passive are the two main approaches where the first provides theoretically no downtime but introduces the problem of concurrency. The second limits concurrency problems (since only one instance runs at a time) but has increased downtime and additional latency as users are moved from one region to another. Active-Active is the desired goal of major multi-regional business critical applications and services.

### Problems

Traditionally active-active has faced the barrier at the database level. This is why AWS has availability zones for better disaster recovery times without the synchronization between regions. However, AWS Aurora Global and DynamoDB both support multi-region essentially eliminating this concern.

There are still problem with determining the transport layer of an application with regards to cross-region support. SQS and SNS do not support cross-region replication and neither does Amazon MQ.

## Fault Scenarios and Recovery Scenarios

1. Synchronous
    1. Description - This is API to API communication where a request is made and a response is given to confirm the action or return a value
    2. Scenario - Dependency Unavailable
        1. Description - A downstream dependency is does not response or responds with an unexpected message (HTTP error code 503)
        2. Causes
            1. Network fault failed to reach endpoint
            2. Timeout, service did not respond
                1. Unhealthy container (Memory, CPU, etc)
            3. Downstream dependency failed as part of a sub-routine
            4. Auto-scaling up/down of service caused transient issue
            5. Service outage
        3. Impact - Various depending on the type of outage, worst case - Entire region unavailable for given service (broken code)
        4. Recovery
            1. Infrastructure & Health Checks - Auto-scaling infrastructure and meaningful, cascading health checks ensure the health of each component is reported up the the auto-scaling controller to ensure that unhealthy instances are removed and new instances are put in it's place. This helps turn a sustained outage or load based outage in to a brief outage.
            2. Retry logic - Retries maintain stability in cases where the interruption is brief and the infrastructure design can automatically adapt and recover from issues
            3. Circuit breaker - Covers sustained outages that are not critical to the operation of the service itself and have a mechanism in place to recover later. If the issue can not be recovered automatically at a later point or is a critical piece of the service functionality (e.g. database) it is better to report an "unhealthy" status and fail the service as well.
2. Asynchronous
    1. Description - Event based messages where the sender has no direct interaction or knowledge of the recipient of a message
    2. Scenario - Failure to Send Message
        1. Description - When trying to send messages, the service is unable to reach the publishing endpoint (e.g. SNS)
        2. Causes
            1. Message publishing endpoint (SNS) is unavailable - Region wide outage
        3. Impact - Unable to publish async messages to downstream, broken pipeline
        4. Recovery
            1. Retry - A retry pattern will ensure that this is not an intermittent issue
            2. Circuit Breaker - This would be for cross region support where the message would be published to a different region
    3. Scenario - Failure to Receive Message
        1. Description - When trying to retrieve messages, the service is unable to reach the incoming messages endpoint (e.g. SQS)
        2. Causes
            1. Incoming message endpoint (SQS) is unavailable - Region wide outage
        3. Recovery
            1. Retry - A retry pattern will ensure that this is not an intermittent issue
            2. Circuit Breaker - This would be for cross region support where the component would read from messages in a different queue
    4. Scenario - Failure to complete Transaction of Received Message - Recoverable
        1. Description - A message was received successfully but the service was unable to complete the transaction of processing that message
        2. Causes
            1. Processing of message throws an exception from a downstream dependency 
                1. e.g. Processing a LOD Changed Event and unable to save to the database
        3. Recovery
            1. Retry - By retrying the processing the message can be re-attempted
            2. Restore Message - If the dependency is down, the message should be restored or republished so that it can be recovered by another instance or region. Then the component can report itself as unhealthy
            3. Error Notification - **TBD:** How to send messages back to the publisher about an error
    5. Scenario - Failure to complete Transaction of Received Message - Unrecoverable
        1. Description - A message was received successfully but the service threw an unrecoverable exception and the process exited without completing the transaction leaving the message processing incomplete with no notification of the service failure
        2. Causes
            1. While processing a message the instance experiences a failure which terminates all processes that are in progress
        3. Recovery
            1. This is a technology/implementation problem where the solution is to essentially confirm receipt / completion of the transaction of the message so that the message is then removed. This would need to be done through a "keep alive" strategy so that once the system fails to complete the transaction the message is "released" for another component while also allowing for the component to "retain" the message if processing is taking longer than expected.
3. Infrastructure Failures
    1. AWS Whole Region Down
        1. If a whole region is down then Route 53 should catch this through the health check implementations
    2. AWS Region Service Down
        1. ECS/EC2
            1. Route 53 controlling the load balancing between regions will handle this. If single region, complete outage.
        2. SNS
            1. Addressed above, would fail to other region
            2. Note - Solution Architecture does not recommend SNS for multi-region applications
        3. SQS
            1. Addressed above, would fail to other region
            2. Note - Solution Architecture does not recommend SNS for multi-region applications






Sources:
 <ac:link><ri:page ri:space-key="NFRSArchive" ri:content-title="6. Disaster Recovery"></ri:page></ac:link>
