# Security Code Reviews

This space is dedicated to discussing the manual process teams can consider when conducting manual security related code reviews.


- Security Code Reviews (Guidance) : [OWASP_Code_Review_Guide-V1_1.pdf]()
- OWASP Secure Coding Practices Quick Reference Guide: https://www.owasp.org/images/0/08/OWASP_SCP_Quick_Reference_Guide_v2.pdf
- Security Attack Tables (Guidance): [SecurityAttackTables.pdf]()
- Security Cheat Sheet (Guidance): [SecurityCheatSheet.pdf]()
- XSS Filter Evasion Cheat Sheet (OWASP): https://www.owasp.org/index.php/XSS_Filter_Evasion_Cheat_Sheet
- Open SAMM: http://www.opensamm.org/download/

 

## Secure Code Reviews: An Overview
You’ve worked hard to ensure that security tools and processes are integrated throughout development, and an application or update is days or possibly just hours away from release. Your app is ready to go, right?

Wrong! You’ve got one more step in the security process before you can give the green light where security is concerned: A Secure Code Review. Especially in our industry, secure code reviews are an critically important part of keeping our client's information secure, and these reviews offer an added layer of security before your application is released. Whether mandated or not, secure code reviews offer an added value for the security of your application, and our organization as a whole.

A Secure Code Review is the process our organization goes through to identify and fix, potentially risky security vulnerabilities in the late stages of the development process. As the last threshold before an app is released, secure code reviews are an integral part of our security process. They serve as a sort of final review to check that your code is safe and sound, and that all dependencies and controls of the application are secured and functional.

Securing our code is our only advantage over malicious hackers. Don’t give up this advantage and rely only on external penetration testing. Use the code to safeguard our client's information.

Become familiar with the guidelines for securing our applications, by:
Reviewing our Security Non-Functional Requirements (NFRs): Non-Functional Requirements#FunctionalRequirements-1.Security
 

 

## What Exactly Is A Secure Code Review?
 

If you’ve integrated security testing throughout your development process, you may think you’re secured for release. But until you’ve ensured that your applications have correctly implemented the security mechanisms by automated and/or manual review, you can’t be sure that last-minute issues or vulnerabilities undetectable by your security tools have popped up.

 

This is where secure code reviews come into the picture. The same way we all review an important document one more time before sending it out, applications require a “last look” to ensure that the application and its’ components, are free of security flaws. A secure code review serves to detect all the inconsistencies that weren’t found in other types of security testing – and to ensure the application’s logic and business code is sound. Reviews can be done via both manual and automated methods – we’ll get into the advantages and disadvantages of each technique later on.


Verifying the security of your code via a secure code review also serves to cut down on time and resources it would take if vulnerabilities were detected after release. The security bugs being looked for during a secure code review have been the cause of countless breaches which have resulted in billions of dollars in lost revenue, fines, and abandoned customers.

 

Security code reviews focus on finding flaws in each of the following areas: Authentication, authorization, security configuration, session management, logging, data validation, error handling, and encryption. Code reviewers should be well-versed in the language of the application they’re testing, as well as knowledgeable on the secure coding practices and security controls that they need to be looking out for.

 

Another important need for the reviewer is for he or she to understand the full context of the application, including its intended audience and use cases, in order to be able to successfully review the code. Without that context, code reviewers won’t be able to secure parts of the code that may look secure at first glance, but given the chance can easily be attacked. Knowing the context by which an app is going to be used and how it will function is the only way to certify that the code adequately protects whatever you’ve relegating to it.



 

## Manual vs. Automated Secure Code Reviews
When it comes time to choosing the tools and processes you’ll use to conduct a secure code review, you may stumble upon the question of which tools to use and whether you should use our automated tools or human inspection. 
Which is better? As with other areas of your SDLC, the best approach is a mixed approach, combining both manual review as well as inspection using strong static code analysis tools. 
Here are the pros and cons of the two methods of review:
 

## Automated Code Review Pros:
- Detects low-hanging fruits and hundreds of other vulnerabilities, including SQL injection and Cross-Site Scripting
- Ability to test quickly and in large chunks of code is crucial in agile and continuous integration environments
- Ability to be scheduled and run on-demand
- Ability to add non-security checks including business logic
- Ability to scale automated testing as per organizational need
- Depending on tool choice, an automated source code review tool can be customized per organizational needs, especially certain compliance standards and for high-value applications
- Can help raise developer security awareness and offer a way to better educate developers who use the tool
 

