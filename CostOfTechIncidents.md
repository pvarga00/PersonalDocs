# Cost of Tech Incidents (Chat / Notes)
[8/30 12:41 PM] Czar, Chris
Hi White, Christian! I believe - way back in the day - we discussed a "cost per hour of downtime" associated with a tech incident, I don't believe anyone ever fully looked into figuring this out, but want to double check with you to see if you had any input on this topic.  Varga, Peter is asking for this metric from me and I don't have a RM number - just what the industry says.  Thanks.
 like 1

[8/30 1:08 PM] White, Christian
Hey Varga, Peter this was a question that came up and the finance team and ERM team looked into it. Andrew Kent or Klajdi Myslimaj from the ERM team can help with the impact to lost revenue from a TI. This is likely the biggest impact of a TI. What I looked at is the cost from a team member response perspective to a TI. We looked at number of TMs per major TI and the hours spend solving that TI and we derived an average cost of TM time of $1,700 per hour for a TI.
 like 1

[8/30 1:09 PM] Varga, Peter
Per individual TM? So if 10 TMs were all pulled in, the $1700 scales for each TM, correct?


White, Christian8/30 1:10 PM
Nope that's all in taking into account all TMs involved and weighting their time

or aggregated across "typical number of TMs... by Varga, Peter
Varga, Peter8/30 1:10 PM
or aggregated across "typical number of TMs cost/time" per hour

Varga, Peter added Mulheisen, Erik and Ervin, Robert to the chat and shared all chat history.
Varga, Peter added Mulheisen, Erik and Ervin, Robert to the chat and shared all chat history.
Added a couple of more folks who were inter... by Varga, Peter
Varga, Peter8/30 1:11 PM
Added a couple of more folks who were interested, into this chat

Profile picture of Czar, Chris.So total cost of incident per hour = $1700 ... by Czar, Chris
Czar, Chris8/30 1:43 PM
So total cost of incident per hour = $1700 + x

With $1700 being TM time and x being lost revenue?

So how much is the total cost of "lost reve... by Varga, Peter
Varga, Peter8/30 1:44 PM
So how much is the total cost of "lost revenue" typically? Let's say AMP or LOLA is down - and business is halted == Trying to solve for "x" 🙂

Profile picture of Mulheisen, Erik.Something I was thinking of, when we are do... by Mulheisen, Erik
Mulheisen, Erik8/30 1:46 PM
Something I was thinking of, when we are down, there is sure to be lost revenue, but hard to say how much because of the nature of our business and that if bankers can't do what they do for a period they can make up that time and still generate the clients they would have. Maybe we look at revenue at risk? Like this impact happened during x time and generally during that time our revenue is x?

White, Christian added Kent, Andrew to the chat and shared all chat history.
White, Christian added Kent, Andrew to the chat and shared all chat history.
Profile picture of White, Christian.Hi Kent, Andrew  would you be able to he... by White, Christian
White, Christian8/30 1:53 PM
Hi Kent, Andrew would you be able to help provide some estimates for Peter for cost per hour of downtime for a TI? I provided them with the estimates I had put together for TM time from a TI response perspective but the risk impact is likely the larger value for something like AMP or LOLA.

Profile picture of White, Christian.Hey all, I connected with Andrew and got so... by White, Christian
White, Christian8/30 2:50 PM
Edited
Hey all, I connected with Andrew and got some guidance on estimating the potential loss.



As an example, with a complete outage with AMP we would typically lose all new production after an hour long outage.



I put together high level numbers of the value lost from a complete outage in a system that directly impacts loan production. Keep in mind this is a high level calculation to help understand the magnitude of what the lost value from a TI may look like. There are many factors that impact the value lost from a specific TI such as the system impacted, how severe the outage is, time of day the outage occurs, the loan channel impacted, and many others. Please reach out to Klajdi Myslimaj if you need to understand the value of a specific outage, system etc.



We could see up to $200K - $400K production value lost per hour from a TI that directly impacts loan production.

Additional question: How many TIs of this n... by Varga, Peter
Varga, Peter8/30 4:31 PM
Additional question: How many TIs of this nature occur per year, on average?

Profile picture of Czar, Chris.Varga, Peter I would imagine this is a por... by Czar, Chris
Czar, Chris8/30 9:58 PM
Varga, Peter I would imagine this is a portion of our SEV1/SEV2 - likely ones that impacted applications critical to completing our loan process (ie AMP, Rocket Logic, Docs, etc.)
August 31
Czar, Chris : Correct, I'm trying to pain... by Varga, Peter
Varga, Peter8/31 9:19 AM
Czar, Chris: Correct, I'm trying to paint a picture as to the total cost per year, as related to TIs/outages



