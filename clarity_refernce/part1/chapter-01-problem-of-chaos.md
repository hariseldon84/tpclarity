# Chapter 1: The Problem of Chaos

---

## The $6 Trillion Problem

I still recall the webinar that was supposed to be a success.

The client, an HR tech company I was working with, had spent months building a platform for team collaboration and communication. We had put forth a lot of effort. Their tech crew was happy. Leadership had marketed the launch in a webinar to anyone who might want to utilize it, urging them to sign up and try it out for themselves.

After that, the system broke down.

Not a smooth decline. A complete crash. The platform couldn't handle all the users at once. Things that had worked in tests just didn't work when there was a lot of traffic. Users that were able to get in found issues and features that weren't working as they should have.

The client's reputation took a small blow. And I still felt it.

What did their tech team say? "We'll take the feedback and fix it in the next sprint. This is how software is made. Early software is always buggy and has fewer features. It's important to test the idea." They mentioned Eric Ries and the MVP notion as if it made launching a faulty product a good idea.

But this wasn't a minimum viable product. It was a broken product with a twist in the marketing.

If I could go back in time, I'd tell myself to "take a break." Don't send out broken MVPs without following a process and thoroughly evaluating the product. At the beginning, it's quite important to make sure that the characteristics of the MVP match what people really want. Don't test a product if it doesn't meet the minimum quality bar that users anticipate.

That event wasn't one of a kind. I've seen this happen over and over again in businesses, sectors, and countries. And here's what keeps me up at night: we're not getting better at avoiding these mistakes. We're becoming worse.

---

## The Proof: Chaos Is Winning

The Consortium for Information and Software Quality says that bad software quality in the US now costs at least **$2.41 trillion**. Technical debt has grown to almost **$6 trillion** around the world.

These statistics aren't just ideas. They stand for:
- Wasted people's time
- Chances that were missed
- Businesses that didn't work
- Things that never lived up to their potential

The Standish Group's CHAOS Report says that only 31% of IT initiatives are successful. That suggests that 83.9% of projects fail in some way or entirely.

Take a moment to think about that. If you're currently working on a software project, the odds are fewer than one in three that it will be successful.

The 2024 DORA State of DevOps Report showed an even worse trend: the number of high-performing teams fell from 31% in 2023 to only 22% in 2024. At the same time, the number of teams that didn't do well rose from 17% to 25%.

We're not just sitting here. We're moving back.

Even though there have been Agile methods, DevOps practices, and a lot of productivity tools for decades, things are getting worse, not better.

The point of this chapter is to look chaos in the eye and name it what it is.

---

## Why Do Good Teams Make Bad Products? The Nature of Chaos

Let me be clear: teams don't produce chaos because they don't know what they're doing.

Some of the smartest engineers and product managers I've worked with have been stuck in systems that are out of control. We don't have the structure to organize our thoughts, choices, and actions, which is why things get chaotic.

Consider living things. DNA is a genetic blueprint that tells cells how to produce and keep living things alive. DNA doesn't control every molecule interaction, but it does give life its basic structure.

Things that are products need the same thing.

Without a "genetic structure" for product development, which is a clear way to make decisions, teams fall back on reactive patterns:
- Add features because people who matter ask for them
- Go after competition since that's what everyone else is doing
- Use new technologies that are popular on Hacker News
- Send out broken MVPs since "move fast and break things" sounds like innovation

**This is chaos pretending to be progress.**

The costs are huge:
- Studies reveal that 80% of product features are rarely or never used
- A benchmark research from 2024 indicated that people only use 6% of product features
- 60% of the expenses of rework come from requirements that are wrong or not complete
- Some companies now spend up to 87% of their application budgets on technical debt, leaving only 13% for innovation

That isn't a way to make a product. That's a factory for making features that wastes 94% of its time.

But we need to know what chaos looks like before we can develop better structure.

---

## The Seven Faces of Chaos

Chaos doesn't let you know it's coming. It hides behind common sense, best practices, and what others in the field know.

I've found seven patterns, or "faces," of disorder that keep showing up in product groups that are having trouble.

You've probably seen all of them. You could be living with a few of them right now.

**If you took the Clarity Audit in Chapter 0, these seven faces map directly to where you scored low:**

- **Scored 0-4 on Purpose Clarity?** You're experiencing Face #4 (Feature Factory) and Face #7 (Stakeholder Chaos)
- **Scored 0-4 on User Clarity?** You're experiencing Face #2 (Broken MVP Myth)—building from assumptions, not user reality
- **Scored 0-4 on Execution Clarity?** You're experiencing Face #1 (Move Fast and Break Things) and Face #3 (Hype-Driven Tech Selection)
- **Scored 0-4 on Technical Clarity?** You're experiencing Face #6 (Architecture by Chance) and Face #5 (Tribal Knowledge)
- **Scored 0-4 on Cultural Clarity?** All seven faces compound—without cultural discipline, nothing holds

