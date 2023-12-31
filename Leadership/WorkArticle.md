
# Coda Hale { writing, projects, about, contact } 
# [Work Is Work](https://codahale.com/work-is-work/)
## In which returns diminish.
12 Jan 2020

## Article:
Every time I’ve written or spoken about organizational design, I’ve regretted it. There’s something about staking out a position on it which manages to prove me wrong a few years later. But I’ve been having some long thinks about it again, and here’s what I’ve got. Strap the fuck in.

At some point in time, every organization realizes that it’s slowing down. Features take longer to ship, folks spend more and more time in meetings, and everyone gets panicky about estimation and planning. If we’ve internalized essentialist bullshit about “B players hiring C players”, maybe we get nervous about The Bar and hiring. If we’re anxious and uncertain, we might get religion about Agile or Scrum or whatever. If we’re prone to modernist flights of fancy, we might decide to spend our innovation tokens trying to disrupt the 200,000 year old industry of getting humans to work together. If we’re the type to do our eight and hit the gate, we chalk it up as the price of success.

These approaches rarely yield results.

Our Dogmatic Slumber
Most explanations of organizational success or failure are crap. Emic accounts–i.e., those from within the organization–are limited to those concepts and narratives which exist within the organization. They may structurally serve as self-narratives and foster a sense of in-group identity and purpose but because they come from the epistemological equivalent of a gravity well their explanatory power outside of that organization is usually terrible.

If we take the etic perspective–i.e. from outside the organization–we can see that emic explanations for an organization’s success or failure have readily available counterfactuals in other organizations. If agile, flat organizations, code reviews, monorepos, open offices, fancy type systems, etc. were actually the causal factors they’re purported to be, then why do so many organizations adopt those practices without success? Why are there other successful organizations which lack those practices? How can we tell the difference between cum hoc, ergo prompter hoc just-so stories and actual causal factors?

More importantly, can we determine the supervenience of some set of factors on organizational performance, not just in a particular context but across all possible organizations? That is, are there necessary, a priori truths of organizational performance?

As it happens, there are.

Corporate America’s Next Top Model
If you squint hard enough, an organization doing work is just an incredibly complex, dynamic, distributed, parallel process. We have very good tools for understanding the rough outlines of how those work, dating back at least to Manabrea’s 1842 comment to Babbage regarding his analytical machine. Now, I won’t pretend to having developed psychohistory and given how difficult it is to predict the behavior of even simple dynamic systems, a fully predictive model of organizational success certainly seems impossible.

But like Kant attempting to derive the necessary preconditions of subjective experience in Critique Of Pure Reason, we can sketch out the boundaries of what an organization is capable of and the dynamics of that as it grows. In the same way that the a priori knowledge that ten pounds weighs more than five pounds informs how much shit we can expect to fit into a bag, modeling organizations as parallel processes can inform the way we design them.

What happens inside those boundaries is a matter of execution and effort; what happens outside those boundaries is impossible.

The Ceiling Is Low
The work capacity of an organization scales, at most, linearly as new members are added. Each new member in an organization adds a constant number of possible work hours to the total possible work hours of the company’s existing employees. Amdahl’s Law states that given a fixed task, a parallel solution utilizing NN processors will run faster than a sequential solution by at most a factor of NN.

As parallel resources are added, the total time spent in the parallelizable portion of the task amortizes to zero; in contrast, the total time spent in the sequential portion of the task never drops below a floor value. This is as true for a group of people trying to write software as it is for a group of CPUs trying to model the behavior of stars in the galaxy. Our intuition tells us that larger organizations do exhibit superlinear behaviors, but this literally cannot be the case if hiring is the only variable in the equation. Therefore, our only hope for superlinear productivity lies in changing the task which is being executed. Thankfully, work capacity is not the same as productivity.

As an organization hires more employees, work on productivity improvements must be a constant priority. Internal tooling, training, and services must be developed and fielded to ensure that all members are able to work on problems of continuously increasing impact. The ceaseless pursuit of force multipliers is the only possible route to superlinear productivity improvements as an organization grows.

Finally, it must be emphasized that this linear bound on work capacity is a ceiling, not a floor. One cannot do better than linear, but one can certainly do worse. There are many other factors which act as a drag on work capacity, and organization-wide improvements in productivity are critical in mitigating them.

The Floor Is Lava
Contention costs grow superlinearly as new members are added. Parallel solutions to tasks are rarely perfectly concurrent (and indeed, such tasks are rightfully called “embarrassingly parallel”), and often require some sequential critical sections. The line of CPUs or people waiting to enter a critical section can be modeled as a queue, which allows us to use queueing theory to understand how the queue’s cycle time changes as the queue size grows. If we model the line for a sequential section as a G/G/1G/G/1 queue, which is to say, without making any assertions about the arrival process or service time distribution but assuming a single queue server (i.e. only one CPU or person can hold the lock), we arrive at Kingman’s Formula for the mean wait time:

\mathbb E(W_q) \approx \left( \frac{\rho}{1-\rho} \right) \left( \frac{c_a^2+c_s^2}{2}\right) \tau
E(W 
q
​
 )≈( 
1−ρ
ρ
​
 )( 
2
c 
a
2
​
 +c 
s
2
​
 
​
 )τ
Notably, the wait time of a queue increases non-linearly with respect to \rhoρ (utilization) and quadratically with respect to c_ac 
a
​
  (the coefficient of variation for arrivals) and c_sc 
s
​
  (the coefficient of variation for service times). (This is the quantified form of the intuition that queues are either empty or overflowing.)

The non-linearity of this should give us pause, as increasing the number of people contending for a shared resource is the same thing as increasing \rhoρ. If contention on those resources is unmanaged, organizational growth can result in catastrophic increases in wait time. At some point, adding new members can cause the organization’s overall productivity to decrease instead of increase, as the increase in wait time due to contention is greater than the increase in work capacity. (This is the organizational version of the latency spikes we see as servers become overloaded.)

These shared resources aren’t necessarily physical things, like bathrooms or printers; they can be digital, like files in a source code repository or tickets in a bug tracker, or organizational, like code reviews or work assignments. As with writing highly-concurrent applications, building high-performing organizations requires a careful and continuous search for shared resources, and developing explicit strategies for mitigating their impact on performance.

A commonly applied but rarely successful strategy is using external resources–e.g. consultants, agencies, staff augmentation–as an end-run around contention on internal resources. While the consultants can indeed move quickly in a low-contention environment, integrating their work product back into the contended resources often has the effect of ballooning c_sc 
s
​
  (the variation of service times, or how long a critical section is held). This produces a quadratic spike in wait times which increases utilization which in turn produces a superlinear spike in wait times. (Queueing theory is a harsh mistress.) Successful strategies for reducing contention include increasing the number of instances of a shared resource (e.g., adding bathrooms as we add employees) and developing stateless heuristics for coordinating access to shared resources (e.g., grouping employees into teams).

As with heavily layered applications, the more distance between those designing the organization and the work being done, the greater the risk of unmanaged points of contention. Top-down organizational methods can lead to subdivisions which seem like parallel efforts when listed on a slide but which are, in actuality, highly interdependent and interlocking. Staffing highly sequential efforts as if they were entirely parallel leads to catastrophe.

Hell Is Other People
Coherence costs grow quadratically as new members are added. Working on complex tasks using parallel resources (or with a group of people) requires communication. A group of 33 has 33 dyads; a group of 44 has 66; a group of 55 has 1010; a group of NN people has \frac{N^2-N}{2} 
2
N 
2
 −N
​
  possible dyads. Point-to-point communication (i.e., talking to each other) can be modeled as the activation of a subset of those dyads.

While some organizations are chattier than others, this communication is essential for the sharing of information and the coordination of action. But it’s not free. Communication takes time. If the relative percentage of people who need to talk to each other to get something done stays constant as the organization grows (i.e., x\%x% of all dyads), the total time spent communicating will grow quadratically as the work capacity of the organization grows linearly.

We can consider group meetings as a batching strategy to reduce the number of entities involved in point-to-point communications, but the effectiveness of this strategy depends heavily on the relative overlap of groups and the group structures. The degree to which the groups overlap is essentially the same factor as the percentage of dyads required for communication. If the group sizes are bounded, the growth of coherence costs will be reduced by a constant factor but still grow quadratically. It may be tempting to try to punt on coherence and just ride dirty, but even subtle forms of incoherence have massive business costs. The only scalable strategy for containing coherence costs is to limit the number of people an individual needs to talk to in order to do their job to a constant factor.

In terms of organizational design, this means limiting both the types and numbers of consulted constituencies in the organization’s process. Each additional person or group in a responsibility assignment matrix geometrically increases the area of that matrix. Each additional responsibility assignment in that matrix geometrically increases the cost of organizational coherence.

It’s also worth noting that these pair-wise communications don’t need to be formal, planned, or even well-known in order to have costs. Neither your employee handbook nor your calendar are accurate depictions of how work in the organization is done. Unless your organization is staffed with zombies, members of the organization will constantly be subverting standard operating procedure in order to get actual work done. Even ants improvise. An accurate accounting of these hidden costs can only be developed via an honest, blameless, and continuous end-to-end analysis of the work as it is happening.

Principles From Beyond Space And Time
Keep the work parallel, the groups small, and the resources local.
When presented with a set of problems which grow superlinearly intractable as NN increases, our best bet is to keep NN small. If the organization’s intent is to increase value delivery by hiring more people, work efforts must be as independent as possible. Leaders should develop practices and processes to ensure that the work efforts which their strategies consider parallel are actually parallel. Shared resources should be continuously managed for contention, and where possible, the resources a group needs should be colocated with that group (e.g., if the work involves a lot of design, staff a designer to that group). Combined arms doctrine isn’t just for soldiers.

