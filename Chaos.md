Our Team: Dave Terry Bhavdeep Patel Lane Goolsby Chris Boler Peter Varga Kyle Robertson

GIT Repo (App): https://git.rockfin.com/origination/loanCreationv2

GIT Repo (BOOMStick): https://git.rockfin.com/lgoolsby/Boomstick

CircleCI: https://circleci.foc.zone/gh/origination/workflows/loanCreationv2

HackWeek Project: https://quicken-loans.brightidea.com/D51542

MyAccess: AWS-SSO-RocketAPI-NonProd-Developer (ID: 690484663496)



Let's build an agent of chaos engineering. This service will intentionally inject chaos conditions into the data services systems in production in order to determine weaknesses. We will then report on these conditions in real-time which will allow our teams to determine our current "steady state" and highlight areas that we need to focus on improving.

We will begin our experiment by using the following steps:

Start by defining 'steady state' as some measurable output of a system that indicates normal behavior.
Hypothesize that this steady state will continue in both the control group and the experimental group.
Introduce variables that reflect real world events like servers that crash, hard drives that malfunction, network connections that are severed, etc.
Try to disprove the hypothesis by looking for a difference in steady state between the control group and the experimental group.
Check out https://confluence/pages/viewpage.action?pageId=163589484 for a more detailed description and for additional resources.

That Will Result In.... 
A higher level of confidence in our production systems and a more robust and hardened process.

What will you impact most? 
Client Experience

What metric are you trying to change?
Overall site reliability. We want to know where are weaknesses are, instead of encountering them in the wild.

At the end of Hack Week, your goal for the experiment is to: 
Create a proof of concept

Experiment Summary
What's the value of Chaos Engineering?
Think of Chaos Engineering as a fire drill for system outages. They help teams get familiar with how to manage specific outages and close the gap between knowns and unknowns. You can also think about Chaos Engineering as a vaccine for systems. By injecting a smaller scale failure or outage and using careful monitoring we can potentially inoculate a system against those failures modes. Chaos Engineering provides value to the entire business through the following means:

Customer: the increased availability and durability of service means no outages disrupt their day-to-day lives.
Business: Chaos Engineering can help prevent extremely large losses in revenue and maintenance costs, create happier and more engaged engineers, improve in on-call training for engineering teams, and improve the tech incident responses for the entire company.
Technical: the insights from chaos experiments can mean a reduction in incidents, reduction in on-call burden, increased understanding of system failure modes, improved system design, faster mean time to detection for TI's and reduction in repeated TI's.
What are we trying to do?
We wanted to illustrate how we can utilize chaos engineering practices and tools to help identify potential failures before they become outages.

What we did?
Stood up the following services in AWS
Halyard
Spinnaker
Bastion
MySql
Chaos Monkey
Modified the LoanCreator2 application to provide insight into system health
Created BOOMStick application that can act as our own Chaos Monkey (infrastructure is hard)
Created front-end dashboard to track the results of our chaos experiments.
So what happened?
We struggled for a little while with the stack and AWS
We decided to build our own app that would utilize the AWS SDK to perform the same tasks as Chaos Monkey
We struggled some more getting Spinnaker and Bastion to work together in our environment
What's next?
Polish up BOOMStick and Ping front-end
Identify applications to perform experiments
Documentation and Training on Chaos Engineering practices and design techniques
Identify other experiment types (CPU usage, network latency, datastore saturation, etc)
Create/Install additional tools to perform experiments
Rinse and repeat


Original Content from here: https://www.capitalone.com/tech/software-engineering/continuous-chaos-introducing-chaos-engineering-into-devops-practices

Moar Content:

https://techbeacon.com/app-dev-testing/chaos-engineering-testing-34-tools-tutorials
https://sharpend.io/chaos-engineering-101/
https://www.gremlin.com/community/tutorials/a-primer-on-automating-chaos/
https://chaostoolkit.org/ / https://github.com/chaostoolkit
https://github.com/Netflix/chaosmonkey
https://github.com/dastergon/awesome-chaos-engineering
https://www.gremlin.com/chaos-monkey/chaos-monkey-tutorial/ – TUTORIAL!!
https://www.gremlin.com/chaos-monkey/ - OVERVIEW
https://netflix.github.io/chaosmonkey/How-to-deploy/ - Step-by-step Netflix
https://www.baeldung.com/spring-boot-chaos-monkey - Java apps setup