**The patterns you'll recognize below are symptoms of structural clarity deficits. Once you see them, you can't unsee them.**

### Face #1: The "Move Fast and Break Things" Lie

"Move fast and break things" is a popular saying in Silicon Valley. But at some point, it ceased being a tactic that worked in certain situations and became a rule for everyone.

I learned this lesson when that HR IT platform went live.

The team said it was okay to deploy a product that couldn't manage multiple users at once, had errors, and didn't have important features. Why did they do it? "This is how software is made. We'll fix it in the next sprint."

But here's what top software teams know: You don't get things done faster by breaking them. You get things done quickly by not breaking them.

DORA's research shows that **high-performing teams deploy multiple times per day** and have a **change failure rate of 5% or less**. They get faster by being reliable, not by being unreliable.

When you break things, things get messy. Things that are out of order make you slower. In the end, you're not getting anywhere fast; you're putting out fires, fixing things, and telling users why their data is gone.

Velocity isn't the same as speed without organization. It's just moving.

### Face #2: The Myth of the Broken MVP

I worked on telemetry (IoT-connected) software for field users at PepsiCo. It got information from market equipment and showed it to sales and maintenance workers.

We developed what we thought was an MVP: a simple web app that collected data and provided a basic dashboard.

People wanted an app for their phones. They wanted to be able to add, look at, and change sales and marketing data while they were out in the field. We gave them a very basic web dashboard.

What did they do? Radio silence.

They liked that the technology was innovative (IoT/telemetry). The innovation team was in a hurry to get things going. But they didn't use the app very often.

We learned what they really needed later through interviews. The team learned something useful, but only after they sent something that wasn't right.

This happened to me on a lot of different projects, and it taught me a harsh lesson: "MVP" had become an excuse instead of a plan.

Eric Ries said that an MVP is "the version of a new product that lets a team learn the most about customers with the least amount of work."

Take note of what that means: "validated learning."

An MVP isn't "minimum effort" or "minimum quality." It's the least amount of work that can be done while still meeting the quality standards that make a product "viable"—usable, reliable, and valuable enough that people will actually use it.

Teams cause trouble when they mix up "minimum" with "low quality." They send out goods that don't fulfill the demands of users, don't prove their assumptions, and don't help people learn.

### Face #3: Choosing Technology Based on Hype

Blockchain and metaverse technology were everywhere in 2022.

We used 2D metaverse team collaboration software at one of the companies I worked with. Not because we knew what problem the user had that it would fix. Not because we had confirmed the requirement.

Because it was fun and exhilarating.

We spent $500,000 on six engineers for three to four months, a product manager, two directors, server fees, and the cost of not doing something else.

After two months, we figured out that users only stayed on the app for a few hours at a time. There was no genuine value added.

We turned it off.

What signs did we miss?
- Other corporations' early tests hadn't worked on a large scale
- There was presumably a reason the corporation wasn't going B2C if there was an open-source version
- Companies that had used this technology on a large scale did so with a lot of pain and money. We thought this meant "the technology can get funded," but it really meant "this needs a lot of money to work."

**We were using a technology that couldn't fix a problem we didn't have.**

Choosing technology based on hype is a bad idea since it makes things more complicated without adding any value. Every new piece of technology comes with cognitive burden, problems with integration, learning curves, and extra work for upkeep.

Your purpose should drive your user experience, which should drive your technology, which should drive your architecture. When you let technology make decisions instead of purpose, you're building on sand.

### Face #4: Feature Factory Syndrome

In 2024, I saw a sales team try to sell a product to a customer.

They showed off 100+ features. But they couldn't articulate the main point—the product's clear value proposition.

One thing that stuck out was the built-in website builder. Instead of utilizing WordPress, clients could make landing pages with our platform.

It took three to four months to make. It was never used.

The team was shocked when I showed them usage data. The tech team had always thought this was a terrific feature. "Why would people use WordPress when we can give them this?"

The rationale for building it? "Because our rival has it."

If I could make that choice again, I would ask:
- Did we consult users if they need this?
- What comments have we received?
- What does our data tell us about what is and isn't working?

**When teams measure success by outputs (features shipped) instead of outcomes (issues addressed, user value delivered, business results achieved), they create a feature factory.**

Feature factories seem to be working. Moving boards. Sprints are done. There are releases.

But customers are still not happy. Retention isn't going up. The product isn't getting any better in a significant way.

Most product teams work like feature factories, developing things without knowing what really matters if 80% of features are rarely or never used.

### Face #5: Tribal Knowledge and Documentation Debt

I needed to learn from a scientist in Rotterdam, Netherlands, when I worked at Unilever.

