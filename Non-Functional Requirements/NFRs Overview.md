
# Overview

Non-functional Requirements (also sometimes referred to as "Quality Attributes" for our systems/processes) are the overall factors that affect run-time behavior, system design, and user experience.



NFRs represent areas of concern that have the potential for application wide impact across many layers and tiers. Some of these NFRs are related to the overall system design, while others are processes specific to run-time, design-time, or user-centric issues. The extent to which the application possesses a desired combination of NFRs such as documentation, usability, performance, reliability, and security indicates the success of the design and the overall quality of the software application.



When designing applications to meet any of the NFR requirements, it is necessary to consider the potential impact on other non-functional requirements. Teams must analyze the tradeoffs between multiple quality attributes. The importance or priority of each NFR may differ from system to system.



The list below describes the NFRs that teams will consider when designing their applications. Use the table below to gain an understanding of how NFRs map to system and application quality factors.



Then use the sections containing key guidelines for each of the NFRs to understand how that attribute has an impact on design/implementation, and then determine the decisions your team must make to address these NFRs. Keep in mind that the list of NFRs in this table are not exhaustive, but provides a good starting point for asking appropriate questions about your architecture.



# The Plan For NFRs\*\*

The following table describes the NFRs we have implemented currently, and some that we are planning for in the future. This table categorizes the NFRs  in four specific areas linked to <u>Design</u>, <u>Runtime</u>, <u>System</u>, and <u>User Qualities</u>. Use this table to understand what each of the NFRs mean in terms of your applications.




| Category<br> | NFR Candidates<br> | Description<br> |
| --- | --- | --- |
| **Design Qualities**<br> | *Conceptual Integrity*<br> | Conceptual integrity defines the consistency and coherence of the overall design. This includes the way that components or modules are designed, as well as factors such as coding style and variable naming.<br> |
| *Maintainability*<br> | Maintainability is the ability of the system to undergo changes with a degree of ease. These changes could impact components, services, features, and interfaces when adding or changing the functionality, fixing errors, and meeting new business requirements.<br> |
| *Reusability*<br> | Reusability defines the capability for components and subsystems to be suitable for use in other applications and in other scenarios. Reusability minimizes the duplication of components and also the implementation time.<br> |
| ***Documentation*** | Architecture is about the elements of a system’s design, the relationships between those elements, and the degree to which they can be decoupled. There is a wealth of architectural information about a system that needs to be communicated that when put on one diagram would be too complicated. |
| *Extensibility* | Extensibility is a design principle where implementation takes future needs into consideration. Extensibility is the ability of a system to be changed or updated easily, by leveraging configuration modifications, feature flags, etc. This makes adding functionality easier, by adding new changes on top of pre-existing systems or infrastructure. |
| **Run-time Qualities**<br> | *Availability*<br> | Availability defines the proportion of time that the system is functional and working. It can be measured as a percentage of the total system downtime over a predefined period. Availability will be affected by system errors, infrastructure problems, malicious attacks, and system load.<br> |
| *Interoperability*<br> | Interoperability is the ability of a system or different systems to operate successfully by communicating and exchanging information with other external systems written and run by external parties. An interoperable system makes it easier to exchange and reuse information internally as well as externally.<br> |
| ***Performance***<br> | Performance is an indication of the responsiveness of a system to execute any action within a given time interval. It can be measured in terms of latency or throughput. Latency is the time taken to respond to any event. Throughput is the number of events that take place within a given amount of time.<br> |
| *Reliability*<br> | Reliability is the ability of a system to remain operational over time. Reliability is measured as the probability that a system will not fail to perform its intended functions over a specified time interval.<br> |
| *Scalability*<br> | Scalability is ability of a system to either handle increases in load without impact on the performance of the system, or the ability to be readily enlarged.<br> |
| ***Security***<br> | Security is the capability of a system to prevent malicious or accidental actions outside of the designed usage, and to prevent disclosure or loss of information. A secure system aims to protect assets and prevent unauthorized modification of information.<br> |
| **System Qualities**<br> | ***Monitoring/Alerting**(Supportability)*<br> | Monitoring/Alerting (Supportability) is the ability of a system to provide information helpful for identifying and resolving issues when the system fails to work correctly.<br><br>Monitoring/Alerting (Supportability) for a system defines how easy it is for system administrators to manage/watch an application (as it is running), usually through sufficient and useful instrumentation exposed for use in monitoring systems, and for debugging and performance tuning.<br> |
| ***Testability (Code Coverage)***<br> | Testability is a measure of how easy it is to create test criteria for the system and its components, and to execute these tests in order to determine if the criteria are met. Good testability makes it more likely that faults in a system can be isolated in a timely and effective manner.<br> |
| **User Qualities**<br> | *Usability*<br> | Usability defines how well the application meets the requirements of the user and consumer by being intuitive, easy to localize and globalize, providing good access for disabled users, and resulting in a good overall user experience.<br> |




\*\* NFRs in **BOLD** are implemented/being tracked currently


