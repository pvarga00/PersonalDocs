# Anti-Fragile Code / Systems

Some good reading material: https://leanpub.com/antifragilesoftware/read / http://arxiv.org/pdf/1404.3056.pdf / http://www.monperrus.net/martin/antifragile-discussion / http://dustinewers.com/building-antifragile-software/ / 

Good book: Antifragile – Things that Gain from Disorder by Nassim Nicholas Taleb

Another Source Material: Fragile Services / Antifragile Software by Russ Miles

 

Anti-Fragile is a concept that pertains to systems becoming stronger as stress is placed on them.

Some things become better when exposed to volatility. For example, when you lift a heavy weight, your body makes itself stronger. It becomes stronger in response to stress. Additionally, if you never exercise, your body becomes weak. The human body needs some stress to be healthy. The opposite is true for mechanical systems typically, in that the metal becomes fatigued and wears down as more stress is applied, especially over time to the metal.

Software can be thought of "anti-fragile" - in that we make it better over time, reducing defects, refactoring, and adding features.

 

Some Axioms to Consider:

Your software’s first role is to be useful
The best software is that which is not needed at all
Human comprehension is King
Mechanical Sympathy is Queen
Software is a process of research & development
Software Development is an extremely challenging Intellectual Pursuit
 

Axiom 1: Software’s first role is to be useful The effect and outcome of software, it’s contribution to desirable value that was not present without the software, is the primary responsibility of good software. While the process and crafting techniques used to create software is certainly important, software at a minimum must at least exhibit some usefulness to people as an outcome whether they be a business or an individual.

Axiom 2: The best software is that which is not needed at all This axiom is more controversial, especially given the silo that the majority of contemporary software developers work within. It is our position that a software developer should be most primarily concerned with enabling valuable change² rather than simply focussed on shipping software. If this axiom is accepted, valuable change becomes a maxim of a software developers thinking as they approach a problem domain where software might be applicable. If this broadness of options is recognised, software is one possible answer to the problem domain but should be placed in a context of other recognised options for meeting the challenges of the domain. As other axioms here state, developing software is a challenging intellectual pursuit and, even with the enabling factor of adaptability, can result in a complex solution where an alternate solution was possible. Simply stated, this axiom puts to you that software is one option but by no means the only option when enabling valuable change, which is in our opinion, ironically perhaps given the name, the role of the modern software developer.

Axiom 3: Human Comprehension is King “I don’t want ‘beautiful code’ that I can marvel at in wonder of the smartness of the all-powerful creator! Give me instead ‘Cartoon Code’, something as clean, clear and comprehendible as reading the funnies in a newspaper; but perhaps not quite as funny…” Software is communication primarily between yourself, the original author of your code, and others, the people who will need to be able to change the code. If your architecture, design and code is not clearly communicated with the aim of maximising a reader’s comprehension of your software, how can a reader be expected to understand and update your software? Code comprehension is one of the major forces that can enable, or hinder, a person’s ability to confidently adapt your software. Whole software products have been abandoned, even though at the time they were functional, on the justification that the teams of people involved in working that code no longer understand nor are confident enough to change and adapt the existing codebase. It is important to choose to optimise your code in the first instance in order to maximise the comprehension of others. This extends to all aspects of your code, even to your test code. Test code is crucially important as its aim is to clearly communicate the intentions behind your code. If readers can understand your intention, they will have greater confidence when changing the code and tests as intentions for the software change. To this end, simpler architecture, design and code should focus on maximising human comprehension by effectively documenting intent and minimizing cognitive overhead in the person struggling to comprehend your software. In summary, prefer clarity of intent in your code and avoid anything that introduces confusion, such as surprise!

Axiom 4: Mechanical Sympathy is Queen “to get the best out of any car, you have to have a sympathy for how it actually works and then you can work in harmony with it”, Jackie Stewart Mechanical Sympathy may have its roots in Formula 1 car racing, that high speed processional sport that we brits love, but Martin Thompson³ has importantly re-introduced this facet of thinking into the code we design and write. Mechanical Sympathy is a philosophical approach to designing and writing software whereby the consumer of your software, in this case the machine, is primarily considered. The nuances of the underling machine are clearly understood and have a large effect on the code your write as you strive to make the most of what the machine is trying to accomplish. This approach is particular important where low latency is crucial to the success of a piece of software. At first glance, mechanical sympathy and maximizing for human comprehension can seem to be at odds with one another. However to place the two as distinct competing forces can result in a false dichotomy.

As long as human comprehension has been thought about and optimized for then applying the tenets of machine sympathy to compromise some aspect of comprehension where applicable is a useful and appropriate secondary goal.

Axiom 5: Software is a process of Research & Development “We don’t know what we’re doing…”, “You are not a software developer, you make change happen and software is just one tool…” No, really; we don’t know what we’re doing and that’s ok! Perhaps it might be more accurate to state that we don’t know exactly what we’re aiming for when developing software, especially when embracing the natural change that agile methods informs us is important. When embarking on building a software solution, arguably even before we decide that any software is needed at all, we embark on a journey or research and discovery. Our research with span everything from the concepts and language used in the problem space we’re addressing, right through to the best tools, techniques and languages we can employ to produce the change needed to address those problems. We are researchers and developers, and this has wide-ranging impacts on how we manage our work. Recognizing the importance of research and discovery in software solution development shifts our thinking from the factory floor (i.e. let’s just churn out some more widgets!) to the status of change agents and problem solvers. Software is often our answer, but we are also responsible for exploring, understanding and researching the problem space because, more frequently than not, this is poorly understood even by those who believe they know what is needed.

Axiom 6: Software Development is an extremely challenging Intellectual Pursuit This might come as a surprise to some managerial-types, but software development really doesn’t happen when someone is hammering enthusiastically, or not, on a keyboard. That, as those of us in the trade would say, is just the ‘output’. That hard part has already been done. Software is designed in the mind and collaboratively in conversation and on whiteboards before it goes anywhere near the need to turn it into characters of text in a program. The majority of the effort in software development is in understanding what might be needed, and then turning that into a design that can deal with the test of time. It is that test of time, the ultimate stressor on a design, that this book aims to help with. So in fact when developer’s are thinking, they are working. When they are typing, they are turning their hard work into something that can be used. Unfortunately, thinking is hard and, when it comes to software and the variability of ever understanding what people might want, this places software development firmly in the camp of the most vital and intellectually challenging jobs of the 21st century.

 

Summary: Too much time is wasted building the wrong thing, or building something that takes herculean levels of effort to keep it stumbling forward, like a drunk sumo wrestler up a hill (I love this metaphor/simile).

The key challenges of software development can be distilled into two areas:

• Challenge 1: Building the right thing (or not building anything at all!)   >  How do I avoid Over Production? We’re creating too much software, and what we do create is often not valuable.

• Challenge 2: Building the right thing, right   >  How do I create and maintain software that adapts as fast as the needs placed upon it? We need to create software that meets the needs of ubiquitous and accelerating change.

 

 

Some Concepts to Consider:

Self-Healing Systems

Insulation / Layered Architecture

Microservices

Design Modularity

Redundancy

SOA / Messaging

Cacheing

Eventual Consistency
