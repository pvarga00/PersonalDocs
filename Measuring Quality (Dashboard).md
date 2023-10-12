


QUOTE: How can we get better, if we don't first measure where we are now, and by how we much are improving?

# VENDOR:

## <ac:link><ri:page ri:space-key="SONAR" ri:content-title="SonarQube Documentation"></ri:page><ac:plain-text-link-body><![CDATA[SONAR]]></ac:plain-text-link-body></ac:link> - Implementation <ac:link><ri:page ri:content-title="TD" ri:space-key="IC"></ri:page><ac:plain-text-link-body><![CDATA[TBD]]></ac:plain-text-link-body></ac:link>







# HOMEGROWN (**Abandoned**):

**<u>PROJECT PROPOSAL &lsquo;QUALITY METRICS&rsquo; SUMMARY:</u>**

We want to have a reporting system on a “project’s quality”, for the purpose of continuous improvement.



We will make use of unit tests and reported metrics in an aggregated manner, displayed in the [Core](http://core/) website.



Quality metrics will be automatically generated from build servers.

*Note: There will be NO manual process involved.*





**<u>Intended Audience:</u>**

Karim Taleb, Steve Brennan, Keith Elder



**<u>Project Champions:</u>**

Peter Varga, Alex Islas-Montantes, Kevin Price, Matt Nagi



***<u>PROPOSAL:&nbsp; </u>***

***A web page displaying quality metrics for every project code repository/deployable:***

-          *Latest "Source" build Number*

-          *Latest "Source" build State*

- *Built (compiled/built + build verification tests all passed)*
- *Failed (broken compile or build verification tests failed)*


-          *Code coverage percentage*

- *# unit tests passing*
- *# unit tests failing*
- *Total # unit tests*


-          *[Cyclomatic Complexity](http://en.wikipedia.org/wiki/Cyclomatic_complexity)*

-          *[CRAP index](http://www.artima.com/weblogs/viewpost.jsp?thread=210575)*

-          *Lines of Code (kLOC) [?]*





***<u>BENEFITS:</u>***

- Clarity / transparency of project state
- Measurements displayed, for improvements of ALM/development processes




**<u>Requirements:</u>**

- Automatically generate data (from build server)
- Code Coverage Info
- Build Info
- Project code has unit tests
- Project “state/health” is calculated based on CRAP index




**<u>In Scope:</u>**

- .NET projects
- “Open Source” projects
- PHP, JS, HTML, etc.




**<u>Out of Scope:</u>**

- 4GL / Progress projects
    - *NOTE: Need to determine a solution for these projects in the future*






**<u>Workflow:</u>**

<ac:image><ri:attachment ri:filename="QualityMetricsWorkflow.png"></ri:attachment></ac:image>



***<u>Implementation Proposal:</u>***

See attached: “Project Metrics – BigBoard.xlsx” for details





**<u>Stuff to Figure Out:</u>**

- Who (resources) will work on what / when
- What additional data to get (if any)
- How to get the data (from build servers: TFS / Travis)
- Data format (neutral file / XML / fields)
- Core API to determine common file format to use
- Storing the data (Core to save)
- Displaying the data (from Core)
- Historic tracking/viewing of data (histograms / trends)




**<u>Intended Timeline for Feedback:</u>**

Please respond with any questions/feedback to the group by: 7/18/2014 – Otherwise, we’ll proceed as planned.

*Note: We can always change the implementation / details later on – but as this is the “rough cut” (Version1.0) of the plan – changes are more easily made earlier on...*


