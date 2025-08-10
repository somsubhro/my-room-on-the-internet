---
title: "Learnings as a AWS Technical Program Manager (from Medium archives)"
date: 2020-04-17
---

> In this piece, I share my learnings with the hope that this will be useful for aspiring candidates to know what we expect from them.

`This writing is from 2020`

I am a Technical Program Manager within AWS Commerce Platform. This team is responsible for building billing models, payments services, and cost and usage services that our customers use. Given the type and volume of data we deal with, we have an inviolable responsibility to not eff-up and do better than the day before. This responsibility leads to a relentless focus on operational excellence, and to develop and deploy secure, scalable, available services. Below are some details on how this responsibility transpires into real-world actions.

### We write a lot
Teams make high-quality decisions every day. These decisions need to make its way to other engineering teams, product managers, and leaders of the org. We have found that the best way to broadcast decisions without losing information fidelity is by writing it down in 2–3 page decision docs. These docs generally contain why we need to make a decision now, what engineering/product components are affected by this decision and how, what alternatives we have considered and why were they discarded. These decision docs will almost always contain what impact the decision has on our customers. We do everything ̶i̶n̶ ̶o̶u̶r̶ ̶p̶o̶w̶e̶r̶ to avoid ̶,̶ ̶w̶h̶a̶t̶ ̶w̶e̶ ̶c̶a̶l̶l̶,̶weasel words and passive voices in our writing. We write about 25–30 pages on average every week. Some write more depending on their roles. We often utilize the readability statistics score to review our documents before submission.

### We read a lot
I have personally seen us reading anywhere between 7–9 docs each week or an average of 1700 words per 15 mins during meetings. As these docs are our vehicles of decision-making, one is expected to comprehend and provide feedback with care. An unasked question or incorrect feedback may lead to wrong decisions. In addition to decision docs, we also read technical implementation guides, project plans, design docs, and training materials. I have not found an easy button on how to read fast and comprehend well at the same time. I personally think it takes practice and a lot of it.

### We trust humans to do the right thing, but build mechanisms to verify.
We are expected to write code that does what it says it does. But we also build mechanisms like automated integration tests in our code pipelines to assert tests and validate the same. We trust people to not deploy during block days, but we build mechanisms such that code pipelines are automatically blocked from deploying in prod fleets during those days. So that block days are not a deterrent from deploying code change to fix urgent customer issues, we build break-glass workflows. When needed, such workflows work off a 2-person rule and kick in an approval process with our org leaders. As members of engineering teams, we are urged to develop mechanisms.

### We work with ambiguity
Close to 90% of our product roadmaps are result of direct customer feedback. However, customer feedback does not always translate 1:1 with the tasks that engineering teams need to perform. With hundreds of 2-pizza teams, it is oft hard to disambiguate who needs to do what and in which sequence. A TPM comes in handy; they cut across several 2-pizza teams to develop an engineering roadmap in line with the product roadmap. A TPM is expected to go deep into each product such that she can identify design blockers or contradicting implementations. A TPM relentlessly prioritizes work to create a path of least resistance, least amount of throw away engineering work, and least amount of technical debt.

### We don't keep an eye on operations.
At Amazon, I learned that ops can be sexy. Teams do not keep an eye on dials to ensure the health of their service is stable or the service is performant. Dev teams use detective metrics (e.g.: API latency) on production to scale up resources or to automatically cut high severity tickets if manual intervention is needed. As services mature, so do their operational metrics. Periodically, teams use these metrics to identify cost savings opportunities, design changes, and considerations for new development. Operations play a lead role in the remaining 10% of the product roadmap. Every member of a team rotates to be on-call which is an opportunity to be forged in fire.

### We don't hypothesize in vaccuum.
Once we have made a decision we get behind it. Sometimes, however, we need to make decisions without all information available. In such cases, we may need to test a hypothesis. When testing a hypothesis we employ technical mechanisms like allow lists/feature access controls (e.g. using AWS AppConfig) in production. We work with a "treatment group" of customers that receive a change and we record their feedback. If the test is a success we then throttle out the change to the rest of the customers, otherwise we roll back. It is in this role that I learned about the real meaning of two-way door decisions and fail fast.

### We do stickers and swags.
I am a stickler for stickers. I am a stickler for swags. I can trade in a month's salary if you hand me cool stickers. Pro-tip: Use a laptop cover to stick with your stickers even if you have to part ways with the hardware.