He was in charge of a team and knew a lot about chemistry and new ways to use labs. He knew what mistakes you could make when testing chemicals. He knew how to deal with problems within the company to get a product out the door. He was so good at chemistry that he thought everyone else knew things that were never written down.

A lot of the knowledge transfer was written down and given to someone else. But the more I talked to him, the more I found hidden tacit knowledge that he had never communicated and that was hard to write down.

We had a hard time when he left. We learned from the same mistakes he made. It kept happening. Things took longer than planned.

It took almost a year to put that information back together. Research and development on products slowed down a lot.

Why wasn't it written down? Things that everyone thought they knew.

This is tribal knowledge, and it's one of the most insidious kinds of chaos.

When critical understanding only exists in people's heads, you become fragile. That information goes away when that person goes on vacation, gets a new job, or retires. The team moves more slowly. It's harder to make choices. Bugs turn into mysteries.

Tribal knowledge creates friction that leads to chaos when it comes to onboarding, debugging, scaling, changing architecture, and recovering after an incident.

### Face #6: Architecture by Chance

We used Flutter to make a mobile app for my ed-tech firm, YSchool.

Flutter only worked for making mobile apps back then, not web apps. We needed both, but we built the mobile version and hoped we'd figure out web later.

Later, when we needed to add a web app and scale, the architecture we had unwittingly built became a problem.

What would the system have looked like if we had planned it out from the beginning?

**A cross-platform solution (Web + Mobile) with fundamental features: a reliable LMS, a question bank, assessment, and adaptive testing that most K–12 ed-tech platforms need.**

Instead, we had a system that "just grew" without any planning.

Most systems aren't made on purpose. They've accumulated.

Here, a feature is added. There, a service is taken out. Someone needed a database for a prototype; thus, one was added. None of these choices are incorrect in and of themselves.

But when they arise without any thought to architecture—without any clear choices about modularity, boundaries, dependencies, and trade-offs—you have architecture by accident.

The end result is systems that are hard to understand, hard to change, and hard to maintain.

Research on technical debt shows that maintaining poorly structured systems can take up to 87% of engineering budgets, leaving just 13% for innovation.

That's the penalty of architecture by accident: it doesn't kill you right away; it steadily makes it harder for you to move forward.

### Face #7: Chaos Caused by Stakeholders

One of the founders of MyClassroom, who had a background in education, desired a feature: a timetable scheduler for their teachers.

His explanation was based on how things worked. He wanted to help set up classes. It felt like the request couldn't be changed.

We confirmed the requirement. What we found: For the amount of complexity needed, it could have been done easily in an Excel or Google sheet.

Still, we built it. At first, it was used. But people always compared it to the best scheduling software on the market. In the end, we got rid of the feature.

What was put off to make room for it?

An AI-based review engine that could have benefitted end users, increased engagement, and enhanced retention. This was a key feature that would have set our ed-tech platform apart from others.

In hindsight, I would say, "Let's take a structured approach to this need and use a methodology" (what I would today call the Product Genome + Clarity OS).

When stakeholder requests don't follow the usual order of priority, they create:
- Strategic incoherence: The roadmap turns into a jumble of things that don't go together
- Validation bypass: "The founder wants it" means that assumptions aren't tested
- "Team whiplash": Teams can't keep up with changing priorities fast enough
- Technical debt: Features are produced too quickly without the right design
- Morale damage: Teams feel like they are just taking orders instead of solving problems

All ideas, including those from stakeholders, should go through the same strategic filters: Does it fit with our purpose? Does it meet the needs of real users? Is it compatible with our architectural constraints? Can we deliver it at the level of quality we promised?

When you avoid such inquiries, things get out of hand.

---

## The Costs of Chaos That Keep Adding Up

Each face of chaos is manageable on its own.

Teams can handle going a little too quickly. They can ship a suboptimal MVP and fix it later. They can use one hyped-up technology that doesn't work out.

**But chaos compounds.**

"Move fast and break things" and "ship broken MVPs" together make products that are both rushed and of poor quality.

Add "hype-driven technology selection," and now you're making rushed, low-quality items on shaky architectural ground.

You ship things quickly and badly on fragile tech, not knowing if any of it matters, because of "feature factory syndrome."

This is how teams get:
- $2.41 trillion in expenses from bad software quality (only in the U.S.)
- $6 trillion in technical debt around the world
- 83.9% of projects that fail or just partially succeed
- 80% of features that were deployed but are rarely or never used
- 87% of budgets going to maintenance instead of innovation

These numbers aren't just statistics. They represent real teams that are burning out, making things that don't matter, and questioning why they can't get ahead even though they are working harder than ever.

And here's the worst part: chaos feeds on itself.

