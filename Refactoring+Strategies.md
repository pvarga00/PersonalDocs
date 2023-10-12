
*<u>Original Source Material:&nbsp;<a href="https://sourcemaking.com/refactoring">https://sourcemaking.com/refactoring</a></u>*

### <u>General Refactoring Strategy:</u>

- Make a commitment to continual improvement (know that your refactoring will bring you goodness in the long run)
- Make some tests (they'll start out ugly, and need to be refactored too - just get started!)
- Plan out your Refactoring (make your life easier, and start with the end in mind)
- Use "Internal" (because you can’t test privates)
- Insert Seams (adding/breaking apart code for ease of maintainability)
- Use Parameter Injection (resolving dependencies / delegates)
- Run your tests, to ensure you can make changes with confidence
- Repeat the process over-and-over again




### [Composing Methods](https://sourcemaking.com/refactoring/composing-methods)

A large part of refactoring is composing methods to package code properly. Almost all the time the problems come from methods that are too long. Long methods are troublesome because they often contain lots of information, which gets buried by the complex logic that usually gets dragged in.


| <ul><li><a href="https://sourcemaking.com/refactoring/extract-method">Extract Method</a></li><li><a href="https://sourcemaking.com/refactoring/inline-method">Inline Method</a></li><li><a href="https://sourcemaking.com/refactoring/inline-temp">Inline Temp</a></li><li><a href="https://sourcemaking.com/refactoring/introduce-explaining-variable">Introduce Explaining Variable</a></li><li><a href="https://sourcemaking.com/refactoring/remove-assignments-to-parameters">Remove Assignments to Parameters</a></li></ul> | <ul><li><a href="https://sourcemaking.com/refactoring/replace-method-with-method-object">Replace Method with Method Object</a></li><li><a href="https://sourcemaking.com/refactoring/replace-temp-with-query">Replace Temp with Query</a></li><li><a href="https://sourcemaking.com/refactoring/split-temporary-variable">Split Temporary Variable</a></li><li><a href="https://sourcemaking.com/refactoring/substitute-algorithm">Substitute Algorithm</a></li></ul> |
| --- | --- |




### [Moving Features Between Objects](https://sourcemaking.com/refactoring/moving-features-between-objects)

One of the most fundamental, if not the fundamental, decision in object design is deciding where to put responsibilities. So, this set of refactorings is all about object's responsibilities.


| <ul><li><a href="https://sourcemaking.com/refactoring/extract-class">Extract Class</a></li><li><a href="https://sourcemaking.com/refactoring/hide-delegate">Hide Delegate</a></li><li><a href="https://sourcemaking.com/refactoring/inline-class">Inline Class</a></li><li><a href="https://sourcemaking.com/refactoring/introduce-foreign-method">Introduce Foreign Method</a></li></ul> | <ul><li><a href="https://sourcemaking.com/refactoring/introduce-local-extension">Introduce Local Extension</a></li><li><a href="https://sourcemaking.com/refactoring/move-field">Move Field</a></li><li><a href="https://sourcemaking.com/refactoring/move-method">Move Method</a></li><li><a href="https://sourcemaking.com/refactoring/remove-middle-man">Remove Middle Man</a></li></ul> |




### [Organizing Data](https://sourcemaking.com/refactoring/organizing-data)

Here are several refactoring techniques that make working with data easier.


| <ul><li><a href="https://sourcemaking.com/refactoring/change-bidirectional-association-to-unidirectional">Change Bidirectional Association to Unidirectional</a></li><li><a href="https://sourcemaking.com/refactoring/change-reference-to-value">Change Reference to Value</a></li><li><a href="https://sourcemaking.com/refactoring/change-unidirectional-association-to-bidirectional">Change Unidirectional Association to Bidirectional</a></li><li><a href="https://sourcemaking.com/refactoring/change-value-to-reference">Change Value to Reference</a></li><li><a href="https://sourcemaking.com/refactoring/duplicate-observed-data">Duplicate Observed Data</a></li><li><a href="https://sourcemaking.com/refactoring/encapsulate-collection">Encapsulate Collection</a></li><li><a href="https://sourcemaking.com/refactoring/encapsulate-field">Encapsulate Field</a></li><li><a href="https://sourcemaking.com/refactoring/replace-array-with-object">Replace Array with Object</a></li></ul> | <ul><li><a href="https://sourcemaking.com/refactoring/replace-data-value-with-object">Replace Data Value with Object</a></li><li><a href="https://sourcemaking.com/refactoring/replace-magic-number-with-symbolic-constant">Replace Magic Number with Symbolic Constant</a></li><li><a href="https://sourcemaking.com/refactoring/replace-record-with-data-class">Replace Record with Data Class</a></li><li><a href="https://sourcemaking.com/refactoring/replace-subclass-with-fields">Replace Subclass with Fields</a></li><li><a href="https://sourcemaking.com/refactoring/replace-type-code-with-class">Replace Type Code with Class</a></li><li><a href="https://sourcemaking.com/refactoring/replace-type-code-with-state-strategy">Replace Type Code with State/Strategy</a></li><li><a href="https://sourcemaking.com/refactoring/replace-type-code-with-subclasses">Replace Type Code with Subclasses</a></li><li><a href="https://sourcemaking.com/refactoring/self-encapsulate-field">Self Encapsulate Field</a></li></ul> |




### [Simplifying Conditional Expressions](https://sourcemaking.com/refactoring/simplifying-conditional-expressions)

Conditional logic has a way of getting tricky, so here are a number of refactorings you can use to simplify it.


| <ul><li><a href="https://sourcemaking.com/refactoring/consolidate-conditional-expression">Consolidate Conditional Expression</a></li><li><a href="https://sourcemaking.com/refactoring/consolidate-duplicate-conditional-fragments">Consolidate Duplicate Conditional Fragments</a></li><li><a href="https://sourcemaking.com/refactoring/decompose-conditional">Decompose Conditional</a></li><li><a href="https://sourcemaking.com/refactoring/introduce-assertion">Introduce Assertion</a></li></ul> | <ul><li><a href="https://sourcemaking.com/refactoring/introduce-null-object">Introduce Null Object</a></li><li><a href="https://sourcemaking.com/refactoring/remove-control-flag">Remove Control Flag</a></li><li><a href="https://sourcemaking.com/refactoring/replace-conditional-with-polymorphism">Replace Conditional with Polymorphism</a></li><li><a href="https://sourcemaking.com/refactoring/replace-nested-conditional-with-guard-clauses">Replace Nested Conditional with Guard Clauses</a></li></ul> |




### [Making Method Calls Simpler](https://sourcemaking.com/refactoring/making-method-calls-simpler)

Objects are all about interfaces. Coming up with interfaces that are easy to understand and use is a key skill in developing good object-oriented software. Explore these refactoring techniques that make interfaces more straightforward.


| <ul><li><a href="https://sourcemaking.com/refactoring/add-parameter">Add Parameter</a></li><li><a href="https://sourcemaking.com/refactoring/encapsulate-downcast">Encapsulate Downcast</a></li><li><a href="https://sourcemaking.com/refactoring/hide-method">Hide Method</a></li><li><a href="https://sourcemaking.com/refactoring/introduce-parameter-object">Introduce Parameter Object</a></li><li><a href="https://sourcemaking.com/refactoring/parameterize-method">Parameterize Method</a></li><li><a href="https://sourcemaking.com/refactoring/preserve-whole-object">Preserve Whole Object</a></li><li><a href="https://sourcemaking.com/refactoring/remove-parameter">Remove Parameter</a></li><li><a href="https://sourcemaking.com/refactoring/remove-setting-method">Remove Setting Method</a></li></ul> | <ul><li><a href="https://sourcemaking.com/refactoring/rename-method">Rename Method</a></li><li><a href="https://sourcemaking.com/refactoring/replace-constructor-with-factory-method">Replace Constructor with Factory Method</a></li><li><a href="https://sourcemaking.com/refactoring/replace-error-code-with-exception">Replace Error Code with Exception</a></li><li><a href="https://sourcemaking.com/refactoring/replace-exception-with-test">Replace Exception with Test</a></li><li><a href="https://sourcemaking.com/refactoring/replace-parameter-with-explicit-methods">Replace Parameter with Explicit Methods</a></li><li><a href="https://sourcemaking.com/refactoring/replace-parameter-with-method">Replace Parameter with Method</a></li><li><a href="https://sourcemaking.com/refactoring/separate-query-from-modifier">Separate Query from Modifier</a></li></ul> |




### [Dealing with Generalization](https://sourcemaking.com/refactoring/dealing-with-generalization)

Generalization produces its own batch of refactorings, mostly dealing with moving methods around a hierarchy of inheritance.


| <ul><li><a href="https://sourcemaking.com/refactoring/collapse-hierarchy">Collapse Hierarchy</a></li><li><a href="https://sourcemaking.com/refactoring/extract-interface">Extract Interface</a></li><li><a href="https://sourcemaking.com/refactoring/extract-subclass">Extract Subclass</a></li><li><a href="https://sourcemaking.com/refactoring/extract-superclass">Extract Superclass</a></li><li><a href="https://sourcemaking.com/refactoring/form-template-method">Form Template Method</a></li><li><a href="https://sourcemaking.com/refactoring/pull-up-constructor-body">Pull Up Constructor Body</a></li></ul> | <ul><li><a href="https://sourcemaking.com/refactoring/pull-up-field">Pull Up Field</a></li><li><a href="https://sourcemaking.com/refactoring/pull-up-method">Pull Up Method</a></li><li><a href="https://sourcemaking.com/refactoring/push-down-field">Push Down Field</a></li><li><a href="https://sourcemaking.com/refactoring/push-down-method">Push Down Method</a></li><li><a href="https://sourcemaking.com/refactoring/replace-delegation-with-inheritance">Replace Delegation with Inheritance</a></li><li><a href="https://sourcemaking.com/refactoring/replace-inheritance-with-delegation">Replace Inheritance with Delegation</a></li></ul> |




### [Big Refactorings](https://sourcemaking.com/refactoring/convert-procedural-design-to-objects)

Have a sense of the whole "game." You are refactoring to some purpose, not just to avoid making progress (at least usually you are refactoring to some purpose). What does the end game look like?


| <ul><li><a href="https://sourcemaking.com/refactoring/convert-procedural-design-to-objects">Convert Procedural Design to Objects</a></li><li><a href="https://sourcemaking.com/refactoring/extract-hierarchy">Extract Hierarchy</a></li><li><a href="https://sourcemaking.com/refactoring/separate-domain-from-presentation">Separate Domain from Presentation</a></li></ul> | <ul><li><a href="https://sourcemaking.com/refactoring/tease-apart-inheritance">Tease Apart Inheritance</a></li><li><a href="https://sourcemaking.com/refactoring/the-nature-of-the-game">The Nature of the Game</a></li><li><a href="http://paulhammant.com/2013/07/14/legacy-application-strangulation-case-studies/">Strangler Pattern</a>** (see below)</li></ul> |




# The strangler pattern is a software architecture pattern where a legacy system or feature is strangled with new code:

1. Make something new, that obsoletes a small percentage of something old
2. Put them "live" -- together (feature toggles!)
3. Rinse and repeat


This is a good pattern to prevent feature branches in source control (with all of the integration headaches that go with it!)

“We never told the users that they must use the new system. Nor did we remove access to the old system. We relied on making the system so compelling that there was no reason to use the "old way'. This also meant that we stayed focused on the user's real requirements”

<ac:image ac:style="letter-spacing: 0.0px;" ac:height="400"><ri:attachment ri:filename="image2016-11-14 15:31:26.png"></ri:attachment></ac:image>
