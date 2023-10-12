
<ac:structured-macro ac:name="toc" ac:schema-version="1" ac:macro-id="0ff9fad9-d801-41d2-bba6-f36f6bafc4e1"></ac:structured-macro>

# <u>TEST</u>

## **Test - Person and GCID**

<ac:link><ri:page ri:space-key="LO" ri:content-title="Person Entity Enrichment"></ri:page></ac:link>


| FirstName | LastName | SSN | GCID | DOB | Client Address | [Loan Numbers](https://confluence/display/LO/OP+Test+Data#OPTestData-Loans) | Credit Report | Comments |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Alice | Firstimer | 991-91-9991<br> | 62641955<br> | 1960-05-01 | 9991 Warford Street<br>Dawson<br>IA<br>50066 | 8594181043 | [Sample Individual Credit Pull](http://creditv2analyzertest/api/v1/AnalyzerReports?creditRequestId=0&amp;requestingSystem=Brain&amp;analyzerReportFormat=BrainFilePlusAnalyzer&amp;CreditRequestGuid=894e0110-3466-11e9-ac4c-005056af3ab6)<br><br>[Credit Service Log](http://xberttest/applications/CreditV2/CreditRequestHistory.aspx#/?GUID=894e0110-3466-11e9-ac4c-005056af3ab6)<br><br>Note: this goes to out to the vendor's test system<br> | <br> |
| Alice | Firstimer | 911-11-1143<br> | 24769830<br> | 1960-05-01 | 9991 Warford Street<br>Dawson<br>IA<br>50066 | <br> | [Sample Credit Report](http://creditv2test/CreditViewer?CreditRequestGuid=032a9450-5a26-11e9-8dd6-005056af3ab6&amp;requestingSystem=Xbert) (html)<br><br>Note: this is a QL internal test case, copied from vendor report above, more reliable<br> | <br> |
| John<br><br>Mary<br> | Homeowner<br><br>Homeowner<br> | 999-40-5000<br><br>500-22-2000<br> | <ac:inline-comment-marker ac:ref="3d785426-8ca9-46de-a2a3-db1028284a46">15875134</ac:inline-comment-marker><br><br><ac:inline-comment-marker ac:ref="3d785426-8ca9-46de-a2a3-db1028284a46"><span>15875135</span><br></ac:inline-comment-marker><br> | John: 1962-12-15<br><br>Mary: 1960-12-15<br> | 175 13th Street<br>Washington<br>DC<br>20013 | None | [Sample Joint Credit Pull](http://creditv2analyzertest/api/v1/AnalyzerReports?creditRequestId=0&amp;requestingSystem=Lakewood&amp;analyzerReportFormat=LKFilePlusAnalyzer&amp;CreditRequestGuid=10b6c4c0-3467-11e9-8ed5-005056941d84)<br><br>[Credit Service Log](http://xberttest/applications/CreditV2/CreditRequestHistory.aspx#/?GUID=10b6c4c0-3467-11e9-8ed5-005056941d84)<br> | <br> |
| Nhi | Testco | 000-15-8634<br> | 11346878 | <br> | <br> | <br> | This SSNs will return a credit report<br>(add sample here) | <br> |
| ? | ? | 900-00-0448<br> | 16553617 | <br> | <br> | <br> | This SSNs will return a credit report<br>(add sample here) | <br> |
| ? | ? | 900-00-0456<br> | 15881170 | <br> | <br> | <br> | This SSNs will return a credit report<br>(add sample here) | <br> |
| Todd | Testco | 000-61-5460 | 10658240 | <br> | <br> | <br> | This SSNs will return a credit report<br>(add sample here) | <br> |
| Mary<br><br>John<br> | Homeowner<br><br>Homeowner<br> | 911111137<br><br>911111138<br> | <br> | 1970-01-01<br><br>1969-01-01<br> | 175 13th Street<br>Washington<br>DC<br>20013 | <br> | [Sample Joint Credit](http://creditv2analyzertest/api/v1/AnalyzerReports?creditRequestId=0&amp;requestingSystem=Lakewood&amp;analyzerReportFormat=LKFilePlusAnalyzer&amp;CreditRequestGuid=c2dd2830-4c02-11e9-aeca-005056af3ab6)<br><br>[Credit Service Log](http://xberttest/applications/CreditV2/CreditRequestHistory.aspx#/?GUID=c2dd2830-4c02-11e9-aeca-005056af3ab6)<br> | <br> |
| ? | ? | 900-90-1234 | 62641955 | <br> | <br> | <br> | <br> | <br> |
| ? | ? | 900-90-5678<br> | 2007287933<br> | <br> | <br> | <br> | <br> | <br> |
| John<br><br>Mary<br> | Homeowner<br><br>Homeowner<br> | 911111146<br><br>911111147<br> | 24769830<br><br>24769830<br> | 1960-05-01<br><br>1958-05-01<br> | 175 13th Street<br>Washington<br>DC<br>20013 | <br> | [Joint Credit Report](http://creditv2analyzertest/api/v1/AnalyzerReports?creditRequestId=0&amp;requestingSystem=Lakewood&amp;analyzerReportFormat=LKFilePlusAnalyzer&amp;CreditRequestGuid=c2f0e210-5c7b-11e9-98e4-005056941d84) | <br> |


## 
**Test - Subject Property**

<ac:link><ri:page ri:space-key="LO" ri:content-title="Property Entity Enrichment"></ri:page></ac:link>


| Property Address | PropertyGuid | Property Type | Comments |
| --- | --- | --- | --- |
| 8226 Wilson Dr<br>Omaha<br>NE<br>68127-4606<br> | 124C6DA9-A4B6-4FB5-842F-212018E4C8C7 <br>(Property Hub Test) | Single Family Residence | <br> |
| 536 Ashton Manor Dr<br>Loganville<br>GA<br>30052-5332<br> | 8C5AE4C5-A91A-4702-8123-557999282475<br>(Property Hub Test) | Single Family Residence | <br> |
| 209 E Highland St<br>Tecumseh <br>OK <br>74873-4215<br> | 1A36E420-F6E5-46F9-B786-69947951F854 <br>(Property Hub Test) | Manufactured Home | <br> |


## **Test - Loans**

<ac:link><ri:page ri:space-key="LO" ri:content-title="Loan Entity Enrichment"></ri:page></ac:link>


| Loan Number | [GCID](https://confluence/display/LO/OP+Test+Data#OPTestData-PersonandGCID) | Unpaid Principal Balance | Subject Property Address |
| --- | --- | --- | --- |
| 8594181043 | 24769830 | 0 | 765 Anywhere Street<br>Townsend<br>MA<br>01469 |
| 3333369493 | 62641955 | 94523.81 | <br> |
| 3217388672<br><br><br><br><br><br><br><br>3290791926<br><br><br> | 2007287933<br><br><br><br><br><br><br><br>2007287933<br> | 148335.27<br><br><br><br><br><br><br><br>0<br> | 8226 Wilson Dr<br>Omaha<br>NE<br>68127<br><br><br><br>123 J Fake St<br>Detroit<br>MI<br>48226<br> |




# <u>BETA</u>

## **Beta - Person and GCID**


| FirstName | LastName | SSN | GCID | DOB | Client Address | Loan Numbers | Credit Report | Comments |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Alice | Firstimer | 991-91-9991<br> | <br> | 1960-05-01 | 9991 Warford Street<br>Dawson<br>IA<br>50066 | None | [Credit Analyzer](http://creditv2analyzerbeta/api/v1/AnalyzerReports?creditRequestId=0&amp;requestingSystem=Xbert&amp;analyzerReportFormat=LKFilePlusAnalyzer&amp;CreditRequestGuid=13228bf0-7ca5-11e9-84e8-005056943efc)<br><br>[HTML Report](http://creditv2beta/CreditViewer?CreditRequestGuid=13228bf0-7ca5-11e9-84e8-005056943efc&amp;requestingSystem=Xbert)<br><br>Note: this goes to out to the vendor's test system<br> | <br> |
| Alice | Firstimer | 911111143 | <br> | 1960-05-01 | 9991 Warford Street<br>Washington<br>IA<br>50066 | <br> | [Credit Analyzer](http://creditv2analyzerbeta/api/v1/AnalyzerReports?creditRequestId=0&amp;requestingSystem=Xbert&amp;analyzerReportFormat=LKFilePlusAnalyzer&amp;CreditRequestGuid=db296160-7d62-11e9-be29-005056947895)<br><br>[HTML Report](http://creditv2beta/CreditViewer?CreditRequestGuid=db296160-7d62-11e9-be29-005056947895&amp;requestingSystem=Xbert)<br> | <br> |
| Joey | Gladstone | 911111150 | <br> | 1978-05-02 | 20555 Victor Parkway<br>Livonia<br>MI<br>48152<br> | <br> | [Credit Analyzer](http://creditv2analyzerbeta/api/v1/AnalyzerReports?creditRequestId=0&amp;requestingSystem=Xbert&amp;analyzerReportFormat=LKFilePlusAnalyzer&amp;CreditRequestGuid=4b62c7f0-7d63-11e9-be29-005056947895)<br><br>[HTML Report](http://creditv2beta/CreditViewer?CreditRequestGuid=4b62c7f0-7d63-11e9-be29-005056947895&amp;requestingSystem=Xbert)<br> | <br> |
| John<br><br>Mary<br> | Homeowner<br><br>Homeowner<br> | 911111151<br><br>911111152<br> | <br> | 1960-05-01<br><br>1958-05-01<br> | 175 13th Street<br>Washington DC<br>DC<br>20013<br> | <br> | [Credit Analyzer](http://creditv2analyzerbeta/api/v1/AnalyzerReports?creditRequestId=0&amp;requestingSystem=Xbert&amp;analyzerReportFormat=LKFilePlusAnalyzer&amp;CreditRequestGuid=be055130-7d61-11e9-be29-005056947895)<br><br>[HTML Report](http://creditv2beta/CreditViewer?CreditRequestGuid=be055130-7d61-11e9-be29-005056947895&amp;requestingSystem=Xbert)<br><br>Note: internal test case<br> | <br> |


## **Beta - Subject Property**


| Property Address | PropertyGuid | Property Type | Comments |
| --- | --- | --- | --- |
| 8226 Wilson Dr<br>Omaha<br>NE<br>68127-4606<br> | f539c6a3-474f-43d0-b89b-f820efdc4625<br> | Single Family Residence | <br> |
| 536 Ashton Manor Dr <br>Loganville <br>GA <br>30052-5332<br> | d6a5127c-4343-4feb-846e-f620d9226f96<br> | Single Family Residence | <br> |
| 209 E Highland St <br>Tecumseh <br>OK <br>74873-4215<br> | 5117d6af-d1da-458f-9865-9b90e213835b | Manufactured Home<br> | <br> |


## **Beta - Loans**


| Loan Number | GCID | Unpaid Principal Balance | Subject Property Address |
| --- | --- | --- | --- |
| 3333369493 | <br>```<br>2007734768<br>```<br> | 94523.81 | 3368 CRVSS CRGGK # 3368<br>SCRCSVTC<br>FL<br>34231<br><br>(not in Property Hub)<br> |