Traditional testing approaches can’t predict all failure modes; Chaos Engineering is a discipline to simulate these failures and build better applications. It’s about introducing controlled disruptions into a distributed system, carefully studying the behavior, identifying the weak areas, and improving resiliency with automation. Adding continuous chaos to DevOps culture helps us build better anti-fragile applications.



So, what are the various phases of Chaos Engineering? Let’s describe them.

Application Assessment for Readiness
Before an org can start running Chaos Experiments on an application, you need to assess it for readiness. This means going over the following:

The Application Architecture must be reviewed in depth to identify various failure points, dependencies, customer impact, and recovery procedures.
Identify potential failure points which may not be optimal for running chaos testing.
Certify Chaos Testing Readiness for targeted components/services.
Once you’ve determined that you’re ready to test, it’s time to define some parameters.

Define Steady-State Behaviors and Form Hypotheses
Steady-State Behavior
First, define the steady-state behavior of the application. This refers to the normal operation of the application. Keep in mind, SLAs must be taken into account for the steady-state.

To define the steady-state, you should use both technical and business metrics. Some samples are as below:

Technical Metrics

Latency
Number of errors thrown over a period
Results from health end endpoint
Average CPU
Business Metrics

Number of logins per minute during peak
Number of failed logins per minute
Number of declined transactions per second
Form Hypotheses
Once you’ve define the steady-state behavior, the next goal is to form some hypothesis of what you expect from the Chaos Experiment.

Some hypotheses may include, but are not limited to:

The Application Health Check endpoint will not be impacted throughout the experiment.
When a random virtual machine is terminated, our failures are negligible at < 10 failed logins per 10,000 logins.
When the Database fails over, the application will continue to function normally but will provide a friendly message for certain transactions to retry after few minutes.
When testing geographical failure, the application will be down for five minutes, but a static site will serve some basic information.
Define the Chaos Experiments You’ll Be Running
Unlike a traditional testing approach, with Chaos Experiments we’re studying expected outcomes rather than predicting exact behaviors. For example, when we terminate 33% of auto-scaling group instances to simulate an AZ failure, we expect that ASG will spin up new instances and the application will eventually be at full capacity. But how many in-flight transactions will be affected? Actual customer impact is something we could form a hypothesis for, but we will have to study the outcome to understand actual behavior and address gaps in the system.

Define your experiments according to the application architecture, keeping in mind known limitations. Note that these should be real-world events.

The following are sample experiments for a generic three tier application deployed in two regions. This list is not comprehensive and depends on the application tooling support and maturity, but it is a good starting point.

Terminate random virtual server in a region.
Subject entire fleet to high CPU/Memory within a region.
Increase latency in one or more servers.
Block access to a storage system.
Failover a database to its secondary.
Random killing of critical processes.
Once an application demonstrates resilience to these basic experiments, the experiments should be compounded to increase the intensity of the experiment. Some samples of what this could look like are below:

Hog both CPU and memory in part of the fleet.
Terminate virtual servers while database is failing over.
By varying these real-world events and continuing to study the behavior of the systems, we can address the gaps and revisit the steady-state. Then we can form new hypotheses and create a feedback loop until we exhaust our hypotheses. All while we continue to run tests to ensure that any change in the system didn’t invalidate the previous hypotheses.

Bring Chaos into Practice
Once Chaos Engineering objectives are set, it’s time to bring them to reality. The practice should be adopted incrementally from lower environments all the way to live production systems. The practice should mature over time and eventually become part of standard development with developers improving systems until they’re not even aware of chaos injection schedule, instead relying on resilient systems to handle it all the time.

