
The QA Sync up was re-purposed to talk about Data Services Entities to identify what would be needed/feasible in order to automate end to end flows. If required to have an ideal scenario when it comes to data in hubs it would be as follows:



**All data needed for a test is seeded in Data Services' hubs pre-testing and utilized during E2E testing for consistent and repeatable results. Data would be cleaned up afterwards or at least flagged to signify it being test data.**



Ideally this scenario would be for every applicable hub, but understood that it may not be possible for all. During the meeting we went over some of the hubs to get a better idea of what to ask for and what would be involved.



* * *



**Property Hub** (Property Data Management Team) (PO: Jess Lane) (QE: Jesse Cunningham)

- Alice Firsttimer is put in there manually (pre-populated)
- **Takeaway/Future Action needed**: Meet with team/PO to see if what we're looking for is feasible




**Person Hub** (Hub 2.0 Team) (PO: Jennifer Crumit) (Viraj Pandit provided insight)

- Will save data from any upstream system
- Any duplicate social security numbers will get overwritten if other one gets put in there
- No merging, just overwritten (currently, is maybe planned)
- Can dissociate old GCID if getting new social security number 
    - DB engineer would have to delete data
    - Can maybe only delete data if it's test data
    - Test in Prod??? Only for our test data
- **Takeaway/Future Action needed**: Meet with team/PO to see if what we're looking for is feasible




**Loan Hub**(Loan Data Management Team) (PO: Tammy Maxson)

Mark:

- Took loan from loan hub, w/ gcid and prepopulated
- GCID is used from gcid hub to call other hubs (associated w/ GCID)
- **Takeaway/Future Action needed**: Meet with team/PO to see if what we're looking for is feasible




**Credit Hub** (Street Cred Team) (PO: Josh Lenard)

- Ability to provide canned response for certain credits?
- **Takeaway/Future Action needed**: Meet with team/PO to see if what we're looking for is feasible. Need to see if we can prevent calls to 3rd party services.




**Income Hub** (Income and Asset Services) (PO: Vlad Cruck)

- Generated mocked responses for pre-planned scenarios
- Mark Phillips has a story to get more information about income hub, so more information will be coming
- **Takeaway/Future Action needed**: Meet with team/PO to see if what we're looking for is feasible




**GCID** (currently mocked by Flux) (need to work Jennifer)

- Flux controls currently, Social Security gets associated with GCID
- GCID would be eventually be managed within <ac:inline-comment-marker ac:ref="612149cb-3b93-40d6-8939-d22116c57835">Person Entity</ac:inline-comment-marker> (Q2 planned) (maybe)
- Flux's GCID generator would be depreciated once it's been transitioned over
- **Takeaway/Future Action needed**: Meet with team/PO to see what is planned. See if we can get ahead of the curve and have things in place before this service is stood up.




**Mortgage Solutions** (Einstein)

- Only get back what we expect based on scenarios (only returns products)
- Not really much needs to be done here in regards to setting up test data




* * *

Unknown Items/Not sure of scope:



**Assets Import** (As a service?)

- Just pulls third party data
- Rocket team may have test data
- Super low priority


**Headstart**?

**Thin MVP for hand off to AMP???**

* * *



Side note:

- E2E for prototype? Only one or two scenarios for operational prototype. We JUST got to a solid point in regards to content for Scope Area 1 so should start thinking about this.
- 4 demo scenarios need to be automated at very least and every subsequent demo needs to be automated to verify it never breaks in the future (anything that has worked historically should continue working at all times in the future)


* * *

Attendees:

- Peter Varga
- Mustaali Antaria
- Venkata Lingamaneni
- Owen Arent
- Ankush Gupta
- Ed Goff
- Shawn Mallon
- Natasha Kapoor
- Mark Phillips
- Lindsay Bennett
- Viraj Pandit
- Evan Parizot


Recording (Honestly just audio, nothing visual)

[https://teams.microsoft.com/\_#/files/Quality?threadId=19%3Afb0695ff3bae4d69950efa74cf012a90%40thread.skype&ctx=channel&context=QA%2520Sync%2520Meeting%2520Recordings%252F2019-Feb-27](https://teams.microsoft.com/_#/files/Quality?threadId=19%3Afb0695ff3bae4d69950efa74cf012a90%40thread.skype&amp;ctx=channel&amp;context=QA%2520Sync%2520Meeting%2520Recordings%252F2019-Feb-27)