- And ultimately why testing in BETA is critical to stopping revenue loss VERSUS the cost of implementing safety measures to lessen the loss of $ (ROI)

Profile picture of Czar, Chris.Varga, Peter  I believe you would need to... by Czar, Chris
Czar, Chris8/31 9:36 AM
Varga, Peter I believe you would need to dig into the TIs to determine if they "directly impact loan production" then get the total MTTR and multiply that by cost per minute ($3.3K - 6.6K).



Whether or not a TI "directly impacts loan production" I do not believe is anyone would know unless this is a criteria for SEV1 and SEV2 - do you know Mulheisen, Erik ?

Profile picture of Mulheisen, Erik.If an incident has a severity of 3 or worse... by Mulheisen, Erik
Mulheisen, Erik8/31 9:39 AM
If an incident has a severity of 3 or worse, then there should be either active business impact or impending risk of business impact. For example, QTrade will have severity 2 incidents some mornings for a delay some of there important Capital Markets processes. As that incident goes on risk gets greater, think timeliness of the market.

If you look at the severity definitions in ... by Mulheisen, Erik
Mulheisen, Erik8/31 9:39 AM
If you look at the severity definitions in the guidebook, while not perfect, the thing that stands out is active business impact is happening.

Link https://guidebook.foc.zone/processesbo... by Mulheisen, Erik
Mulheisen, Erik8/31 9:40 AM
https://guidebook.foc.zone/processesbooks/itsm-processes/incident-management/incident-declaration/

I'm surprised that this metric hasn't been ... by Varga, Peter
Varga, Peter8/31 9:42 AM
I'm surprised that this metric hasn't been identified and tracked yet at a higher level: then we could potentially budget a line item for "next year's probable loss" in the future - (and "cover it" / expected losses) - and then focus on minimizing that loss number with prioritized initiatives to improve/lessen the losses...

Profile picture of Czar, Chris.In my experience there are a couple reasons... by Czar, Chris
Czar, Chris8/31 9:52 AM
Edited
In my experience there are a couple reasons:

Incidents are a topic that is very hard to get anyone to own. Many are involved and impacted but there has never been a driver for an initiative like that. When we build big/incidents it was extremely hard to get feedback on what our dev teams wanted in it, unlike other reports.

The $ is hard to accurately quantify. I actually advocated for QiKJif value driver for "reduced downtime" awhile back, but that never really went anywhere. I'm actually glad to see the $200-400K because that is the first attempt to put a $ amount that I've seen.



Honestly Varga, Peter if this is something that you wanted to run with, I think you would have a lot of support for trying to quantify the impact of incidents. I would assume Karim would be very interested, as well.

Let me see what additional conversations I ... by Varga, Peter
Varga, Peter8/31 9:53 AM
Let me see what additional conversations I can drum up for this...



White, Christian: Are there any "finance teams/names" that could be focused on this, that I could talk to?

Profile picture of White, Christian.Hey Czar, Chris , the updated Risk Reduc... by White, Christian
White, Christian8/31 10:22 AM
Hey Czar, Chris, the updated Risk Reduction add-on value driver "System Stability - Client Impact" in the 3.2 framework does the reduced downtime calculation. The methodology behind that QiKJiF calculation is similar to what I used to get to the $200K-$400K number. Only difference is I took it down to $s rather than clients at risk

Profile picture of White, Christian.Varga, Peter  I think a lot of the more s... by White, Christian
White, Christian8/31 10:28 AM
Varga, Peter I think a lot of the more specific metrics you are looking for around # of TIs, if they impact loan production, and $ is potentially tracked to some extent already. I would reach out to the Enterprise Risk Team (Brandon Dennis and Klajdi Myslimaj) to see what data they might have. I believe they are likely able to look at, for example, the impact that the TIs from QTrade had, how much that impacted loan production, and $s.

Profile picture of Czar, Chris.Begin Reference, Hey Czar, Chris, the updat... by Czar, Chris
Czar, Chris8/31 10:39 AM
White, Christian
8/31/22 10:22 AM
Hey Czar, Chris, the updated Risk Reduction add-on value driver "System Stability - Client Impact" in the 3.2 framework does the reduced downtime calculation. The methodology behind that QiKJiF calculation is similar to what I used to get to the $200K-$400K number. Only difference is I took it down…
I did not dig into that! That's awesome.

