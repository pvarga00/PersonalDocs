
NOTIONAL/HIGH LEVEL GOALS ONLY FOR DISCUSSION

TEST - [https://rocketprohim-test.docker.foc.zone](https://rocketprohim-test.docker.foc.zone/ "https://rocketprohim-test.docker.foc.zone/")

BETA - [https://rocketprohim-beta.docker.foc.zone](https://rocketprohim-beta.docker.foc.zone "https://rocketprohim-beta.docker.foc.zone")



<ac:structured-macro ac:name="toc" ac:schema-version="1" ac:macro-id="4111c45d-e050-467c-9e2e-bb7914cd5bf9"></ac:structured-macro>

# **Demo #1: Failed client pre-screening, single client**

Requires: Checklist item, data exception, and topic configuration for SA1 only; Q&A screen type, occupancy type derivation, property type derivation, GCID enrichment, loan hub enrichment, "thinking like a banker" algorithm, Mortgage Solutions integration

Test data set:


| **Topic**<br> | **Value(s)**<br> | **Notes**<br> |
| --- | --- | --- |
| ClientIdentifyingInfoTopic<br> | Name: Danny Tanner<br><br>SSN (**Test**): 900-90-1234 <br>SSN (**BETA):** 900-90-1235<br><br>Married = Yes<br><br>Spouse on loan? = No<br> | **Enrichment gump:** We identified that Danny Tanner was a previous QL client by his SSN with **GCID enrichment**and stored his GCID it in LOD.<br><br><br><br>Associated GCID: 62641955<br><br>Loan: 3333369493<br> |
| LoanPurposeTopic<br> | Refinance<br> | <br> |
| LoanRefinanceGoalsTopic<br> | Get a lower monthly payment<br> | <br> |
| ConfirmRefinanceLoanInfoTopic<br> | Data about the loan is presented on the screen for review:<br><br>Address (**TEST**): 765 Anywhere Street, Sarasota, FL 34231 (Sarasota County)<br>Address (**BETA**): 3368  CRVSS CRGGK # 3368, SCRCSVTC, FL 34231<br><br>Property type: Condominium<br><br>Loan Number (Test): 3333369493<br><br>Loan Date: 2015-03-03<br><br>Original Loan Amount: 98000.00<br><br>Interest Rate: 3.25%<br><br>UPB: 94523.81<br><br>Monthly Payment: $426.51<br><br>Is this the loan you’re looking to refinance? = Yes<br><br>[Estimated value] = may need to fill in an estimated value manually<br> | **Enrichment gump:**  Using Danny Tanner's GCID, we called **Loan Hub** and retrieved his previously closed loans with QL, including the details of the loan (data points on screen)<br><br>This property is not available in Property Hub.<br><br>Loan Hub did contain a record for this loan<br><br>which did contain all the property information<br><br>except the county.<br><br>Will need to add in Sarasota County<br><br><br><br><br> |
| PropertyOccupancyTopic<br> | Do you live in your home for at least 6 months out of the year? = Yes<br> | Result will be “primary” occupancy type<br> |
| InitialIncomeSurveyTopic<br> | “I don’t have income”<br> | <br> |
| NoAvailableProductOptionsTransition<br> | User sees failure message – end demo here with no user input<br> | <br> |


Last updated: 3/18 – Updated to be a refinance scenario since refi scenarios are currently unsupported past scope area 1 (due to needed changes to LOD data model for LOD-Einstein mappings for subject property dispositioning)

1. User enters client's identifying information, indicates they are married but they do NOT want their spouse on the loan
2. User has a currently serviced loan with QL, so the Loan Hub enrichment finds an existing loan. The property does not exist in property hub, however, so no property GUID is returned.
3. User enters client's intent “refinance”
4. User enters refinance goal “get a lower monthly payment”
5. The user confirms the currently serviced QL loan data enriched from Loan Hub
6. User answers questions to derive the intended occupancy type.
7. User answers initial income survey and indicates "i don't have income"
8. User views failure message (no products available)


# **Demo #2: Outright qualification for at least one product after income and credit review, married client with spouse on loan with manually gathered income data**

Requires: Checklist item, data exception, and topic configuration for both SA1 and SA2; Q&A screen, occupancy type derivation, "thinking like a banker" algorithm, GCID enrichment, joint credit report enrichment, Mortgage Solutions integration

Test data set:


| **Topic**<br> | **Value(s)**<br> | **Notes**<br> |
| ClientIdentifyingInfoTopic<br> | John Homeowner, 911-11-1151, Married? = Yes, SpouseonLoan? = Yes<br><br>Mary Homeowner, 911-11-1152<br> | 4/22: Updated John's and Mary's SSN.<br> |
| LoanPurposeTopic<br> | Purchase<br> | <br> |
| LoanPurchaseInformationTopic<br> | Accepted Offer = Yes<br><br>Contract Purchase Price = $400,000<br><br>Down Payment Amount = $80,000<br> | <br> |
| PropertyAddressIdentifyingInformationTopic<br> | 1111 Quicken Way<br><br>Beverly Hills, CA 90210 (Los Angeles County)<br> | **Enrichment gump:**  Behind the scenes, we'll call **PropertyHub** with the entered address, but since it's made up, we won't get any results back<br><br>Confirmed - this property is not in property hub<br> |
| PropertyOccupancyTopic<br> | Do you plan to live in your new home for at least 6 months out of the year? = Yes<br><br>Do you plan to move into your home within 60 days of closing? = Yes<br> | Occupancy Type will be set to “Primary”<br> |
| CapturePropertyTypeTopic<br> | Does the home have more than one unit? = No<br><br>Are homeowner's association dues required for the home? = No<br><br>Was the home manufactured in a factory and assembled on site? = No<br> | Result will be “SingleFamily” property type<br> |
| InitialIncomeSurveyTopic<br> | What are the current sources of income? Select all that apply:<br><br>John Homeowner = Employment<br> | <br> |
| InitialIncomeSurveyTopic<br> | What are the current sources of income? Select all that apply:<br><br>Mary Homeowner= Employment<br> | <br> |
| CaptureCreditScoreTopic<br> | What is the estimated credit score?<br><br>John Homeowner = 680-739<br> | <br> |
| CaptureCreditScoreTopic<br> | What is the estimated credit score?<br><br>Mary Homeowner = 740+<br> | <br> |
| PostInitialClientScreeningSummary<br> | User clicks “next” to proceed past pre-screening and into income/credit review<br> | <br> |
| CaptureCreditConsentTopic<br> | Consent to pull your credit? = Yes<br><br>John Homeowner<br><br>911-11-1151<br><br>05/01/1960<br><br>175 13th Street<br><br>Washington, DC 20013<br><br>Consent to pull your spouse’s credit? = Yes<br><br>Mary Homeowner<br><br>05/01/1958<br><br>911-11-1152<br><br>175 13th Street<br><br>Washington, DC 20013<br><br><br><br>Do you and your spouse have the same mailing address? = Yes<br> | **Enrichment gump:** with John and Mary's personal information, we're calling **Credit Service** for a joint credit request<br><br>[Credit report (XML)](http://creditv2analyzertest/api/v1/AnalyzerReports?creditRequestId=0&amp;requestingSystem=Xbert&amp;analyzerReportFormat=LKFilePlusAnalyzer&amp;CreditRequestGuid=bdf7bfd0-676c-11e9-add9-005056941d84)<br><br>[Credit report (HTML)](http://creditv2test/CreditViewer?CreditRequestGuid=bdf7bfd0-676c-11e9-add9-005056941d84&amp;requestingSystem=Xbert)<br> |
| <br> | WAIT state<br> | Checklist engine generates a data exception with no associated topic here while waiting for the credit report enrichment – then Checklist Engine resolves the associated data exception when the credit.performedDate in the LOD is not NULL<br> |
| FullIncomeSurveyTopic<br> | What employment income do you have? (Select all that apply)<br><br>John Homeowner : Employer - W2<br> | <br> |
| FullIncomeSurveyTopic<br> | What employment income do you have? (Select all that apply)<br><br>Mary Homeowner: Employer - W2<br> | <br> |
| AddW2EmploymentIncomeTopic<br> | John Homeowner:<br><br>Employer’s name: Joe’s Machine Shop<br><br>Estimated hire date: 1/1/2016<br><br>Rate of Pay: 800.00<br><br>Hourly/Salary: Salary<br><br>Pay Frequency: Twice a Month<br><br>Total Annual Income: $19,200<br><br>Do you receive bonus income with this employer?: No<br><br>Do you receive overtime income with this employer?: No<br> | At this point, TLAB recognizes that this is not enough income to qualify outright for the desired loan amount. TLAB algorithm pops a second instance of the AddW2EmploymentIncomeTopic (below) to ask for more income for the primary borrower<br> |
| AddW2EmploymentIncomeTopic<br> | John Homeowner:<br><br>Do you have additional income from a different employer? = No<br> | At this point, TLAB recognizes that this is not enough income to qualify outright for the desired loan amount. TLAB algorithm pops another instance of the AddW2EmploymentIncomeTopic (below) to start asking about spouse income<br> |
| AddW2EmploymentIncomeTopic<br> | Mary Homeowner:<br><br>Employer’s name: Betty’s Bookkeeping<br><br>Estimated hire date: 1/1/2010<br><br>Rate of Pay: 10000.00<br><br>Hourly/Salary: Salary<br><br>Pay Frequency: Twice a Month<br><br>Total Annual Income: $240000<br><br>Do you receive bonus income with this employer?: No<br><br>Do you receive overtime income with this employer?: No<br><br>Do you receive commission income with this employer?: No<br> | At this point, TLAB recognizes that this is enough combined income to qualify for at least one agency product<br> |
| PreProductSelectionSummary<br> | “We may have some options for you. Almost there!”<br> | End on this screen – no user action required<br> |


Last updated: 3/18 – Updated from a PAL scenario to an accepted offer scenario

1. User enters client's identifying information, indicates they are married and they DO want their spouse on the loan
2. User enters client's intent "purchase"
3. User enters that the client has an accepted offer, enters contract purchase amount, down payment amount
4. User enters subject property address information (property is not present in property hub)
5. User guided to enter intended occupancy type (answers will lead to "primary" determination)
6. User guided to enter property type questions (answers will lead to “single family” determination)
7. User answers initial income survey for both the primary client and spouse (both have employment income)
8. User answers stated credit score question for both the primary client and spouse (both have good to high credit scores)
9. User views success message and clicks button to continue to income and credit review
10. Client does not have a current QL loan so user enters all required data manually to pull credit for both primary client and spouse
11. System pulls joint credit report and the resulting Mortgage Solutions evaluation does not block the client from qualifying, so we move to the next topic
12. Client indicates they refuse to provide consent to enrich their income data
13. User manually adds a single source of employment income manually for the primary client - does not qualify yet based on just this income source
14. User indicates they do not have any more sources of employment income for the primary client
15. User manually adds a single source of employment income manually for the spouse
16. User views success message because they qualify outright for at least one product


# **Demo #3: Qualification for at least one product after running an LTV remedy play, single client with manual income gathering (no enriched income data available)**

Requires: Checklist item, data exception, and topic configuration for both SA1 and SA2; Q&A, screens; occupancy type derivation, "thinking like a banker" algorithm, GCID enrichment, single credit report enrichment, Mortgage Solutions integration, property hub integration (to get GUID)

Test data set:


| **Topic**<br> | **Value(s)**<br> | **Notes**<br> |
| ClientIdentifyingInfoTopic<br> | Alice Firstimer, 911-11-1143, Married? = No<br> | <br> |
| LoanPurposeTopic<br> | Purchase<br> | <br> |
| LoanPurchaseInformationTopic<br> | Accepted Offer = Yes<br><br>Contract Purchase Price = $300,000<br><br>Down Payment Amount = $5,000<br> | <br> |
| PropertyAddressIdentifyingInformationTopic<br> | 8226 Wilson Drive<br><br>Omaha, NE 68127 (Douglas County)<br> | **Enrichment Gump**: With Alice's address, we'll call **PropertyHub** and successfully find a property<br><br>This property exists in property hub as a single family residence with GUID 124C6DA9-A4B6-4FB5-842F-212018E4C8C7<br> |
| PropertyOccupancyTopic<br> | Do you plan to live in your new home for at least 6 months out of the year? = Yes<br><br>Do you plan to move into your home within 60 days of closing? = Yes<br><br><br> | Occupancy Type will be set to “Primary”<br> |
| ConfirmPropertyTypeTopic<br> | Is this the correct property type? = Yes<br> | <br> |
| InitialIncomeSurveyTopic<br> | What are the current sources of income? Select all that apply:<br><br>Alice Firstimer = Employment<br> | <br> |
| CaptureCreditScoreTopic<br> | What is the estimated credit score?<br><br>Alice Firstimer = 680-739<br> | <br> |
| PostInitialClientScreeningSummary<br> | User clicks “next” to proceed past pre-screening and into income/credit review<br> | <br> |
| CaptureCreditConsentTopic<br> | Consent to pull your credit? = Yes<br><br>Alice Firstimer<br><br>05/01/1960<br><br>911-11-1143<br><br>9991 WARFORD STREET DAWSON,  IA   50066<br> | **Enrichment gump:** with Alice's personal information, we're calling **Credit Service** for an individual credit request<br><br>[Credit report](http://creditv2test/CreditViewer?CreditRequestGuid=032a9450-5a26-11e9-8dd6-005056af3ab6&amp;requestingSystem=Xbert)<br> |
| <br> | WAIT state<br> | Checklist engine generates a data exception with no associated topic here while waiting for the credit report enrichment – then Checklist Engine resolves the associated data exception when the credit.performedDate in the LOD is not NULL<br> |
| FullIncomeSurveyTopic<br> | What employment income do you have? (Select all that apply)<br><br>Alice Firstimer: Employer - W2<br> | <br> |
| EstablishDownPaymentMaxTopic | What is the maximum amount of money (including down payment, closing costs, escrow, etc.) you could bring to closing for this loan? = $20,000 | At this point the LTV tags on at least one agency product need to be resolved so that the client qualifies for at least one agency product |
| AddW2EmploymentIncomeTopic<br> | Alice Firstimer:<br><br>Employer’s name: Tesla<br><br>Estimated hire date: 1/1/2016<br><br>Rate of Pay: 5,000<br><br>Hourly/Salary: Salary<br><br>Pay Frequency: Twice a Month<br><br>Total Annual Income: $130,000<br><br>Do you receive bonus income with this employer?: No<br><br>Do you receive overtime income with this employer?: No<br> | NOTE: We are assuming here that the client does not have a DTI issue based on comparing their credit report obligations against their income. If DTI issue exists, we can adjust the salary upward to avoid it if needed.<br> |
| PreProductSelectionSummary<br> | “We may have some options for you. Almost there!”<br> | End on this screen – no user action required<br> |


Last updated: 3/12 - Clarified that the scope is to refuse enriched income data and instead be directed to gather income manually

1. User enters client's identifying information, indicates they are not married
2. User enters client's intent "purchase"
3. User enters that the client has an accepted offer, enters contract purchase amount and down payment amount (enters a very low down payment amount to trigger LTV issue)
4. User enters property address and system enriches property GUID from property hub
5. User guided to enter intended occupancy type (answers will lead to "primary" determination), and confirms the property type (single family) from property hub is correct
6. User answers initial income survey for the primary client (employment income)
7. User answers stated credit score question for the primary client (good credit score)
8. User views success message and clicks button to continue to income and credit review
9. Client does not have a current QL loan so user enters all required data manually to pull credit for primary client
10. System pulls single credit report and the resulting Mortgage Solutions evaluation does not block the client from qualifying, so we move to the next topic
11. There are not property tradelines on the credit report to be dispositioned so we skip this step
12. Client indicates they refuse to provide consent to enrich their income data
13. User is prompted to gather income manually (single employment income source of at least 2 years length)
14. After mortgage solutions request and response, TLAB algorithm sees that there are no deal killers, but that LTV ineligibility tags exist on all agency products. Algorithm determines an LTV remedy play is needed ("Uncertain Down Payment Max" exception and remedy play).
15. User is presented with a message that asks if they would consider adding more down payment; user enters a higher down payment amount. It is enough of an increase that after we call Mortgage Solutions again, the TLAB algorithm recognizes that the LTV ineligibility tag has been resolved on at least one agency product and no additional remedy plays are needed.
16. User view success message because they now qualify for at least one product.


# **Demo #4: Qualification for at least one product after running a DTI play, single client with manual income gathering (no enriched income data available)**

Requires: Checklist item, data exception, and topic configuration for both SA1 and SA2; Q&A screens; occupancy type derivation, "thinking like a banker" algorithm, single credit report enrichment; GCID enrichment; Mortgage Solutions integration, Income Entity enrichment with no data available

Test data set:


| **Topic**<br> | **Value(s)**<br> | **Notes**<br> |
| ClientIdentifyingInfoTopic<br> | Joey Gladstone, 911-11-1150, Married? = No<br> | <br> |
| LoanPurposeTopic<br> | Purchase<br> | <br> |
| LoanPurchaseInformationTopic<br> | Accepted Offer = Yes<br><br>Contract Purchase Price = $300,000<br><br>Down Payment Amount = $60,000<br> | <br> |
| PropertyAddressIdentifyingInformationTopic<br> | 9999 Quicken Way<br><br>Beverly Hills, CA 90210 (Los Angeles County)<br> | **Enrichment Gump**: With Joey's address, we'll call **PropertyHub** but won't find a property since it's made up<br><br>Matt confirmed this property is not in Property Hub<br> |
| PropertyOccupancyTopic<br> | Do you plan to live in your new home for at least 6 months out of the year? = Yes<br><br>Do you plan to move into your home within 60 days of closing? = Yes<br> | Occupancy Type will be set to “Primary”<br> |
| CapturePropertyTypeTopic<br> | Does the home have more than one unit? = No<br><br>Are homeowner's association dues required for the home? = No<br><br>Was the home manufactured in a factory and assembled on site? = No<br> | Result will be “SingleFamily” property type<br> |
| InitialIncomeSurveyTopic<br> | What are the current sources of income? Select all that apply:<br><br>Joey Gladstone = Employment<br> | <br> |
| CaptureCreditScoreTopic<br> | What is the estimated credit score?<br><br>Joey Gladstone = 680-739<br> | <br> |
| PostInitialClientScreeningSummary<br> | User clicks “next” to proceed past pre-screening and into income/credit review<br> | <br> |
| CaptureCreditConsentTopic<br> | Consent to pull your credit? = Yes<br><br>Joey Gladstone<br><br>05/02/1978<br><br>911-11-1150<br><br>20555 Victor Parkway,  Livonia MI   48152<br> | **Enrichment gump:** with Joey's personal information, we're calling **Credit Service** for an individual credit request<br><br>[Credit (HTML)](http://creditv2test/CreditViewer?CreditRequestGuid=f04b8870-66b0-11e9-89ad-005056af3ab6&amp;requestingSystem=Xbert)<br><br>[Credit (XML)](http://creditv2analyzertest/api/v1/AnalyzerReports?creditRequestId=0&amp;requestingSystem=Xbert&amp;analyzerReportFormat=LKFilePlusAnalyzer&amp;CreditRequestGuid=f04b8870-66b0-11e9-89ad-005056af3ab6)<br> |
| <br> | WAIT state<br> | Checklist engine generates a data exception with no associated topic here while waiting for the credit report enrichment – then Checklist Engine resolves the associated data exception when the credit.performedDate in the LOD is not NULL<br> |
| FullIncomeSurveyTopic<br> | What employment income do you have? (Select all that apply)<br><br>Joey Gladstone: Employer - W2<br> | <br> |
| AddW2EmploymentIncomeTopic<br> | Joey Gladstone:<br><br>Employer’s name: Big Box Store<br><br>Estimated hire date: 1/1/2016<br><br>Rate of Pay: 1,800<br><br>Hourly/Salary: Salary<br><br>Pay Frequency: Twice a Month<br><br>Total Annual Income: $43200<br><br>Do you receive bonus income with this employer?: No<br><br>Do you receive overtime income with this employer?: No<br><br>Do you receive commission income with this employer?<br><br>No<br><br><br> | NOTE: Assuming that this level of salary will create a DTI problem. If not, will reduce the salary amount accordingly.<br> |
| AddW2EmploymentIncomeTopic<br> | Joey Gladstone:<br><br>Do you have additional income from a different employer? = No<br> | <br> |
| DispositionRevolvingDebtObligationTopic<br> | Revolving obligation 1:<br><br>Mark which of the below apply. = Paid by Others<br> | NOTE: Based on the data in the credit report, not sure if Revolving debt will be the first DTI remedy play or not. If not, we’ll just work through the various DTI remedy plays until we resolve that issue.<br> |
| PreProductSelectionSummary<br> | “We may have some options for you. Almost there!”<br> | End on this screen – no user action required<br> |


Last updated: 3/18 to change the scenario from refinance to purchase with accepted offer

1. User enters client's identifying information, indicates they are not married
2. User enters client's intent "purchase”
3. User enters that the client has an accepted offer, enters contract purchase amount and down payment amount (enters a high down payment amount to avoid any LTV issues)
4. User guided to enter intended occupancy type (derived value will be "primary")
5. Property is not present in property hub, so user is guided to answer property type Q&A (answer will be “single family”)
6. User answers initial income survey for the primary client (employment income)
7. User answers stated credit score question for the primary client (good credit score)
8. User views success message and clicks button to continue to income and credit review
9. User manually enters all data required to pull credit
10. System pulls single credit report and the resulting Mortgage Solutions evaluation does not block the client from qualifying, so we move to the next topic
11. There are no property tradelines on the credit report to be dispositioned so we skip this step
12. User performs full income survey for the primary client, who has W2 income only
13. Client indicates they refuse to provide consent to enrich their income data
14. User is prompted to gather income manually, enters a single income source of at least 2 years' length - low $$ amount income
15. User is prompted to ask if the client has any more employment income, user enters No
16. After mortgage solutions request and response, TLAB algorithm determines no deal killers exist, but a DTI ineligibility tag exists on all agency products. Algorithm determines a DTI remedy is needed ("Unexhausted W2 Income" exception and remedy play).
17. User is presented with a message asking if they have any additional sources of income, they say no
18. TLAB algorithm identifies next priority remedy play, based on credit report findings ("UndispositionedRevolvingDebt" exception and remedy play)
19. User is presented with a revolving debt from their credit report and a request to disposition. They clarify it is paid by others. It is a large revolving debt and resolves the DTI ineligibility tag for at least one agency product, and the TLAB algorithm determines no other remedy plays are required.
20. User views the success message because they are qualified for at least one product


# **Demo #5: Update Topic Text Quickly and Without an Engineer**

1. Start a new application in the UI and show the current topic text on the screen: "Client Contact Info"
2. Request new topic text ideas from the demo audience
3. Open the topics.csv file and make the text changes, show the process of committing the changes via the uploader tool
4. Log out of the UI and log back in - start a new application again and show that the text has changed



