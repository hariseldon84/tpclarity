# Chapter 17: Scaling Without Breaking—Team Topologies and the Product Genome

---

## The Moment Amazon Realized More People Meant Slower Delivery

By early 2002, Amazon had grown to several hundred engineers. They had talent, funding, and Jeff Bezos' relentless focus on customers. They should have been shipping faster than ever.

Instead, they hit a wall.

To launch a simple feature—like a new "Recommendations" widget—a developer had to coordinate with the database team for schema changes, the frontend team for UI placement, and the "Monolith Owners" for deployment approval. Projects that should have taken two weeks were taking months. The "Coordination Tax" was consuming nearly 70% of engineering effort.

Jeff Bezos looked at the roadmap and realized something profound: **The bottleneck wasn't the code. It was the meetings.**

Communication overhead was growing exponentially while output was growing linearly. Amazon had fallen into the scaling trap: **More people, slower delivery. More process, less agility.**

Bezos issued what became known as the **"API Mandate" in 2002**—a forced restructuring that would change not just Amazon, but the entire software industry:

**The Two-Pizza Rule**: Every team must be small enough to be fed by two pizzas (5 to 8 people).

**Autonomous Ownership**: If a team owned "The Shopping Cart," they owned the frontend, the backend, and the database—end-to-end.

**The Interface Rule**: Teams were forbidden from "collaborating" through meetings. They communicated only through service interfaces (APIs).

**The result?** Amazon transformed from a monolithic mess into the microservices pioneer that eventually created AWS. The "Two-Pizza Teams" became autonomous units that could deploy code in minutes without talking to anyone outside their team.

**The lesson:** Scaling isn't about adding more people. It's about designing team structures that enable fast flow despite more people.

---

## The Math of Coordination Hell

Here's why Amazon's problem was structural, not cultural.

**Brooks's Law** states: "Adding manpower to a late software project makes it later." The underlying reason: coordination costs increase non-linearly.

**The math is brutal:**

- A team of 5 has **10 communication paths** ((n × (n-1))/2)
- A team of 50 has **1,225 communication paths**

That's a **122x increase in coordination complexity** for a **10x increase in team size**.

Without structure, those 1,225 paths become meetings, Slack messages, alignment sessions, syncs, and "quick questions" that collectively consume your team's capacity.

**The solution isn't more process.** Most organizations respond to scaling chaos by adding governance committees, approval workflows, and standardization mandates. This treats symptoms, not the root cause.

**The solution is Team Topologies**—a framework for designing team types and interaction modes that enable desired architecture and delivery speed at scale.

---

## The Four Team Types That Enable Scale

**Team Topologies** (by Matthew Skelton and Manuel Pais) defines four fundamental team types. Each has a different purpose, autonomy level, and interaction pattern.

### 1. Stream-Aligned Teams (The Feature Builders)

**Definition**: Teams aligned to a continuous flow of work from a user or customer—delivering directly to them.

**Characteristics:**
- End-to-end ownership (design, build, deploy, operate)
- Cross-functional (engineering, product, design, QA)
- Autonomous within their domain
- Primary team type in most organizations

**Example from Cadence:**

At Cadence Infotech, we restructured from separate "Frontend Team" and "Backend Team" into cross-functional squads. One squad of 6 people includes: 3 full-stack developers, 1 UI/UX designer, 1 QA engineer, and 1 product manager.

**Their stream:** The "Enrollment-to-Collection" user journey—owning everything from when a parent first visits the school website to when the first term fee is reconciled in the school's bank account.

**Their autonomy:** They can choose their own libraries, refactor their own services, and pivot the onboarding flow based on user feedback—without asking the CTO—as long as they don't break the API contract with the Academic module.

**The result:**
- **Lead time** dropped from 6 weeks to 10 days (everyone needed to ship was in the same room)
- **Bug rates** dropped because the developer who wrote the code was the same one deploying and monitoring it (Radical Ownership)
- **Team velocity** increased because handoff waste was eliminated

**Why it worked:** The Builder's Hierarchy (Chapter 12) gave them an Outcome Map, not a To-Do List. They knew their work linked directly to the "100% Predictable Revenue" goal for schools. ADRs (Architecture Decision Records) ensured I could see their decisions without attending their daily scrums.

### 2. Enabling Teams (The Capability Builders)

**Definition**: Teams that help stream-aligned teams overcome obstacles, detect missing capabilities, and research options—temporarily.

