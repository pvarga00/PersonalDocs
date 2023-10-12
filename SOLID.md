SOLID Design Principles
Skip to end of metadata
Created by Peter Varga on Jan 27, 2020
Go to start of metadata
SOLID
Michael Feathers originated the idea of SOLID and Robert Martin (aka Uncle Bob) named the important principles in his ["Principles of OOD" article.](http://butunclebob.com/ArticleS.UncleBob.PrinciplesOfOod)
SOLID deals specifically with the creation and maintenance of systems that are expected to exist for a long time.
These principles cross languages and paradigms, though they are often most closely aligned with Object Oriented solutions. We are planning on writing an article about each principle and hope to include samples for C#, PHP, and Progress.




Single responsibility principle (S)
"A class or method should have only a single responsibility."




Chapter 8 of Uncle Bob's book, "Agile Software Development: Principles, Patterns, and Practices" has been made freely available here.
What are some simple indicators that code may violate this principle?

The method or class is "Long"
The code directly acts on more than one architecture layer
Business
UI
Data
The code has more than one responsibility or reason to change
The method or class has the word "And" or "Or" in it
Open/closed principle (O)
"You should be able to extend a classes behavior, without modifying it."




Uncle Bob also made an article from his "Engineering Notebook" about this principle freely available here. Often Open/closed is taken as an absolute, which it is not. Bob addresses this concern on page 6 of the article under the heading of "Strategic closure."
What are some simple indicators that code may violate this principle?

[The need to change a method because of a new type](http://professionalservices.matrixresources.com/blog/open-closed-principle-simplified-example)
[Double Dispatch](https://lostechies.com/derekgreer/2010/04/19/double-dispatch-is-a-code-smell/)
Overly complicated control flow:
Too many switch statements
Complicated if-else statements
Overly nested if-else statements
Liskov substitution principle (L)
"Notion of substitutability for mutable objects; that is, if S is a subtype of T, then objects of type T in a program may be replaced with objects of type S without altering any of the desirable properties of that program."
 



Even for technical people that may not be the simplest explanation. Barbara Liskov is explaining that the base or super class is the contract and those who inherit from it are expected to provide implementations that do not break that contract.
A simple example would be:

StreamWriter is our base class
StreamWriter has a Write method which can throw an InsufficientMemoryException
Any classes which inherit from StreamReader and implements the Write Method must throw InsufficientMemoryException or an exception that inherits from it.
[Interface Segregation Principle (I)](http://en.wikipedia.org/wiki/Interface_(computer_science))
"Interfaces provide layers of abstraction that facilitate conceptual explanation of the code and create a barrier preventing dependencies."
 



If you took an Object Oriented class you may remember "is-a" and "has-a" relationships. "Is-a" has to do with "who am I" and "am I this descendant of that." This helps determine what the available behaviors are. When combining the Interface Segregation Principle with Liskov's Substitution Principle you can create really powerful abstractions thanks for [Covariance, and Contravariance.](http://en.wikipedia.org/wiki/Covariance_and_contravariance_(computer_science))
This also comes into play when considering testing, and dependency injection.
More simply put, interfaces are something so common in the "real world" that we don't see them for what they are, a contract about behavior.

Dependency inversion principle (D)
"Depend upon Abstractions. Do not depend upon concretions."




By depending on an abstraction and not a concrete implementation we can change behavior by changing the concrete implementation used behind that abstraction.
For example, I have a program that needs to work with multiple different relational databases. For most vendors we've committed to SQL optimization and the use of the most engine performant features available. Per the Open/closed principle, adding a bunch of conditionals to the code to decide which TSQL options I want to use should be avoided.


How do we address the problem of allowing customization while avoiding an increase in the number of conditionals?


Separate concreations with a common interface. These concreations are then injected as interfaces into the classes that use them. When we inject our SQL dependency our application code can be as small and optimized as our SQL.

Disclaimer: more than likely you should be using stored procedures.

Summary
Principles, not laws.
Toy or throwaway examples do not need to be built using this
SOLID at a glance
Single Responsibility
Open to extension/Closed to modification
Liskov's Substitution
Interface Segregation
Dependency Injection
Dissenting opinions
SOLID has its detractors [1] because sometimes SOLID becomes a dogma. It's proponents lose sight of the reason for the principles, "Simple, maintainable systems."



SOLID – Single Responsibility Principle
SOLID - Open / Closed Principle
  

Other Good Articles (External):

[Single Responsibility Principle (Software Gardening: Seeds)](http://www.dotnetcurry.com/software-gardening/1148/solid-single-responsibility-principle)

[Object Oriented Programming (Software Gardening - Seeds)](http://www.dotnetcurry.com/ShowArticle.aspx?ID=1125)

[Code Refactoring (Software Gardening - Pruning)](http://www.dotnetcurry.com/ShowArticle.aspx?ID=1105)

[Software Gardening - Agile is not for the faint of heart](http://www.dotnetcurry.com/ShowArticle.aspx?ID=1087)

[Software Gardening: Harvesting (Continuous Delivery Techniques)](http://www.dotnetcurry.com/ShowArticle.aspx?ID=1065)

[Software Gardening: Insecticide – Getting Started with Unit Testing using an ASP.NET MVC application](http://www.dotnetcurry.com/ShowArticle.aspx?ID=1043)

[Software Gardening - Storing Seeds (Software Branching Practices)](http://www.dotnetcurry.com/ShowArticle.aspx?ID=1026)
