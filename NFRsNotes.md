# Architecting for NFRs : Understanding and Considering the "-ilities" (Quality Attributes)

Architecting for the "-ilities" (Quality Attributes)

Nathiel Schutta @ntschutta

 

What you'll learn

Learn approaches for balancing the various quality attributes on a project
Understand how to document your decisions
 

Description

Developers focus on functional requirements, but once you step into the architect role, your world is increasingly inhabited by the “-ilities”—the nonfunctional or quality attributes of a software system. But which “-ilities” matter and which don’t? As much as we may want to turn every knob up to 11, many “-ilities” are inversely related; maximize one, and you by definition minimize another.

Nathaniel Schutta explores approaches to architectural problems and explains how to best document the inevitable decisions we arrive at. Along the way, you’ll get the opportunity to try and balance nonfunctional requirements yourself.

 

Architecting for the ‘-ilities’ : Quality Attributes

http://nealford.com/katas/list.html

 

Customers are focused on functionality… And developers delivered ‘em

 

As architects however, we need to think of other things: Non-Functional Requirements

 

QUALITY ATTRIBUTES (Cross-Functional Requirements or aka Architectural Requirements)

 

Service Level Agreement

 

Types of NFRs:

Maintainability

Performance

Scalability

Reliability

Security

Deployable (Fast, easy, repeatable)

Simplicity

Usability

Compatibility

Fault-Tolerance

Modularity

… ETC!

 

Inverse relationships: Max one - min another

Ex: Security vs Usability

 

This Is An Art: It’s a balance

 

Most are obvious to our customers … and some aren’t (invisible / hard to understand)

Ex: Maintainability + Simplicity

 

Buy-In (Influence) Techniques:

Outline Benefits: Their language - not ours (common ground agreements)
Avoid aggression / arguments (be cautious in communications)
Listen
Have a conversation
Hard to convince people - 2 approaches:
1) Hammer (order ‘em to do it …. not great)
2) Ninja (have them think it’s their idea)
Find the influencers (or make ‘em) : Influence the influencers!
Most effective: Indirection (be a ninja)
Approach as equals - rely on strength of ideas + reputation
Reputation speaks for you when you’re not there
Ask what your rep is / figure it out : find out from others
Find the Common Ground!
Reciprocity
Be Helpful + Respectful (no table flips)
Research your ideas + trust your sources
Recruit credible allies! BRING HELP!
Speak their language : clients / users, team members, leaders, etc.
Frame chats around measurables: Cost / Productivity / Speed / Reliability
Shape your approach respectively to the intended audience
 

ARCH KATAS:

Series of steps / processes
The processes become second nature - with LOTS of practice
Effortful study: PRACTICE
Fred Brooks: “How do we get great designers? Great designers, DESIGN”
Architectural Katas: PRACTICE projects : minimal consequences
 

Documenting NFRs:

Not complicated
Simple (is better) vs. Easy
Mindmap, list, etc.
Rank the list (ranking is subjective - and it changes across domains)
Give it a shot, solicit feedback, iterate > Rinse and repeat
Software Architecture Decision Doc: SAD Doc
Consider a “time capsule” : ex: podcast on “why” you did things
Quality Attributes impact arch designs
 

KATA: The iDon’tDrive System (Autonomous Car)

Cars phone home on regular cadence
Sends a standard payload including VIN
Demand is extremely high
Must be secure (only access your car)
Allow owner to summon the car to their present location
Push notifications for maintenance, low battery, etc.
System must be available 24/7
Expect millions of cars use this
Demand is extremely high
Web interface + mobile apps
 

Fleet generates a LOT of data - that can be mined
Data must be anonymized
Allow an owner to check status of the car
Ensure only authorized users have access
Audit access to customer data
Push software updates to car
Push recall/update info to customers
Audit access to customer data
 

Audibility, Availability, Security, etc.

 

Different Perspectives on System - Differently Ranked Attributes (from different “users”): 

Client/driver: Usable, Available, Security, Reliable
Company Tech/Support: Security, Audit, Efficient, Usable
 

Need to harmonize competing NFRs : ART / challenging

Decisions made for one, affect others!

 

Think of NFRs from varying contextual standpoints:

User
Architects
Support
Business
Etc.
 

Validate + Rank ‘em

 

Consider the implications + document decisions = Vital to project success

 

Have teams do this activity! (NFR workshop for advocates!)