**Characteristics:**
- Temporary assistance (not permanent dependency)
- Knowledge transfer focus (teach, don't do)
- Detect capability gaps across stream teams
- Example specializations: CI/CD expertise, observability, security

**Example from Swiggy:**

As Swiggy scaled from a few dozen to hundreds of microservices, their feature teams (stream-aligned) struggled to manage their own infrastructure, deployment pipelines, and observability—leading to massive cognitive overload.

**The Enabling Team:** Swiggy's Platform Engineering and SRE teams acted as enabling teams, focused on building "Service Ownership & Observability" capability within their Pods (stream-aligned teams).

**How they engaged:**
- **Embedded SREs**: Instead of an SRE doing the work for a team, they "embedded" with a feature team for 2-4 weeks, pairing with developers to set up monitoring dashboards and automated alerting
- **Golden Path Workshops**: Teaching teams how to use Swiggy's self-service infrastructure tools—ensuring they understood the why behind the architecture, not just the how
- **Docs-as-Code Playbooks**: Creating runbooks that teams could follow to resolve common infrastructure issues independently

**When they disengaged:** Once a team demonstrated they had functional SLOs (Service Level Objectives), automated alerts, and could handle a canary deployment independently, the enabling SRE moved to the next team.

**Why it worked:** The capability lived in the team's local DNA, not in a central department. Teams stopped saying "The infra is slow" and started saying "Our service's p99 latency is crossing its SLO; we need to optimize our database queries."

### 3. Platform Teams (The Force Multipliers)

**Definition**: Teams that provide compelling internal products to accelerate stream-aligned teams via self-service capabilities.

**Characteristics:**
- Platform as product (not just shared services)
- Self-service (minimal coordination needed)
- Reduce cognitive burden on stream teams
- Examples: AWS, internal developer platforms, CI/CD platforms

**Example from Spotify: Backstage**

As Spotify moved from a single app to hundreds of microservices and squads, they faced the "Scaling Paradox": it became increasingly difficult for developers to find information, spin up new services, and maintain standards.

**The Problem:** Autonomous squads were reinventing the wheel. Every time a team wanted to build a new feature, they had to manually set up CI/CD pipelines, documentation sites, and monitoring. The "Fragmentation Tax" was slowing down the Evolution Flow.

**The Solution:** Spotify's platform team created **Backstage** (later open-sourced in March 2020 and donated to CNCF)—a unified Internal Developer Platform.

**The Mandate:** "Build a Golden Path, not a Golden Cage." Make it so easy to follow best practices (security, scalability, observability) that teams choose the platform's defaults over building custom solutions.

**How it works:**
- **Self-Service Templates**: A developer clicks "Create New Service" in Backstage. Within minutes, the platform automatically provisions the Git repo, the CI/CD pipeline, the documentation site, and the cloud infrastructure
- **Plugin Architecture**: If a specific squad (e.g., Payments) needs a specialized tool, they build their own plugin and contribute it back. The core team focuses on the "Honeycomb" (structure), while others add the "Honey" (features)
- **X-as-a-Service Interaction**: No meetings required to launch a service. Communication happens through the platform's API and UI

**The result:** Spotify scaled to thousands of engineers without needing a proportional increase in infrastructure staff. One platform team could support hundreds of stream-aligned squads.

**Product Genome connection:** Backstage embodies **Experience DNA** (Developer Experience)—judged by "Time to First Hello World." It codifies **Architecture DNA** (the Golden Path ensures security and data standards are inherited automatically).

### 4. Complicated-Subsystem Teams (The Specialists)

**Definition**: Teams responsible for subsystems that require specialist knowledge—reducing cognitive load on stream-aligned teams.

**Characteristics:**
- Deep expertise in a specific technical domain
- Handle complexity so stream teams don't have to
- Examples: Video codec optimization, ML infrastructure, fraud detection algorithms

**Example from Swiggy: Order Assignment Engine**

In food delivery, most engineers work on stream-aligned features like the cart, tracking UI, or search filters. But Swiggy identified that the **Order Assignment Engine**—matching a delivery partner to an order—was too mathematically complex for generalist teams.

**What it does:** Uses complex algorithms (Integer Linear Programming - ILP) to decide which delivery partner should pick up which order, whether to batch multiple orders from the same restaurant, and the optimal route to minimize delivery time while maximizing partner earnings.

**Why it's separated:**
- **Computational Complexity**: Solves a "Multi-objective Optimization" problem millions of times a day in real-time—requires mathematics and data science beyond standard backend developers
- **Strategic Risk**: A bug here is a "Doomsday Scenario." If this engine fails, the entire logistics network collapses
- **Cognitive Load Protection**: By isolating this complexity, the "Checkout" or "Restaurant Listing" teams don't need to know how ILP or Geohashing works

**Who's on the team:**
- Optimization Researchers (PhDs in mathematical optimization)
- ML Engineers (experts in training models on massive geospatial datasets)
- Network Simulators (building "digital twins" of cities to test algorithm behavior)

**How other teams interact:** X-as-a-Service. When a "Cart" team finishes checkout, they publish an `order_created` event. The Assignment Engine consumes it, runs its math, and publishes a `partner_assigned` event. The "Tracking UI" team simply listens for that event. They never touch the assignment code.

**What would have happened without this team:** Individual feature teams would try to "fix" assignment for their specific use case (e.g., "Priority Gold Users"), accidentally degrading efficiency for 95% of users. Generalist engineers would use simple heuristics (find the nearest driver), which works at 1,000 orders but fails at 1 million.

---

## The Three Interaction Modes: How Teams Communicate

Team types alone aren't enough. **How teams interact** determines whether coordination becomes a bottleneck or a multiplier.

### 1. Collaboration (High Bandwidth, Time-Boxed)

**When to use:** Rapid discovery (exploring new domain), shared learning, high uncertainty.

**Time-boxed:** This is NOT a permanent state. Continuous collaboration = high coordination cost. After discovery, shift to X-as-a-Service or Facilitating.

**Example:** Stream team and platform team collaborate for 2 sprints to design a new API. After that, they shift to X-as-a-Service (stream team consumes the API without meetings).

### 2. X-as-a-Service (Low Coordination, High Autonomy)

**When to use:** Service is well-defined, consumer needs are known, low coordination needed.

**Goal:** Minimize interaction cost. Clear API/interface, self-service documentation, SLAs.

**Example:** Stream-aligned team deploys to platform provided by platform team. No meetings needed—just API calls and documentation.

**This is Amazon's "Interface Rule" in action.** The overwhelming majority of team interactions at scale should be X-as-a-Service.

### 3. Facilitating (Teaching, Not Doing)

**When to use:** Stream team has a knowledge gap, new technology/practice adoption, temporary need.

**Example:** Enabling team pairs with stream team for 2 weeks to implement observability. After 2 weeks, the stream team owns it.

**Key:** The enabling team disengages once capability is built. They don't become a permanent dependency.

---

## Conway's Law: Your Org Chart Becomes Your Architecture

**Conway's Law** (1968): "Organizations which design systems are constrained to produce designs which are copies of the communication structures of these organizations."

**Translation:** Your org chart IS your architecture. If you have a backend team and a frontend team, you'll get a backend and a frontend—not a unified system.

### The Reverse Conway Maneuver

If Conway's Law is inevitable, **use it deliberately**. The Reverse Conway Maneuver means restructuring teams to enable the desired system architecture.

**Amazon's transformation:**
- **Old structure**: Frontend team, Backend team, Database team (functional silos)
- **Result**: Monolithic, tightly-coupled architecture
- **New structure**: Two-Pizza teams owning services end-to-end
- **Result**: Microservices architecture naturally emerged, with service boundaries matching team boundaries

**Your team structure IS your architectural strategy.** Architecture DNA (Chapter 8) and Team Topologies are two sides of the same coin.

---

## Cognitive Load: The Real Scaling Constraint

Here's the truth about scaling: **Teams have limited cognitive capacity.** As organizations scale, cognitive load becomes the bottleneck—not coding speed.

**The three types of cognitive load:**
1. **Intrinsic load**: Fundamental complexity of the domain (financial regulations, distributed systems)
2. **Extraneous load**: Complexity from environment/tooling (15 deployment steps, brittle CI/CD)
3. **Germane load**: Learning and skill development (valuable cognitive effort)

**Goal:** Minimize extraneous load, optimize intrinsic and germane load. Teams should spend cognitive capacity on domain complexity and learning—not fighting tools.

**Amazon's Two-Pizza Rule isn't arbitrary**—it's cognitive load management. Research shows optimal team size is 4-5 people, maximum 9. Larger teams have combinatorial communication paths and diffuse responsibility.

**When cognitive load signals "stop growing":**
- Teams self-report "overwhelmed" >50% of the time
- Extraneous load can't be reduced further
- Platform teams already absorbing maximum complexity

**Response:** Scale via leverage (automation, platform, tooling)—not headcount.

---

## Sustaining the Genome as You Scale

Here's how the Product Genome integrates with Team Topologies to enable sustainable growth:

### 1. Preserve Principles, Evolve Practices

**Invariants (preserve):**
- **Mission** (Purpose DNA): Why we exist, who we serve
- **Values** (Cultural DNA): Non-negotiables (integrity, user focus, excellence)
- **Quality bar** (MQB): Standards don't drop as we scale

**Variants (evolve):**
- **Processes**: Weekly all-hands → monthly town halls at scale
- **Structures**: Flat startup → Team Topologies at 50+ people
- **Tools**: Slack channels → structured communication platforms

**Strategy:** Annual "Genome Audit"—revisit DNAs, update practices to match current scale, reinforce principles.

### 2. Design for Flow, Not Control

Traditional scaling adds management layers, governance committees, approval workflows (control). Team Topologies scaling designs team types and interaction modes to enable fast flow (autonomy within guardrails).

**Principle:** Minimize coordination, maximize autonomy. Stream-aligned teams should operate independently 90% of the time.

**Metrics:**
- Coordination overhead <15% of capacity
- Decision cycle time <2 days for team-level decisions
- Deployment independence (teams deploy without coordinating with others)

### 3. Platform as Force Multiplier

As you scale, **leverage > headcount**. Platform teams create reusable infrastructure so stream teams don't reinvent.

**ROI calculation:** Platform team of 8 people supports 12 stream teams (60 people). If the platform reduces stream team infrastructure work by 20%, that's 12 FTE-equivalents saved—150% ROI on platform investment.

**When to invest in platform:** When 3+ stream teams repeatedly solve the same problem independently.

### 4. The Genome Operating System at Scale

**Purpose DNA** guides what stream teams build (user value, business outcomes).

**Architecture DNA** aligns with team boundaries (Conway's Law, Reverse Conway).

**Experience DNA** is maintained by platform teams (golden paths, self-service).

**Intelligence DNA** is instrumented by stream teams, aggregated by platform (observability).

**Cultural DNA** is preserved via culture carriers (principles), evolved via adaptation (practices).

---

## Maintaining Clarity at Scale

Here's the paradox: **As teams grow, clarity naturally fragments.**

At 6 people, everyone's in every conversation. Purpose DNA is absorbed through osmosis. Scope is clarified in hallway conversations. Alignment happens automatically.

At 50 people, you have 8 teams, distributed locations, asynchronous work. The same clarity disciplines that worked for 6 people need structural reinforcement.

**This is where Clarity OS becomes essential—not optional.**

### How Clarity OS Scales Across Teams

**At Cadence Infotech, we scaled from 6 to 52 people in 18 months.** Here's how we maintained clarity without adding bureaucracy:

#### 1. Each Team Has Its Own Clarity Checkpoints

Every stream-aligned team runs **monthly Clarity Checkpoints** (the 5 diagnostic questions from Chapters 5-10). But they customize questions to their domain:

**Fees Team:**
- Purpose DNA: "Does fee automation still advance our North Star (return educator time to learning)?"
- User DNA: "Have we validated accountant pain points this quarter?"

**Attendance Team:**
- Purpose DNA: "Does attendance tracking reduce admin burden, or just digitize old processes?"
- User DNA: "Do teachers actually use our app, or default to Excel?"

**Result:** Each team maintains clarity within their domain without needing central approval.

#### 2. Cross-Team Sync Uses Builder's Hierarchy

Teams don't coordinate at the **Story level** (that would be chaos). They coordinate at the **Initiative level** using Builder's Hierarchy (Chapter 12).

**Weekly Leadership Sync (45 minutes):**
- Review **Initiatives** (not Stories): What's moving? What's blocked?
- Check **Strategy alignment**: Are Initiatives still advancing annual strategy?
- Update **North Star Metric**: Did we move the needle this week?

**Grandma's Closet becomes org-wide:** Any idea that doesn't trace to Strategy goes into a shared repository. This prevents Team A from building what Team B already parked.

**Example:**
- **Fees Team** proposed "Automated late fee calculation"
- **Grandma's Closet check** revealed **Finance Team** already parked this (didn't align with Strategy)
- **Result:** Prevented duplicate work, redirected Fees Team to higher-impact Initiative

#### 3. No Distraction Clarity Cycle Remains Consistent

The 6-Stage No Distraction Clarity Cycle (Chapter 11) doesn't change as you scale. **Every team runs it identically:**
1. Product Scope → 2. UI/UX Design → 3. Code → 4. QA → 5. Deploy → 6. Scale

**What changes:** Who participates in Clarity Gates.

**At 6 people:** Entire company in Clarity Gate (all 6 people articulate scope).

**At 50 people:** Each team's Clarity Gate includes only that team (5-7 people), but **leadership spot-checks gates quarterly** to ensure discipline isn't slipping.

**Quality enforcement:** Platform Team maintains automated MQB gates (CI/CD checks). If any team ships below quality bar, deployment fails—regardless of team size or seniority.

#### 4. Cultural DNA Carriers

We designated **Culture Carriers**—team members who embody the Product Genome and onboard new hires.

**Their role:**
- Lead Clarity Checkpoint sessions for new teams
- Conduct "Genome Onboarding" (2-hour session explaining Purpose DNA, MQB, ADRs)
- Spot entropy (teams cutting corners) and intervene early

**Not managers—influencers.** Often senior ICs who've lived the transformation.

### The Scaling Story: 6 to 50 People

**At 6 people (Year 1):** Clarity was cultural. Everyone knew the "why" instinctively.

**At 25 people (Year 2):** Clarity required structure. We formalized Purpose DNA, MQB, weekly syncs, ADRs.

**At 50 people (Year 3):** Clarity required systems. We implemented:
- Team-level Clarity Checkpoints (monthly)
- Org-wide Builder's Hierarchy (weekly leadership sync)
- Automated MQB enforcement (CI/CD gates)
- Culture Carriers (4 designated people)

**The proof:** Despite 8x headcount growth, our DORA metrics didn't degrade:
- Lead time: 12 days (unchanged)
- Deployment frequency: 2x/week (unchanged)
- Change failure rate: 11% (improved from 12%)

**Clarity didn't fragment because we made it structural, not cultural.**

---

This book began with chaos—a company drowning in technical debt, feature factory velocity, and misaligned incentives.

Over 17 chapters, we've built a comprehensive operating system for product development:

**Chapters 1-4 (Foundations):** The problem of chaos, the Product Genome solution, feature factory vs genome-driven building, and the Minimum Quality Bar as your non-negotiable standards.

**Chapters 5-10 (The Six DNAs):** The genetic code that defines what kind of product you are—Purpose (your North Star), User (your reality anchor), Experience (your quality thresholds), Architecture (your structural stability), Intelligence (your evidence engine), and Cultural (your values in action).

**Chapters 11-13 (Evolution & Execution):** The Evolution Flow Cycle (how work actually gets done), Builder's Hierarchy (strategy to execution), and real transformations (Etsy, Adobe, Netflix) showing it works.

**Chapters 14-17 (Operating System):** The Execution Playbook (month-by-month), Governance by Artifacts (making decisions visible), AI & Security (modern contexts), and Team Topologies (scaling without breaking).

---

## Your Transformation Starts Here

**The Product Genome isn't a project. It's an operating system.**

Like Linux or macOS, it's:
- **Modular**: Use what you need; ignore what you don't
- **Extensible**: Add your own DNAs, lenses, frameworks
- **Adaptive**: Evolves as your context changes
- **Open**: Built on industry research, not proprietary secrets

**The principles are timeless:**
- Purpose over features (Purpose DNA)
- Simplicity over complexity (Cognitive Load Management)
- Outcomes over outputs (Builder's Hierarchy)
- Evolution over perfection (Evolution Flow Cycle)
- Culture over process (Cultural DNA)
- Flow over control (Team Topologies)

**The Genome is sustained when it becomes the invisible default**—when teams instinctively think in DNAs, when architects apply principles without prompting, when MQB is "how we work," not "a special initiative."

That's when transformation becomes culture.

---

## The Final Word

I've spent 20 years building products—for schools, coaching institutes, corporates, and startups. I've seen chaos up close. I've created it. I've had to fix it.

The Product Genome is what I wish I'd known at the start.

It's not a silver bullet. It won't guarantee success. But it will dramatically increase your odds.

It will save you from:
- Building features no one uses (Purpose DNA, User DNA)
- Shipping fast but breaking everything (MQB, Architecture DNA)
- Making decisions based on gut feel (Intelligence DNA, Validation)
- Scaling teams but slowing down (Team Topologies, Cognitive Load)
- Losing your founding principles as you grow (Cultural DNA, Adaptive Preservation)

**The journey from chaos to clarity, from feature factory to outcome engine, from stagnation to evolution—that's the Product Genome in practice.**

Start with Chapter 14's playbooks. Audit your Purpose DNA. Define your MQB. Implement ADRs. Run the Evolution Flow Cycle. Structure your teams for flow.

One DNA at a time. One practice at a time. One decision at a time.

**Welcome to the Genome.**

**Let's build something extraordinary.**

---

## References

**Amazon Two-Pizza Teams & API Mandate:**
1. Kong Inc. (n.d.). *API Mandate: How Jeff Bezos' memo changed software forever*. Retrieved from https://konghq.com/blog/enterprise/api-mandate
2. AWS Executive Insights. (n.d.). *Amazon's Two Pizza Teams*. Retrieved from https://aws.amazon.com/executive-insights/content/amazon-two-pizza-team/
3. Nordic APIs. (n.d.). *The Bezos API Mandate: Amazon's Manifesto For Externalization*. Retrieved from https://nordicapis.com/the-bezos-api-mandate-amazons-manifesto-for-externalization/
4. Schroeder, G. F. (n.d.). *What year did Bezos issue the API Mandate at Amazon?* Medium/SLINGR. Retrieved from https://medium.com/slingr/what-year-did-bezos-issue-the-api-mandate-at-amazon-57f546994ca2

**Swiggy Order Assignment & Optimization:**
5. Swiggy Bytes. (n.d.). *Logistic Zones for Assignment*. Retrieved from https://bytes.swiggy.com/logistic-zones-for-assignment-48d9ce06c4a8
6. Swiggy Bytes. (n.d.). *The Swiggy Delivery Challenge (Part Two)*. Retrieved from https://bytes.swiggy.com/the-swiggy-delivery-challenge-part-two-f095930816e3
7. NextBillion.ai. (n.d.). *Route Optimization for Food Delivery Apps: Lessons from Swiggy and UberEats*. Retrieved from https://nextbillion.ai/blog/route-optimization-for-food-delivery-apps

**Swiggy Observability & SRE:**
8. New Relic. (n.d.). *Swiggy serves up sizzling orders, digital convenience masterclass with New Relic*. Retrieved from https://newrelic.com/customers/swiggy

**Spotify Backstage Platform:**
9. Backstage. (n.d.). *Backstage 101*. Spotify for Backstage. Retrieved from https://backstage.spotify.com/discover/backstage-101
10. Backstage. (n.d.). *Backstage Software Catalog and Developer Platform*. Retrieved from https://backstage.io/
11. Logz.io. (n.d.). *From Spotify to Open Source: The Backstory of Backstage*. Retrieved from https://logz.io/blog/from-spotify-to-open-source/
12. CNCF. (2024). *Internal Developer Platforms at scale with the Certified Backstage Associate (CBA) certification*. Retrieved from https://www.cncf.io/blog/2024/11/15/internal-developer-platforms-at-scale-with-the-certified-backstage-associate-cba-certification/
13. Humanitec. (n.d.). *Spotify Backstage - everything you need to know*. Retrieved from https://humanitec.com/spotify-backstage-everything-you-need-to-know

**Team Topologies Framework:**
14. Skelton, M., & Pais, M. (2019). *Team Topologies: Organizing Business and Technology Teams for Fast Flow*. IT Revolution Press.
15. Team Topologies. (n.d.). *Team Topologies - Official Framework*. Retrieved from https://teamtopologies.com/
16. IT Revolution. (n.d.). *Team Topologies: Key Concepts*. Retrieved from https://itrevolution.com/articles/team-topologies/

**Conway's Law:**
17. Conway, M. E. (1968). *How Do Committees Invent?* Datamation, 14(4), 28-31.
18. InfoQ. (n.d.). *Conway's Law and Team Topologies*. Retrieved from https://www.infoq.com/articles/conways-law-team-topologies/

**Cognitive Load & Scaling:**
19. Brooks, F. P. (1975). *The Mythical Man-Month: Essays on Software Engineering*. Addison-Wesley.
20. Thoughtworks. (n.d.). *Cognitive Load in Team Topologies*. Retrieved from https://www.thoughtworks.com/insights/blog/organizational-design/cognitive-load-team-topologies
21. Scrum.org. (n.d.). *An Anti-Pattern When You Scale Up the Scrum Team*. Retrieved from https://www.scrum.org/resources/blog/anti-pattern-when-you-scale-scrum-team