## Automated Code Review Cons:
- Coverage and breadth are really dependent on the type of tools we choose and the languages, frameworks, and standards those tools cover (We use Acunetix for automated scans, and BurpSuite for more manual inspections)
- Comes with a learning curve for those not familiar with static code analysis tools
 

## Manual Code Review Pros:
- Ability to deep dive into the code paths to check for logical errors and flaws in the design and architecture most automated tools couldn’t find
- Security issues like authorization, authentication and data validation can be better detected manually compared to some automated tools
- There’s always room for an extra set of (expertly trained) eyes on high-value applications
- Reviewing other people’s code can be a great way to share secure coding and AppSec knowledge
 

## Manual Code Review Cons: 
- Requires an expert of both the language and frameworks used in the app as well as needing a deep understanding of security
- Different reviewers will produce different reports, resulting in inconsistent findings between reviewers – though peer reviews can be a fix
- Testing and writing up reports is timely, and often requires developers to participate in sometimes lengthy interview sessions to offer context to the reviewer, costing developer time and resources
- Manual review of applications with more than 10-15k LoC is limited to targeting high risk functions only
 

## Using Both Automated + Manual Security Testing: A "Best of Both Worlds Strategy"
Our applications typically have thousands to hundreds of thousands of lines of code, and the cycles we’re running to release new apps and versions are getting shorter all the time. 
Still, we can’t review code any faster than we did ten to fifteen years ago. On the other hand, no tool or human is perfect.

 
And, as [Wikipedia’s](https://en.wikipedia.org/wiki/Application_security) entry on Application Security says so well, 
“The human brain is suited more for filtering, interrupting and reporting the outputs of automated source code analysis tools available commercially versus trying to trace every possible path through a compiled code base to find the root cause level vulnerabilities.” 
In many ways, manual and automated source code reviews complement each other well, each covering the areas where the other is typically weak.


As your application's security program matures, you’ll find that both manual and automated code reviews should have a place in your strategy. 
Thus, it’s best to have a mix of both automated and manual reviews in your normal security activities.

 

## Secure Code Reviews: (Some Guidance On How To Do Conduct Them For Your Team)
1. Produce code review checklists to ensure consistency between reviews and by different developers
When conducting manual code reviews, make sure all reviewers are working by the same comprehensive checklist. 
Just as the developers writing the code are human and can neglect secure coding practices, reviewers can forget to certain checks, if not working with a well-designed checklist.

In addition, enforce time constraints as well as mandatory breaks for manual code reviewers. 
Remember, just like as we all fade after writing emails or even reading for hours on end, reviewers will fatigue. 
It’s important to ensure the reviewers are at their sharpest, especially when looking at high value applications. 
At the same time, dedicating a specific amount of time to source code reviews will also keep reviewers motivated to finish in an appropriate amount of time.


2. Ensure a positive security culture by not singling out developers
It can be easy, especially with reporting by some tools being able to compare results over time, to point the finger at developers who routinely make the same mistakes. 
It’s important when building a security culture to refrain from playing the blame game with developers; this only serves to deepen the gap between security and development. 
Use your findings to help guide your security education and awareness program, using those common mistakes as a jumping off point and relevant examples developers should be looking out for.
Again, developers aren’t going to improve in security if they feel someone’s watching over their shoulder, ready to jump at every mistake made. 
Facilitate their security awareness in more positive ways and your relationship with the development team, but more importantly the organization in general, will reap the benefits.

 

3. Review code each time a meaningful change in the code has been introduced
If you have a secure SDLC in place, you understand the value of testing code on a regular basis. 
Secure code reviews don’t have to wait until just before release. For major applications, we suggest performing manual code reviews when new changes are introduced, saving time and human brainpower by having the app reviewed in chunks.

 

4. A mix of human review and tool use is best to detect all flaws
Tools aren’t (yet) armed with the mind of a human, and therefore can’t detect issues in the logic of code and are hard-pressed to correctly estimate the risk to the organization if such a flaw is left unfixed in a piece of code. 
Thus, as we discussed above, a mix of static analysis testing and manual review is the best combination to avoid missing blind spots in the code. 
Use your teams’ expertise to review more complicated code and valuable areas of the application and rely on automated tools to cover the rest.

 

5. Continuously monitor and track patterns of insecure code
By tracking repetitive issues you see between reports and applications, you can help inform future reviews by modifying your secure code review checklist, as well as your AppSec awareness training. 
Monitoring your code offers great insight into the patterns that could be the cause of certain flaws, and will help you when you’re updating your review guide.

 

