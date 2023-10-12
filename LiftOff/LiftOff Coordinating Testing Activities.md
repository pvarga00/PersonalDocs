
<ac:structured-macro ac:name="children" ac:schema-version="2" ac:macro-id="2c5e7074-51e2-423b-8ebc-7fe1772338d2"><ac:parameter ac:name="all">true</ac:parameter><ac:parameter ac:name="depth">2</ac:parameter></ac:structured-macro>

# Overall Testing Order (of focused priority):

1. **Unit Testing**
2. **Integration Testing**: **Code**: **Isolation**: Testing your application's APIs in isolation from automated code: Ensuring every endpoint for your application (using the same code language as the application code)
3. **Integration Testing:** **Code**: **Dependencies**: Testing your application APIs from automated code: Ensuring your application's ability to communicate with direct dependencies / other "external" APIs (using the same code language as the application code)
4. **User Interface (UI) Testing**\*\* (if applicable)
5. **Integration Testing: Postman** **Collections: Isolation**: Testing your application APIs in isolation, of your application (from Postman)
6. **Integration Testing: Postman** **Collections: Dependencies**: Testing your application APIs - ensuring your application's ability to communicate with direct dependencies / other "external" APIs (from Postman)


## Features/Applications To Be Tested (Implementation Details per LiftOff Application)


| Status | Description |
| --- | --- |
| N/A | Not Applicable |
| IP | In-Progress |
| Delivered | Delivered |




Liftoff Git Repositories

