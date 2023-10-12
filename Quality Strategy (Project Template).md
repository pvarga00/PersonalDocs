# Quality Strategy (Project Template)

## Test Data

## Test Plan(s)

## Environments

## Technologies

## Roles & Responsibilities (RACI)
Teams & Team Members / Release Trains / Stakeholders


## Integration Testing Capability
(specifically: API testing)


## Code Reviews


## Static Code Analysis


## Documentation


## Unit Testing Capability


## Load/Performance Testing 


## UI Testing Capability


## E2E System Testing 


## Test Case and Defect Management 


## Security Testing


## Penetration Testing


## HA/DR Testing


## Site Reliability Testing


## Synthetic User Testing


## Accessibility Testing









### Sample Example::
### Overview: The XXX Team is going to build XXXX.

### Objective: The purpose of this document is to describe what quality activities will get done and how it going to accomplish during development of XXXX.

### Test Approach:
The testing of The Answer application will follow The testing Pyramid to write automation tests. Team will maintain approximately 85% of unit tests, 10% of Integration tests and 5% of UI tests.

Different types of testing will be done during XXXX application development based on priority.

### Types of Testing:
- Unit Testing: xUnit framework will be use to develop unit tests. Unit tests will develop with application code to validate individual blocks of application code. All new code will have 90% unit tests code coverage. All unit tests should passed before push the code to Test environment.
How: Software engineer will write the Unit Test along with the development code.  

- Integration Testing (API): MSTest framework will be use to develop integration tests. Integration tests (Service calls tests) will be develop to verify Get/Post/Put/Delete methods.
Service Virtualization: The Answer application will integrated with AMP and Gracie applications. Service Virtualization will allow teams to simulate AMP and Gracie environments.
How: Software Quality Engineer will set up Mountebank for mocking framework.

- UI Testing: Automated UI tests will be develop to verify The Answer UI. Selenium and MSTest framework will be use to write different UI tests.
- Smoke Testing: Automated tests will be develop to test the application to decide if a build is stable enough to proceed with further testing
- Functional Testing: Automated and manual testing will be perform to verify The Answer UI.
- Exploratory Testing: Manual exploratory testing can be performed based on domain knowledge and experience where and what conditions the system might behave unexpectedly.
- End to End Regression Testing: Automated tests will be develop to verify end to end functionalities.
How: Software Quality Engineer will develop the UI automation tests.
- Performance Testing: The Apache JMeter application is open source tool, can be used to determine how a system performs in terms of responsiveness and stability under a particular workload. We will analyze later and decide to perform performance testing on The Answer application.
- Load Testing: Load Test team will use Load Runner tool to determines a system's performance under real-life load conditions. We performed the load tests on CMS non-prod environment. We will be performing the load tests on The Answer site after functional and end to end regression testing.
How: Team Impact will perform Load Testing of CMS and DSS (Site).
- Security Testing:
  - Code Level: Snyk can be used to automatically identify security vulnerabilities in the code during build process.
How: Software Engineer will configure Snyk inside the code and get security vulnerabilities report
  - Application Level: App Spider can be used to scan the application to identify security vulnerabilities at application level.
How: Software Quality Engineer will install App Spider tool and run security vulnerabilities regularly.
- Penetration Testing: Security team will be performing this test to find security vulnerabilities that an attacker could exploit.
- User Acceptance Testing: Business users will be performing User Acceptance Tests ensure user needs are satisfied. 
- Software Compatibility Testing: 
- Browser Compatibility Testing: The Answer application will be verify on both IE and chrome. 
- Operating Systems: The Answer application will be verify different Operating Systems like Window and Mac.
- Recovery Testing: Recovery Testing can be perform how well an application is able to recover from crashes, server failure and other similar problems. Ex. Failure of EC2 instances.

- CI/CD pipeline: The Answer application will have automated deployment 

- Static Code Analysis: Sonar, web based code quality analysis tool will be use to implement static code analysis. Platinum Quality gate will be configure on sonar to analyse the code coverage

- Quality Gates: Certain quality criteria might be used to move code from one environment to other.
  - Unit Tests
  - Sonar Quality Gates
  - Code Review
- Integration Tests
- Smoke Tests
- End to end regression tests
- Code Review (Process): ESLint will be used to make code more consistent and avoiding bugs.

- Deployment Workflow: Unit Tests → Sonar Analysis → Publish build to HAL → Deploy to Test → Integration Tests → UI Smoke Tests → UI End to End Regression Tests → Deploy to Beta →  Integration Tests → UI Smoke Tests → UI End to End Regression Tests → Deploy to Prod → Smoke Tests
- Environments: Test, Beta and Prod

- Tools and Techniques: C#.Net, xUnit for Unit Testing, Snyk, App Spider, MSTest for Selenium and API testing, Load Runner



## Additional Links/Considerations:
- [ServiceNow QS](https://rockfin.sharepoint.com/:x:/r/sites/QLRocketTechWorkIntake/Shared%20Documents/ServiceNow%20MVP%20UAT%20Testing/SN_TestingPlan.xlsx?d=w556c75831ed14cb3bdf5a809c2111f7e&csf=1&web=1&e=9v8E7v)
- [MAAS QS](https://rockfin.sharepoint.com/:w:/r/sites/ContinuousQuality/_layouts/15/Doc.aspx?sourcedoc=%7B43D6566D-31C3-4CB2-8B92-0FF0E422FCF4%7D&file=QualityStrategyInMaaS.docx&action=default&mobileredirect=true&wdOrigin=TEAMS-ELECTRON.p2p.bim&wdExp=TEAMS-CONTROL&wdhostclicktime=1643660086170&cid=04bba0e7-1c04-450e-93b2-9f3ab9473fe9)
- [MAAS QS v2](https://rockfin.sharepoint.com/:w:/r/sites/ProjectMASS/_layouts/15/Doc.aspx?sourcedoc=%7B89DD1D93-DC93-4324-915D-C06A5F7FA09E%7D&file=QualityStrategyInMaaS.docx&action=default&mobileredirect=true)
- [RedBird](https://git.rockfin.com/pvarga/PersonalDocs/tree/master/Rocket%20Bird%20E2E%20Run%20Book)
- [LiftOff (All Docs)](https://git.rockfin.com/pvarga/PersonalDocs/tree/master/LiftOff)
- [LiftOff (Strategy)](https://git.rockfin.com/pvarga/PersonalDocs/blob/master/Quality%20Strategy.md)
- [Quality Driver Playbook How To Ensure a Successful ProgramProject](https://git.rockfin.com/pvarga/ConfluenceDump/blob/cfcdf02ae6c6fdbec6947960724793dd4e458720/gen-docs%5Cdocs%5CQuality%20Driver%20Playbook%20How%20To%20Ensure%20a%20Successful%20ProgramProject.md)
- [Quality Checklist (XLS)](https://rockfin.sharepoint.com/:x:/s/ClientTechnology-QAPOD/EWNggc9LvedDvGqaIIR7xU4B_jezqp89hTVldo_rGKxOQg?e=dupzVl)