Run Experiments in Pre-Production Environments
Once the approach is solidified, we can get our feet wet on the testing approach and tooling in the QA environment. Here we do functional testing validations, mainly to validate the business metrics. Note — since the system is not under load, many technical metrics may not be visible at this point in time.

Once the functional validation is finished, we can move on to other advanced testing strategies which include — but are not limited to — load testing, performance testing, and endurance testing. These testing approaches expose vulnerabilities in the system that are visible only under certain conditions like a high load. Note — at any point in time, the testing must support stopping the experiment to mitigate further risk when things do not go as we expected.

Throughout the pre-production testing, the results are fed back into the application design/architecture and repeated until all the hypotheses are validated against steady-state behavior and we are ready to move on to production.

Game-Day for the Production Environment
Planning a “game-day” makes sure that the right personnel is available to run tests, handle failures, and discuss the outcome in real-time when you move testing to production. Here are some possible steps to preparing for game-day. These will vary by organization and the property being tested, you will need to do research to determine the right steps for your needs:

Pre-production steady-state behaviors, hypotheses, and the Chaos Experiments are reviewed for production applicability and evaluated against the risk of customer impact.
Experiments which are beyond the acceptable scope of impact will be deferred until the system is re-architected to handle them.
Schedule the game-day when the application experts, the Chaos Engineering experts, and other stakeholders can gather and review the plan.
Tests are run in an incremental fashion while monitoring the situation, validating that the system is functioning as expected, and moving on to next experiment when completed.
Additionally, the following should be taken into account:

Ideally, failures must be handled automatically, and the system must be self-healing as failures occur.
The experiment must stop immediately if the system deviates from normal behavior.
At the end of game-day, you should walk out with takeaways to address any gaps found in the system and the variance of results in pre-production vs. production systems. The issues found must be addressed, another game-day should be scheduled, and this should be repeated until you become confident that the system is resilient to the failure scenarios you are testing for.

Integrate Chaos Testing with CICD Pipeline
Once the Chaos Experiments are validated in the development-through-production cycle, it makes sense to integrate with your CICD. As part of the deployment pipeline, a Chaos Configuration File can be pushed to start disruptions in the specific environment. Some of the scenarios you can use are:

Disrupt the virtual servers when a deployment is still being pushed.
Orchestrate a “canary deployment” through the pipeline, induce failures in the new version of the microservice, and check behavior of system.
Kick off a load test after deployment, terminate a few instances and validate that the system can consistently handle the load under reduced capacity.
By including Chaos Testing as part of the CICD pipeline, several hypotheses are continuously validated. For example, a deployment should always succeed even if some instances are not available during the deployment.

Enable Random Chaos in Production
At this stage, applications are expected to be self-healing and able to sustain all known failures. Applications must have monitoring infrastructure in place which can continually provide feedback about the steady-state behavior of the system and alert when deviating from the norm.

Once the Chaos Testing has passed the game-day and been continuously validated in a CICD pipeline, we are in a position to enable it in production. This should be done incrementally, but in a random fashion, without notifying the support teams. This has to be done carefully and the tooling must be mature enough to stop the testing without further impacts.

Generally, Chaos Testing will be initialized during random non-peak times. Over a period of time, the application should reach the maturity point where it can be tested at peak times.

Chaos Engineering Maturity


This diagram shows what Chaos Engineering maturity looks like.

The maturity model depicts how the applications can achieve the maturity by progressively adopting the practice from no chaos to being leaders in the space. The horizontal axis focuses on adoption, while the vertical axis focuses on the sophistication of the tooling involved.

Strong and resilient applications push the needle on both adoption and advanced tooling, evolving as leaders in the space. By making Chaos Engineering part of the DevOps culture, developers and stakeholders continually embrace failure as a way to prepare for and prevent it, resulting in stronger and more resilient applications.





Experiments:
Planning your First Experiment
One of the most powerful questions in Chaos Engineering is “What could go wrong?”. By asking this question about our services and environments, we can review potential weaknesses and discuss expected outcomes. Similar to a risk assessment, this informs priorities about which scenarios are more likely (or more frightening) and should be tested first. By sitting down as a team and whiteboarding your service(s), dependencies (both internal and external), and data stores, you can formulate a picture of “What could go wrong?”. When in doubt, injecting a failure or a delay into each of your dependencies is a great place to start.