When teams are drowning in chaos, they don't have time to stop and fix flaws in their structure. They're too busy putting out fires, fixing things, and meeting deadlines. So they take more shortcuts. They skip more documentation. They make decisions that are more reactive.

And the chaos grows worse.

The 2024 DORA report's observation that the number of high-performing teams dropped from 31% to 22% implies that this is happening across all industries.

**We're all getting worse at making software, not because we don't have the right tools or skills, but because we don't have structural clarity.**

---

## Why Smart Teams Get Out of Control

Why is chaos so widespread if it's so bad? Why do smart, well-meaning teams develop things that clearly don't work?

I have found four main reasons:

### Reason #1: We Mix Up Progress and Motion

People are naturally drawn to activity rather than inaction. When we don't know what to do, we do something—anything—rather than sit with the unknown.

In product development, this looks like adding new features, sending out updates, and moving tickets between boards.

But moving doesn't mean progress. Moving closer to your goal is making progress. Motion is just... going.

The feature factory trap exists because it "feels" like it works. Updating boards. Code is being committed. The metrics are shifting. It appears like things are getting better.

The illusion breaks only when you take a step back and question, "Are we really solving the problem we set out to solve?"

### Reason #2: We Don't Have the Same Mental Models

When teams don't have a shared way of thinking about product development, every choice becomes a negotiation based on first principles.

Should we make this feature a top priority? How are we going to decide what to do first? How can we find a balance between what users want, how much money we have to spend on technology, and our business goals? What does "done" mean? When is quality acceptable?

When teams don't have common mental models—clear, explicit ways to make these decisions—they rely on gut feelings, authority, and whoever makes the best case.

This isn't a process. It's chaos with more meetings.

### Reason #3: We Focus on the Wrong Things

Most companies keep track of and reward outputs like features shipped, velocity attained, and deployments done.

But outputs aren't the same as outcomes.

You can ship 100 features and not provide any value. You can move quickly and have bad quality. You may deploy all the time and make things worse.

When incentives encourage movement over progress, chaos is the logical consequence.

### Reason #4: We Don't Know There Is Another Way

For a lot of teams, chaos is just "how software development works." They've never seen it done any other way. They think that constantly putting out fires, changing objectives, and accumulating technical debt are normal parts of making software, not symptoms of a broken structure.

This is learned helplessness, and it's devastating.

You don't look for a better way if you don't know it exists. You just have to get through the mess you have.

---

## The Way Forward: From Chaos to Clarity

Three months after our internal target, I started this chapter with the launch of that webinar. A team was there to observe people discover a broken product and ask, "How did we get here?"

I now have an answer: We got here by building without structure. By focusing on movement instead of progress. By mixing up activity with value. By letting chaos build up until it took over.

But here's the good news: once you know what chaos is, can see its patterns, name its faces, and understand how much it costs, you can make a different choice.

You can build with structure. With clarity. On purpose.

You can build with a genome.

In the next few chapters, I'll show you how. We'll explore:

- **The Product Genome as Structure** (Chapter 2): How 6 DNAs create the foundation for clarity
- **Feature Factory vs. Genome-Driven Building** (Chapter 3): The difference between reactive building and strategic building, plus how "Grandma's Closet" keeps distractions from hijacking your roadmap
- **The Minimum Quality Bar** (Chapter 4): Non-negotiable standards that prevent chaos from entering the system

And then we'll dive deep into the 6 DNAs—the genetic makeup of great products:

1. **Purpose DNA**: The North Star that guides every choice
2. **User DNA**: The reality anchor—who you're making things for and what they actually need
3. **Experience DNA**: Quality thresholds and interaction patterns
4. **Architecture DNA**: Structural stability that enables evolution
5. **Intelligence DNA**: Evidence infrastructure that drives learning
6. **Cultural DNA**: Values embedded into product decisions

We'll explore the No Distraction Clarity Cycle, the Builder's Hierarchy, and the frameworks that help you apply these principles in daily work. And we'll look at real case studies of teams that transformed from chaos to clarity.

But all of that comes later.

Right now, I want you to sit with this chapter. Look at your own team, your own product, your own process. Ask yourself:

- Which faces of chaos do I recognize?
- What is chaos costing us—in money, time, morale, and opportunity?
- If I took the Clarity Audit in Chapter 0, which dimensions did I score lowest in?
- What would it mean to build differently?

The Product Genome isn't about perfection. It's not about eliminating all uncertainty or risk. It's about replacing chaos with structure, confusion with clarity, and random motion with intentional progress.

**It's about building products that matter, in ways that last, with teams that thrive.**

By the end of this book, you'll retake the Clarity Audit. Most teams improve their score by 5-8 points in six months. Some improve by 10+.

That improvement isn't just a number. It's measurable transformation from chaos to clarity.

Let's begin.

---

**Word Count: ~4,500 words**
