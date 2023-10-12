
- <ac:link><ri:page ri:space-key="LO" ri:content-title="Content Configuration Documents"></ri:page><ac:plain-text-link-body><![CDATA[Configuration Spreadsheet]]></ac:plain-text-link-body></ac:link>
- <ac:link><ri:page ri:space-key="~pvarga" ri:content-title="LiftOff: Overall Issues/Bugs List"></ri:page></ac:link>
- [E2E TFS Testcases](http://tfs/tfs/QL/IT/OrchestrationServices/_testManagement?planId=1438378&amp;suiteId=1468036&amp;_a=tests)
- [LiftOff: Test Data](https://confluence/display/LO/Test+Data)
- [Detroit Labs: Katalon Test Suite (DL's GitHub.com Repo)](https://github.com/detroit-labs/liftoff-automation)
- [Detroit Labs: Katalon Test Suite (QL's copy of the suite in GHE)](https://git.rockfin.com/LiftOff/liftoff-automation)
- [Teams Chat Room: E2E Testing & Coordination](https://teams.microsoft.com/_#/conversations/LiftOff-E2E?threadId=19:9d264d4a506e4eb8a3ce03445739489a@thread.skype&amp;ctx=channel)
- [Initial E2E Kick-Off Meeting (Video)](https://rockfin.sharepoint.com/sites/LiftOffOperationalPrototype/Shared%20Documents/LiftOff-E2E/LO-E2E-KickOff.mp4)




“Orchestration Services” RT owns the entire E2E testing flow (automated tests/suites) – coordinating with the other RTs, to accomplish this.



**<u>E2E Action Plan:</u>**

- Identify each business requirement
- Identify the chain of events for each scenario (from a technical standpoint)
- What services will be called for each scenario, (APIs and their query-string-parameters),  (and which LO Teams/RTs own which services)
- Data contracts for each API (what data needs to be created/passed into the request, how to handle the response messages/bodies, and hoe to clean-up the test data generated)
- Create automated tests, which will chain the API events together in a “flow” (E2E):
    - *Note: E2E Testing will be conducted from both the **CoPilot UI** <u>and</u> from the **API layers** (C# code, as a collection of test suites)*




<u><strong>Helpful Information:</strong></u>

1. Lift Off “30K foot” architecture diagram: [https://confluence/display/LO/Architecture](https://confluence/display/LO/Architecture)  (this shows the full end state, but for the OP we are building the Influencer UI, HIM Conversation Manager, Enrichment Engine, Checklist Engine, and LOD)
2. A low level, technical Visio diagram of how data flows throughout the solution is located here:[https://confluence/display/LO/Mercury+3](https://confluence/display/LO/Mercury+3)
3. John Comiskey’s walk through of the Lift Off Configuration Spreadsheet is located in Teams in the Files tab of the Lift Off &gt; General channel
4. Link to the configuration documentation: [https://confluence/display/LO/Content+Configuration+Documents](https://confluence/display/LO/Content+Configuration+Documents)
5. Link to the latest Lift Off prototype scope area flows:[https://confluence/display/LO/Scope+Area+Flow+1%3A+Client+Pre+Screening](https://confluence/display/LO/Scope+Area+Flow+1%3A+Client+Pre+Screening) and [https://confluence/display/LO/Scope+Area+Flow+2%3A+Income+and+Credit+Qualification](https://confluence/display/LO/Scope+Area+Flow+2%3A+Income+and+Credit+Qualification) (these flows roughly follow the configuration spreadsheet flow of data exceptions and topics but are not an exact 1-1 match, they are a bit more general and they also include the enrichment points)


<u><strong><br></strong></u>

<u><strong><br></strong></u>

<u><strong>LO: ProtoType Image 1:</strong></u>

<ac:image ac:width="950"><ri:attachment ri:filename="LO-ProtoType0.png"><ri:page ri:space-key="~pvarga" ri:content-title="E2E Strategy"></ri:page></ri:attachment></ac:image>

<u><strong>LO: ProtoType Image 2 (continued):</strong></u>

<ac:image ac:width="950"><ri:attachment ri:filename="LO-ProtoType1.png"><ri:page ri:space-key="~pvarga" ri:content-title="E2E Strategy"></ri:page></ri:attachment></ac:image>