- Main: [https://git.rockfin.com/LiftOff](https://git.rockfin.com/LiftOff)
- Conversations API: [https://git.rockfin.com/LiftOff/conversations-api](https://git.rockfin.com/LiftOff/conversations-api)
- Content API: [https://git.rockfin.com/LiftOff/question-trails-content-api](https://git.rockfin.com/LiftOff/question-trails-content-api)




**"RocketPro" : Rocket Professional (previously called: Copilot) Web Application**:

- TEST: [https://copilotweb-test.docker.foc.zone](https://copilotweb-test.docker.foc.zone/login)
- BETA: [https://copilotweb-beta.docker.foc.zone](https://copilotweb-beta.docker.foc.zone/login)




**Conversations API** Swagger:

- TEST: [http://conversations-api-test.mi.corp.rockfin.com:20030/swagger/](http://conversations-api-test.mi.corp.rockfin.com:20030/swagger/)
- BETA: [http://conversations-api-test.mi.corp.rockfin.com:20031/swagger/](http://conversations-api-test.mi.corp.rockfin.com:20030/swagger/)




**Content API** Swagger:

- TEST: [http://question-trail-content-api-test.mi.corp.rockfin.com:20066/swagger/](http://question-trail-content-api-test.mi.corp.rockfin.com:20066/swagger/)
- BETA: [http://question-trail-content-api-beta.mi.corp.rockfin.com:20067/swagger/](http://question-trail-content-api-beta.mi.corp.rockfin.com:20067/swagger/)





| App Name | CoreID | Owner/Leader | Deployment Pipeline<br><br>(CircleCI)<br> | **Static Code Analysis / Code Coverage (%)**<br><br>**(SonarQube)**<br> | Unit Tests | Integration Tests | Performance Tests | Load Tests | Security API Tests<br> | Penetration Tests | Various Other Applicable Testing\*\*<br> | Smoke Tests (PROD) | Monitoring / Alerting<br><br>(PROD)<br> | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Rocket Pro (Co-Pilot): WebApp<br><ul><li><a href="https://github.com/detroit-labs/liftoff-web">https://github.com/detroit-labs/liftoff-web</a></li><li><a href="https://git.rockfin.com/LiftOff/liftoff-web-master">https://git.rockfin.com/LiftOff/liftoff-web-master</a></li></ul><br>Docs:<br><br>[https://github.com/detroit-labs/liftoff-documentation](https://github.com/detroit-labs/liftoff-documentation)<br> | [202218](http://core/app/202218)<br> | Detroit Labs: Ed Goff | IP | IP | <br> | <br> | <br> | <br> | <br> | <br> | UI | <br> | <br> | <br> |
| Rocket Pro (Co-Pilot): BFF<br><ul><li><a href="https://github.com/detroit-labs/liftoff-backend">https://github.com/detroit-labs/liftoff-backend</a></li><li><a href="https://git.rockfin.com/LiftOff/liftoff-backend-master">https://git.rockfin.com/LiftOff/liftoff-backend-master</a></li></ul> | [202217](http://core/app/202217) | Detroit Labs: Ed Goff | IP | IP | <br> | <br> | <br> | <br> | <br> | <br> | **[End-To-End](https://git.rockfin.com/LiftOff/E2E-Testing) (Over-All LO)** | <br> | <br> | <br> |
| Rocket Pro (Co-Pilot): iOS<br><ul><li><a href="https://github.com/detroit-labs/liftoff-ios">https://github.com/detroit-labs/liftoff-ios</a></li><li><a href="https://git.rockfin.com/LiftOff/liftoff-ios-master">https://git.rockfin.com/LiftOff/liftoff-ios-master</a></li></ul> | [202816](http://core/app/202816#info) | Detroit Labs: Ed Goff | IP | IP | <br> | <br> | <br> | <br> | <br> | <br> | <br> | <br> | <br> | <br> |
| Rocket Pro (Co-Pilot) Android<br><ul><li><a href="https://github.com/detroit-labs/liftoff-android">https://github.com/detroit-labs/liftoff-android</a></li><li><a href="https://git.rockfin.com/LiftOff/liftoff-android-master">https://git.rockfin.com/LiftOff/liftoff-android-master</a></li></ul> | [202817](http://core/app/202817#info) | Detroit Labs: Ed Goff | IP | IP | <br> | <br> | <br> | <br> | <br> | <br> | <br> | <br> | <br> | <br> |
| Conversations-API (Brain) | [202069](http://core/app/202069) | Brain: Pratima Naik | [ConversationsAPI](https://circleci.hal.computer/gh/LiftOff/conversations-api)<br> | Done: [BrainConversationsAPI](https://sonarqube.rockfin.com/dashboard?id=QL.202069) | More | More | More | More | More | <br> | <br> | <br> | <br> | <br> |
| Content-Trail Q&A (Brain) | [202191](http://core/app/202191#info) | Brain: Pratima Naik | [QuestionTrailsContentAPI](https://circleci.foc.zone/gh/LiftOff/workflows/question-trails-content-api)<br> | Done: [BrainContentAPI](https://sonarqube.rockfin.com/dashboard?id=QL.202191) | More | More | More | More | More | <br> | <br> | <br> | <br> | <br> |
| Income Qualifier Service (back-end service)<br><br>[http://shorty/veritasiq](http://shorty/veritasiq)<br> | <br> | <br>Veritas: <ac:link><ri:user ri:userkey="8a89036051b6b6d901521281d405000b"></ri:user></ac:link> / <ac:link><ri:user ri:userkey="ff80808149cea7df0149d30f11f50007"></ri:user></ac:link><br> | <br> | <br> | <br> | [https://git.rockfin.com/qualityengineering/IQPassiveTestSuite/](https://git.rockfin.com/qualityengineering/IQPassiveTestSuite/) | <br> | [Load Test](https://confluence/display/IQ/Load+Test) | <br> | <br> | Rules | <br> | <br> | .NET Core/Docker<br><br>Reviewers: Veritas Engineers<br><br>Incomes Types:<br><ul><li>Passive = Done</li><li>Employment = In-Progress</li><li>Self-Employment = TBD</li><li>WVOE = TBD</li><li>WorkNumber = TBD</li></ul> |
| Property Qualifier Service (Veritas)<br><br>Property Qualifier Service (back-end service)<br><br>[http://shorty/veritaspq](http://shorty/veritaspq)<br><br><br> | <br> | <br>Veritas: <ac:link><ri:user ri:userkey="8a89036051b6b6d901521281d405000b"></ri:user></ac:link> / <ac:link><ri:user ri:userkey="ff80808149cea7df0149d30f11f50007"></ri:user></ac:link><br> | <br> | <br> | <br> | TBD | <br> | <br> | <br> | <br> | Rules | <br> | <br> | <br> |
| Assets Qualifier Service (Veritas) | <br> | <br>Veritas: <ac:link><ri:user ri:userkey="8a89036051b6b6d901521281d405000b"></ri:user></ac:link> / <ac:link><ri:user ri:userkey="ff80808149cea7df0149d30f11f50007"></ri:user></ac:link><br> | <br> | <br> | <br> | TBD | <br> | <br> | <br> | <br> | Rules | <br> | <br> | <br> |
| Credit Qualifier Service (Veritas) | <br> | <br>Veritas: <ac:link><ri:user ri:userkey="8a89036051b6b6d901521281d405000b"></ri:user></ac:link> / <ac:link><ri:user ri:userkey="ff80808149cea7df0149d30f11f50007"></ri:user></ac:link><br> | <br> | <br> | <br> | TBD | <br> | <br> | <br> | <br> | Rules | <br> | <br> | <br> |
| Enrichment Action - Property Data | 202960 | Flux Capacitor: Karen Fannin | propertyentity-listener | Yes | Yes | [https://git.rockfin.com/LiftOff/LiftOffTests/tree/master/LiftOff.Tests.EA](https://git.rockfin.com/LiftOff/LiftOffTests/tree/master/LiftOff.Tests.EA) | More | <br> | <br> | <br> | <br> | <br> | <br> | <br> |
| Enrichment Data Integration Svc - Person Data | 202979 | Flux Capacitor: Karen Fannin | edis-propertyhub-api | Yes | Yes | [https://git.rockfin.com/LiftOff/LiftOffTests/tree/master/LiftOff.Tests.EDIS](https://git.rockfin.com/LiftOff/LiftOffTests/tree/master/LiftOff.Tests.EDIS) | <br> | <br> | <br> | <br> | <br> | <br> | <br> | <br> |
| Enrichment Action - Loan Data | 202963 | Flux Capacitor: Karen Fannin | ea-loanentity-listener | Yes | Yes | <br> | <br> | <br> | <br> | <br> | <br> | <br> | <br> | <br> |
| Enrichment Data Integration Svc - Loan Data | 202981 | Flux Capacitor: Karen Fannin | edis-loanentity-api | Yes | Yes | <br> | <br> | <br> | <br> | <br> | <br> | <br> | <br> | <br> |
| Enrichment Action - Credit Data | 202964 | Flux Capacitor: Karen Fannin | ea-creditentity-listener | Yes | Yes | <br> | <br> | <br> | <br> | <br> | <br> | <br> | <br> | <br> |
| Enrichment Data Integration Svc - Credit Data | 202982 | Flux Capacitor: Karen Fannin | edis-credit-data-api | Yes | Yes | <br> | <br> | <br> | <br> | <br> | <br> | <br> | <br> | <br> |
| Enrichment Evaluator API | 202958 | Flux Capacitor: Karen Fannin | enrichment-evaluator-api | Yes | Yes | <br> | <br> | <br> | <br> | <br> | <br> | <br> | <br> | <br> |
| <br> | <br> | <br> | <br> | <br> | <br> | <br> | <br> | <br> | <br> | <br> | <br> | <br> | <br> | <br> |
| <br> | <br> | <br> | <br> | <br> | <br> | <br> | <br> | <br> | <br> | <br> | <br> | <br> | <br> | <br> |
| <br> | <br> | <br> | <br> | <br> | <br> | <br> | <br> | <br> | <br> | <br> | <br> | <br> | <br> | <br> |
| <br> | <br> | <br> | <br> | <br> | <br> | <br> | <br> | <br> | <br> | <br> | <br> | <br> | <br> | <br> |


Note: All apps are containerized (Docker) unless otherwise noted

Note: All code / test code - will be code reviewed (Pull-Requests process)

Note: All applications are automatically deployed using CI/CD &gt; Through CircleCI, unless otherwise denoted

\*\*Note: Various other applicable testing: E2E, User Interface, DMN, BPM, Rules, etc.



#### Overall Testing Approach / Considerations:

- Unit Testing
- Integration Testing (APIs)
- UI/UX Testing
- End-To-End Workflows Testing
- Security Testing
- Load/Performance Testing

