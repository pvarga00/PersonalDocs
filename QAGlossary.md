TERM	DEFINITION
- Acceptance Criteria (AC)	Acceptance Criteria – Ensure that a Requirement can be validated [proved to be working as expected] and is testable

- Agile	Agile Process – A collection of values and principles that encourage a certain type of project team behavior: focus on value generation and collaboration.
  - The main tenet of Agile is to always, iteratively, deliver incremental benefit (value)
  - (See: http://agilemanifesto.org/)

- Automation / Automated Testing	Test automation typically uses special software (separate from the software being tested) to control the execution of tests, and compares the actual outcomes with expected/predicted outcomes. Test automation can automate the repetitive but necessary tasks, or testing that would be difficult to perform manually. Test automations use code to simulate the manual testing process by using machines to perform the same manual validating tasks/processes repeatedly and consistently

- Beta (Pre-PROD) Environment	“Pre-PROD” environment that is as close to PROD as possible. Very stable for testing, and should contain data as close to real as possible, and soon-to be released functionality. System and Integration testing typically occurs here. Regression testing happens here
Black Box Testing	Specification-based tests are also called “black-box” tests because, like a black-box, you cannot see anything inside. You know nothing about the architecture, design, or coding of the system. Specification-based tests are based solely on the functionality and requirements in system specifications and other items in the test basis. You can create models or business scenarios from the software requirements and then create test cases from the scenarios

- BSRD	Business and System Requirements Document – The physical document that lays out what the functional requirements for a system are
Build Verification (Smoke) Testing [BVTs]	BVTs are a set of tests run on each new build to verify that the product/application is functional before releasing it to the QA team for testing
Business Function Testing	Verify feature meets business acceptance criteria.

- CMMI	Capability Maturity Model Integration [think: process validation based on how well the process is performing] – A process to help to improve any process
Configuration Testing	Tests performed on server OS, middleware, network, email, mainframe DLLs, etc.
Defect, Incidence, or Bug	Deviation or non-conformance from agreed upon requirement or function. A flaw that may cause a feature, component, or system to not perform its required function – or to perform it incorrectly. Examples: an incorrect program code statement or condition; an invalid data definition formation in a database; an incorrect system design interface

- DEV (Local) Environment	Place where engineers make code changes to frequently, checking incrementally built functionality. This environment is highly unstable and is used for testing newly made changes. Unit testing is performed here

- End-to End (Life-cycle) Testing	Tests user scenarios and various path conditions by verifying that the system runs and performs tasks accurately with the same set of data from beginning to end, as intended

- Error or Mistake	A human action that produces an incorrect result. Examples: a business analyst misinterpreting a user’s request for a feature; a programmer mistyping a program code statement; a system designer not understanding a requirement

- Exploratory Testing	Testing without a specific/structured plan, simultaneously learning, designing, and capturing test results. This is a style of software testing that emphasizes the personal freedom and responsibility of the individual tester to continually optimize the quality of their work by treating test-related learning, test design, test execution, and test result interpretation as mutually supportive activities that run in parallel throughout the project

- Failure	A deviation of a feature, component, or system from its expected result, service, or delivery. Examples: A web form storing incorrect data in a database; a report containing erroneous information; a program computing an incorrect value

- Integration Testing	Tests that validate the orchestration between the user interface and supporting services and applications.
Load / Volume Testing	Verifies applications and services can process large amounts of data / transactions.

- LoadRunner	HP LoadRunner is an automated performance and test automation product from Hewlett-Packard for application load testing: examining system behaviour and performance, while generating actual load.

- Maintenance / Regression (Re-Testing) Testing	Maintenance (Regression) testing ensures that no pre-existing functionality has been altered or sacrificed in the process of adding new code and functionality into the target environment. Regression Testing covers all areas of existing functionality in the target application

- Manual Testing	Manual testing is the process of manually testing software for validation and potentially finding defects. A QA typically impersonates the role of a client user, testing the features of an application, to ensure correct behavior. To ensure completeness of testing, the tester often follows a written test plan that leads them through a set of important test cases

- Metrics	Measurable data and information collected to aid in decision making, determine the status of project, and to provide future predictability of trends

- MS VSTS/TFS	Microsoft Visual Studio Team System and Team Foundation Server – A tool that is a lot of things: developers write code in it, source code / document repository, team collaboration tool, etc. – with built in tracking of the history of the files within it

- MTM	Microsoft Test Manager – A tool used for organizing testing activities

- Negative Testing	Negative testing is conducted throughout all of phases of testing, to determine how an application or system behaves when given unexpected input. A negative test is designed to validate if the system will handle the invalid input gracefully, or fail unexpectedly

[Examples: Invalid strings (alphas in numeral fields), negative numbers, bad data, etc. – Using invalid data/processes trying to “break the system”]

- Performance Testing	Tests that verify response time and concurrency for supporting systems / applications

- Permission and Privacy (Security) Testing	Security testing for a system may include detection of threats and identification of vulnerabilities for unauthorized intrusion into the system, appropriate privileges granting, and data segregation and data encapsulation.

  - Additional security testing includes testing of data file transfers, storage of files, and ensuring that personal and confidential information is safeguarded. (Personally Identifiable Information “PII”)

  - Personally Identifiable Information (PII)	Personal and confidential information about a person. Examples include: SSN, address, phone numbers, etc.

- PIR	Problem Incident Reporting – Process for logging bugs and issues (any deviation of software behavior from expectations)

- PROD (Production) Environment	This is “released” version of the software that is used by our client users

- QA	Quality Assurance – Process identifying the types of testing desired and related implementation processes

- QAM	Quality Assurance Management. QAM includes the management of: Quality Planning (QP), Quality Assurance (QA), and Quality Control (QC) processes

- QC	Quality Control – Process of using control policies to manage and monitor testing activities – ensuring quality (of both software and processes)

- QP	Quality Planning – Process for planning the testing activities for a project. Determining testing objectives, processes, and procedures

- QTP	HP Unified Functional Testing (UFT) software, formerly known as HP QuickTest Professional (QTP),provides functional and regression test automation for software applications and environments.HP Unified Functional Testing can be used for enterprise quality assurance.

- Quality Center	HP Quality Center is quality management software offered from the HP Software Division of Hewlett-Packard with many capabilities acquired from Mercury HP Quality Center is quality management software offered from the HP Software Division of Hewlett-Packard with many capabilities acquired from Mercury Interactive Corporation. HP Quality Center offers software quality assurance, including requirements management, test management and business process testing for IT and application environments.HP Quality Center is a component of the HP Application Lifecycle Management software solution set.

- RC	Release Candidate – Often the product in BETA is a “release candidate” for going to PROD

- RTM	Requirements Traceability Matrix – A physical cross-referencing representation document that ensures that every Requirement has Acceptance Criteria, which also has corresponding Acceptance Tests

- Security Testing	Tests that look for vulnerabilities and weaknesses that include network (resources and policies), system software (operating system, database, and software), client-side application (browser), server-side application security (code can fend off attack).

- SIT	System and Integration Testing ensures that different components, systems, and the product as a whole can interoperate (work cooperatively with one another or other products)

- Stress Testing	Tests low resources (memory, space) and contention for shared resources (system, database, network)

- TDD	Test Driven Development – Process of writing tests for Acceptance Criteria (based on Requirements) and then implementing code to make sure the tests pass

- Test (Staging) Environment	Slightly more stable, used for testing the interactions between modules. Build and initial product verification occurs here, testing the system as a whole, and the interactions between modules. System and Integration testing (SIT) occurs here

- Test Basis	The test basis is all sources of information from which the requirements of a system can be derived and documentation on which to base test cases. If a document can be amended only by way of formal change procedure, then the test basis is called a “frozen test basis.”

- Test Case	Set of conditions used to determine if a requirement or scenario is satisfied.  Test Cases can be performed manually or scripted to run automatically.  Test cases are documented with a specific sequence of events, designed to test variations of a requirement or criteria.  The outcome is recorded regardless of pass or fail. Test cases are planned, created, collated, executed, and tracked. A good for accomplishing this is the Microsoft Test Manager (MTM) tool

- Test Data	Data used specifically to exercise a Test Case.  There can be several sets of Test Data for any one Test Case.  To meet Test Case needs, Test Data could be real or manufactured, or a combination of both
Test Plan	A logical high level collection of related Test Suites

- Test Suite	Test Suites are a collection of Test Cases, grouped by like functionality or iteration, and are used to organize test cases into executable runs within MTM

- Testware	Testware consists of all the artifacts, (plans, documentation, test cases, procedures, files, databases, environments, and any software or utilities), that are created during the test planning, design, and execution activities. Preserving this testware is an essential element of test closure and often pays dividends when it is needed again (reusability)

- UAT	[User] Acceptance Testing – A testing activity that verifies Acceptance Criteria.

UAT refers to the final testing effort conducted by the client, prior to implementation of the business solution (“pushing to PROD”). UAT determines whether or not the system satisfies the client user’s needs and expectations -- if the system owners will accept the system into operation for productive use
Unit (Component) Testing	Unit tests are written in code and test components of coded features.

Typically created by engineers to ensure that a function or method in code is functional
User Interface Testing	User interface testing is the process of testing a product's graphical user interface to ensure it meets requirements.

- V-Model	The V-Model is a sequential development life-cycle model used to illustrate the relationships between development and testing activities. The test process depends on the corresponding development lifecycle process that a company uses. Because we test what developers create, test and development processes must be planned and managed together to be most effective

- Waterfall / Traditional	Sequential process that defines how to deliver software in a staged manner. Stages or phases are: Conception, Initiation (Planning), Analysis, Design, Construction, Testing, Production/Implementation, and Maintenance

- White Box Testing	Structure-based tests are created from the software’s architecture, design, and the program code. Structure- based tests are also called “white-box” tests - although the term “clear-box” or “glass-box” would be more appropriate. When designing structure-based tests, you use the architecture, design, and code to design tests. Structure-based test designs use knowledge about the system’s internals rather than the system’s requirements

- Work Item (WI)	A work item is a database record created within Visual Studio Team Foundation Server (VS/TFS) to record the definition, assignment, priority, and state of work. Work items are also used to track, monitor, and report on the development of a product and its features