Prioritize the development of force multipliers.
If an organization is largely working on the same types of problems it was in previous years, it’s cause for concern. Teams dedicated to internal tooling should be staffed and given the explicit direction of building tools and optimizing processes to help increase their co-workers’ productivity. If the percentage of the organization dedicated to improving how the organization works begins to fall, ask yourself–have we hit a global or local maximum? Go long on high-leverage tools, but stay grounded in whether or not they actually help.

If possible, factor work products into independent modules; if not, grow slowly and optimize.
If your work product–e.g. codebase, documents, etc.–can be factored into independent modules, do so. The key word there is independent. Slicing your shit up into a hundred microservices will not help you if everyone needs to change ten of them to get anything done. Some problems are not particularly amenable to partition; these are also problems which do not benefit much from additional workers. If the problem is a fixed point, look at ways of optimizing the sequential portion of the work. Know that throwing bodies at that problem will produce a clusterfuck.

Scale organizational efforts across a portfolio of synergistic products.
Most smart businesses start out with a single product. They go long on their product hypothesis, put their eggs in a single basket, and swing for the fences. If they’re lucky enough to get traction, they double down on this. Over. And over. And over. At some point, they’ve got several battalions’ worth of people milling around, all trying to figure out who owns the turboencabulator UI and whether or not the new marzelvanes will be fully antigravic by the big fall marketing push.

To avoid that, organization leaders should keep the development of a product portfolio as an explicit goal. Feature or product ideas which are complimentary to the organization’s overall business strategy but don’t naturally coexist with the main product can be developed as separate products by independent teams. We have evidence that software development schedules can be shorted by, at most, 25%; it should be easy to pick between a single product in 18 weeks or two products in 24 weeks.

Successful new products can be incrementally integrated with the existing products where it makes sense, and tooling, libraries, and frameworks can be developed by force multiplier teams to reduce both time-to-market of new products and the carrying costs of existing products. Unsuccessful new products can be gracefully removed from market at dramatically lower cost than features of similar complexity. After all, removing a feature from a product involves the same contention and coherence costs as adding a feature. It’s rare for a feature to present carrying cost greater than the cost of its removal, thus the prevalence of Flying Dutchman features.

As a concrete example of the virtue of a product portfolio, imagine Amazon Web Services as a single product, staffed by a hundred thousand doomed souls and fronted by a UI which is just a series of buttons allowing you to provision and operate virtual machines, databases, data lakes, robotics applications, augmented reality apps, IoT dinguses, and more. Such a creature would implode under its own weight.

Instead, Amazon Web Services is a portfolio of synergistic products. EC2 has its own independent set of features, developed and operated by an independent set of employees. When its needs can be provided by another AWS product (e.g., storing virtual machine images on S3, or sending metrics to CloudWatch), a cross-product integration is introduced. This product structure enables the highly concurrent organizational structure that enables Amazon to field a blistering number of new products every year while continuing to support and develop existing products. Failed services can be sunsetted or drawn down without disrupting the rest of the organization.

Keep responsibility assignment matrices small, sparse, and local.
As an organization matures, ad-hoc roles are often developed into full teams. This specialization is often critical for building internal economies of scale, but the formalization of new constituencies should be kept in check. Each column in your responsibility assignment matrix expands the possible set of required interactions geometrically; each assignment in the matrix is a coordination point requiring waiting. Where a matrix indicates a high-touch relationship between two groups (e.g., a group of engineers working on a feature and the lawyers trying to ensure the legal compliance of that feature), efforts should be made to reduce the cost of that interaction by colocating their members (e.g., embed a lawyer with the engineers).

Prioritize asynchronous information distribution over synchronous.
A significant source of failure demand for meetings and status updates is the desire of organizational leaders to keep abreast of who’s doing what. This situational awareness is indeed important, but trying to maintain it by calling meetings, messaging people on Slack, and catching people on the hallways is a significant systemic drag on organizational productivity.

A better model for staying informed of developments as the organization scales is for groups to publish status updates as part of the regular cadence of their work. Leaders can asynchronously read these updates and, should the need arise, initiate additional, synchronous conversation to ask questions, provide feedback, etc.

Synchronous meetings should be reserved for low-latency collaboration on complex issues; likewise, collaboration should be reserved for synchronous meetings.

What happens inside the boundaries is important.
That we know some of the boundaries of organizational performance and their dynamics doesn’t excuse us from using our empathy to build humane organizations. Companies are groups of people being compensated for having to spend some of their finite lifetimes not being with their partners, children, pets, or super weird hobbies. They deserve to be members of organizations which honor that time by ensuring that their work has value and meaning. There is no mathematical model to guide us to that goal.

Thanks to various Fiascans for reviewing this post. Any mistakes in this article are mine, not theirs.
