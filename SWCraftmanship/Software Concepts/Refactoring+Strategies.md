# Refactoring + Strategies

## General Refactoring Strategy:
Make a commitment to continual improvement (know that your refactoring will bring you goodness in the long run)
Make some tests (they'll start out ugly, and need to be refactored too - just get started!)
Plan out your Refactoring (make your life easier, and start with the end in mind)
Use "Internal" (because you can’t test privates)
Insert Seams (adding/breaking apart code for ease of maintainability)
Use Parameter Injection (resolving dependencies / delegates)
Run your tests, to ensure you can make changes with confidence
Repeat the process over-and-over again
 

https://sourcemaking.com/refactoring

## [Composing Methods](https://sourcemaking.com/refactoring/composing-methods)
A large part of refactoring is composing methods to package code properly. Almost all the time the problems come from methods that are too long. Long methods are troublesome because they often contain lots of information, which gets buried by the complex logic that usually gets dragged in.

Extract Method
Inline Method
Inline Temp
Introduce Explaining Variable
Remove Assignments to Parameters
Replace Method with Method Object
Replace Temp with Query
Split Temporary Variable
Substitute Algorithm
 

## [Moving Features Between Objects](https://sourcemaking.com/refactoring/moving-features-between-objects)
One of the most fundamental, if not the fundamental, decision in object design is deciding where to put responsibilities. So, this set of refactorings is all about object's responsibilities.

Extract Class
Hide Delegate
Inline Class
Introduce Foreign Method
Introduce Local Extension
Move Field
Move Method
Remove Middle Man
 

## [Organizing Data](https://sourcemaking.com/refactoring/organizing-data)
Here are several refactoring techniques that make working with data easier.

Change Bidirectional Association to Unidirectional
Change Reference to Value
Change Unidirectional Association to Bidirectional
Change Value to Reference
Duplicate Observed Data
Encapsulate Collection
Encapsulate Field
Replace Array with Object
Replace Data Value with Object
Replace Magic Number with Symbolic Constant
Replace Record with Data Class
Replace Subclass with Fields
Replace Type Code with Class
Replace Type Code with State/Strategy
Replace Type Code with Subclasses
Self Encapsulate Field
 

## [Simplifying Conditional Expressions](https://sourcemaking.com/refactoring/simplifying-conditional-expressions)
Conditional logic has a way of getting tricky, so here are a number of refactorings you can use to simplify it.

Consolidate Conditional Expression
Consolidate Duplicate Conditional Fragments
Decompose Conditional
Introduce Assertion
Introduce Null Object
Remove Control Flag
Replace Conditional with Polymorphism
Replace Nested Conditional with Guard Clauses
 

## [Making Method Calls Simpler](https://sourcemaking.com/refactoring/making-method-calls-simpler)
Objects are all about interfaces. Coming up with interfaces that are easy to understand and use is a key skill in developing good object-oriented software. Explore these refactoring techniques that make interfaces more straightforward.

Add Parameter
Encapsulate Downcast
Hide Method
Introduce Parameter Object
Parameterize Method
Preserve Whole Object
Remove Parameter
Remove Setting Method
Rename Method
Replace Constructor with Factory Method
Replace Error Code with Exception
Replace Exception with Test
Replace Parameter with Explicit Methods
Replace Parameter with Method
Separate Query from Modifier
 

## [Dealing with Generalization](https://sourcemaking.com/refactoring/dealing-with-generalization)
Generalization produces its own batch of refactorings, mostly dealing with moving methods around a hierarchy of inheritance.

Collapse Hierarchy
Extract Interface
Extract Subclass
Extract Superclass
Form Template Method
Pull Up Constructor Body
Pull Up Field
Pull Up Method
Push Down Field
Push Down Method
Replace Delegation with Inheritance
Replace Inheritance with Delegation
 

## [Big Refactorings](https://sourcemaking.com/refactoring/convert-procedural-design-to-objects)
Have a sense of the whole "game." You are refactoring to some purpose, not just to avoid making progress (at least usually you are refactoring to some purpose). 
What does the end game look like?

Convert Procedural Design to Objects
Extract Hierarchy
Separate Domain from Presentation
Tease Apart Inheritance
The Nature of the Game

## Strangler Pattern
The strangler pattern is a software architecture pattern where a legacy system or feature is strangled with new code.
Make something new that obsoletes a small percentage of something old.
Put them live together.
Rinse and repeat.
This is a good pattern to prevent feature branches in source control with all of the integration headaches that go with it.

“We never told the users that they must use the new system. Nor did we remove access to the old system. We relied on making the system so compelling that there was no reason to use the old. This also meant that we stayed focused on the users real requirements”

Strangler Applications http://paulhammant.com/2013/07/14/legacy-application-strangulation-case-studies/