Creating a Hypothesis

You have an idea of what can go wrong. You have chosen the exact failure to inject. What happens next? This is an excellent thought exercise to work through as a team. By discussing the scenario, you can hypothesize on the expected outcome before running it live. What will be the impact to customers, to your service, or to your dependencies?



Measuring the Impact

To understand how your system behaves under stress, you need to measure your system’s availability and durability. It is good to have a key performance metric that correlates to customer success (such as orders per minute, or stream starts per second). As a rule of thumb, if you ever see an impact to these metrics, you want to halt the experiment immediately. Next is measuring the failure itself where you want to verify (or disprove) your hypothesis. This could be the impact on latency, requests per second, or system resources. Lastly, you want to survey your dashboards and alarms for unintended side effects.



Have a Rollback Plan

Always have a backup plan in case things go wrong, but accept that sometimes even the backup plan can fail. Talk through how you’re going to revert the impact. If you’re running commands by hand, be thoughtful not to break ssh or control plane access to your instances. One of the core aspects of Gremlin is safety. All of our attacks can be reverted immediately, allowing you to safely abort and return to steady state if things go wrong.



Go fix it!

After running your first experiment, hopefully, there is one of two outcomes: either you’ve verified that your system is resilient to the failure you introduced, or you’ve found a problem you need to fix. Both of these are good outcomes. On one hand, you’ve increased your confidence in the system and its behavior, and on the other you’ve found a problem before it caused an outage.



Have Fun!

Chaos Engineering is a tool to make your job easier. By proactively testing and validating your system’s failure modes you will reduce your operational burden, increase your availability, and sleep better at night. Gremlin makes it safe and simple to get started—email us to get started today!



Experiment 1: The Network is Not Reliable
Network dependencies are a fact of life in a distributed system, and as distributed systems are growing in adoption AND complexity, Chaos Engineering becomes an optimal way to test for potential failures on the path to increasing resilience.

We know from the Fallacies of Distributed Computing that the network is unreliable. This implies that the success of our overall system will be determined by how many network calls we make, and how much we can shield the customer from the failures that do occur.

Applications generally have both internal and external network dependencies. Here, I'm defining internal dependencies to be those systems that are under our organization's control. Someone is carrying a pager for that system and they work for the same company I do. We can (and should) expect that internal teams try to maintain availability, and use the proper tools and channels to notify them if they don't.

When you do have a dependency that is out of your control, it's critical to understand how the system reacts when it is unavailable. This is a network blackhole Chaos Experiment and will make the designated addresses unreachable from your application. Once you've applied the blackhole, you should check that your application starts up normally and is able to serve customer traffic without the dependency.



Vectors:

Attack: Network Blackhole / Latency
Scope: single instance
Expected Results: Traffic to dependency goes to 0 (or gets slow), startup completes without errors, application-level metrics in steady-state are unaffected, traffic to fallback systems shows up and is successful, dependency alerts and pages may fire (if scoped to single-instance)


Experiment 2: DNS Unavailability
It's easy to forget the critical role that DNS plays in keeping our systems running. Many companies experienced customer-facing issues when a real-world DNS failure occurred in October 2016. Because a failure like this is relatively rare, getting a recovery plan together is challenging.

The best way forward is to induce a DNS outage and understand how your application behaves. If you blackhole DNS traffic on a single instance, it will appear to that instance as if DNS is unavailable. The fixes will vary depending on the issue, but common solutions are to pass around IP addresses instead of hostnames for internal addressing and the use of a backup DNS provider. Once you've run this experiment, an exercise for the reader is to then consider what sort of damage an outage of an internal service discovery tool (like etcd, Eureka, Consul, etc) would cause.



Vectors:
- Attack: DNS blackhole
- Scope: single instance
- Expected Results: Inbound traffic may drop, traffic to external systems may fail, startup may not complete successfully
