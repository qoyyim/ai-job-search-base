---
framework_version: 1.0.0
---

# Interview Preparation Guide

<!-- SETUP: STAR examples are personalized by running /setup based on your actual experience -->

## STAR Format

Structure answers as: **Situation** (context), **Task** (your responsibility), **Action** (what you did), **Result** (outcome).

Keep answers to 1-2 minutes. Be specific. End with what you learned or would do differently.

## Ready-Made STAR Examples

### 1. Redis Distributed Locks for Flash Sale Bursts (High-throughput systems)
**S:** At Bukalapak, Flash Sale events drove 10k–50k+ RPS bursts that saturated the Nginx connection pool, threatening checkout availability.
**T:** As Senior Software Engineer, I needed to prevent overselling and pool saturation under extreme burst traffic.
**A:** Designed and implemented Redis distributed locks to serialize critical inventory operations, refactored the Voucher platform from a monolithic Ruby on Rails app into microservices, and integrated payment gateways (Mandiri ClickPay, Doku Wallet, Indomaret).
**R:** Stabilized checkout under 10k–50k+ RPS bursts; platform scaled to billions of vouchers processed.
**Use for:** "Tell me about a time you handled high traffic," "system design under load," "scaling a legacy system."

### 2. Zero-Downtime Migration via GCLB Traffic Mirroring (Cloud migration)
**S:** At INA Digital Edu, the legacy Laravel platform needed upgrading without interrupting service to 100+ pilot schools (20+ live).
**T:** As Principal Software Development Engineer, I owned the migration plan with zero downtime.
**A:** Used GCLB traffic mirroring to shadow production traffic onto the upgraded platform, validated parity, then cut over; consolidated infrastructure into a Shared GCP Project.
**R:** Migration completed with zero downtime and reduced system overhead while retaining high availability.
**Use for:** "Describe a complex migration," "risk management," "zero-downtime deployment."

### 3. Cloud Cost Reduction 50%+ (Cost optimization)
**S:** At INA Digital Edu, cloud spend was high due to PostgreSQL-hosted assets on GCP.
**T:** As Software Architect, I was tasked with reducing cost without downtime or availability loss.
**A:** Migrated assets from PostgreSQL to Google Cloud Storage (GCS), optimized multi-tenant schemas and indexing strategies, and established distributed high-availability architecture standards.
**R:** Cut cloud costs by 50%+ with zero downtime; significantly decreased API response latency.
**Use for:** "Cost optimization," "architecture decisions," "balancing cost and reliability."

### 4. Legacy Codebase Rapid Ownership (Engineering recovery)
**S:** Following team turnover, an abandoned, undocumented legacy backend system at a GovTech engagement had no owner.
**T:** I took operational ownership and needed to make it maintainable quickly.
**A:** Used AI tools to map code dependencies, built safety-net unit tests, and documented the architecture in under 2 weeks.
**R:** Restored operational ownership and reduced risk of the undocumented system within 2 weeks.
**Use for:** "Tell me about a challenging situation," "learning quickly," "taking ownership," "using AI tools."

### 5. KYC Platform & Promotion Engine at Grab (Microservices at scale)
**S:** Grab needed a KYC identity verification platform and scalable promotion engines for GrabPay Singapore.
**T:** As Senior Software Engineer, I engineered high-throughput Go microservices and scaled merchant integrations.
**A:** Built Go microservices for KYC in an Agile setup, authored RFCs, and modernized airtime top-up systems with Apache Kafka for async multi-provider streaming.
**R:** Expanded merchant partner integrations and adoption; improved async processing reliability.
**Use for:** "Microservices design," "cross-functional collaboration," "scaling integrations."

### 6. AWS Cloud Migration & ERP at HIJUP (CTO leadership)
**S:** HIJUP's infrastructure was on-prem with high maintenance overhead and no auto-scaling.
**T:** As CTO, I led the full cloud migration and ERP unification.
**A:** Migrated fully to AWS (cutting server maintenance effort by 60%, enabling auto-scaling) and architected an ERP unifying POS, warehouse management, and inventory sync using MySQL and MongoDB.
**R:** Reduced maintenance effort by 60%; unified operations across POS/warehouse/inventory.
**Use for:** "Leadership experience," "cloud migration," "end-to-end system design."

### 7. Cloud Storage Document Migration & Cost Optimization
**Source:** LinkedIn export - INA Digital Edu (Software Architect)
**What happened:** Migrated document files from RDBMS to cloud storage with zero downtime, reducing cloud utilization costs by over 50%.
**Why it matters:** Answers questions on cost optimization, cloud architecture, high-availability migration, and technical leadership.
**S/T/A/R stub:**
- Situation: Large volumes of document files stored in RDBMS causing high cloud costs and scaling bottlenecks.
- Task: Design and execute a migration to cloud storage without downtime or data corruption.
- Action: Planned zero-downtime migration strategy, dual-write / sync pipeline, and cutover.
- Result: Cloud utilization costs reduced by >50% with zero downtime.

### 8. AI-Powered Help Desk Research & Deployment
**Source:** LinkedIn export - INA Digital Edu (Principal Software Development Engineer)
**What happened:** Collaborated with the help desk team to research AI-powered help desk solutions, reaching a 71% correct answer rate.
**Why it matters:** Answers questions on applied AI integration, cross-functional collaboration, customer support automation, and experimentation.
**S/T/A/R stub:**
- Situation: High support volume needing automated assistance and triage.
- Task: Research and prototype an AI-powered conversational helpdesk solution.
- Action: Partnered with support teams, built prototypes, and evaluated accuracy metrics.
- Result: Achieved 71% correct answer rate on support queries.

### 9. Paper Document Verification Automation with AI
**Source:** LinkedIn export - INA Digital Edu (Software Architect)
**What happened:** Collaborated with AI experts to automate paper document verification, cutting required human verification time and accelerating turnaround.
**Why it matters:** Answers questions on AI/OCR workflows, automation, process efficiency, and technical partnership with AI researchers.
**S/T/A/R stub:**
- Situation: Manual paper document verification for education programs was labor-intensive and slow.
- Task: Automate verification pipeline using AI/vision tools.
- Action: Integrated AI services, designed automated verification pipeline and validation checks.
- Result: Substantially reduced required manual manpower and boosted verification throughput.

### 10. High-Scale Promotions & Payment Delivery for Singapore Grab Pay
**Source:** LinkedIn export - Grab (Senior Software Engineer)
**What happened:** Supported Singapore Grab Pay team in rolling out discount promotions and managing multi-project delivery under tight deadlines.
**Why it matters:** Answers questions on high-scale fintech/payments, delivery under pressure, quality standards, and code review mentorship.
**S/T/A/R stub:**
- Situation: Grab Pay required reliable rollout of merchant and customer discount promotions across Singapore.
- Task: Develop scalable payment / promotion features while managing multiple concurrent project streams.
- Action: Applied agile methodologies, conducted thorough code reviews, and resolved complex technical bottlenecks.
- Result: Increased merchant and customer adoption, met all launch deadlines reliably.

<!-- Add more STAR examples as needed. Aim for 4-6 covering different competencies. -->

## Common Tough Questions

### "Why did you leave [previous company]?"
> [PREPARE YOUR ANSWER - be honest, forward-looking, no negativity about former employer]

### "You don't have [specific skill/experience]."
> [PREPARE YOUR ANSWER - acknowledge the gap, bridge to adjacent experience, show willingness to learn]

### "Where do you see yourself in 5 years?"
> [PREPARE YOUR ANSWER - show ambition aligned with the role's growth path]

### "What's your biggest weakness?"
> [PREPARE YOUR ANSWER - genuine weakness with concrete mitigation strategy]

### "Why this company specifically?"
> Customize per company. Must reference: specific projects, company values, market position, or team structure. Never give a generic answer.

## Questions You Should Ask Interviewers

### About the Role
- "What does a typical week look like in this role?"
- "What would success look like in the first 6 months?"
- "What's the biggest challenge the team is facing right now?"

### About the Team
- "How big is the team, and how do you divide work?"
- "What does the development/project lifecycle look like, from idea to production?"
- "How do you onboard new team members?"

### About Tech & Growth
- "What's your current tech stack for [relevant area]?"
- "Is there room to grow into more architectural or strategic decisions?"
- "How does the team stay current with new tools and methods?"

### About Culture (use these to prevent disappointment)
- "How would you describe the team culture?"
- "What does professional development look like here?"
- "Is there flexibility for remote/hybrid work?"
- "What's the balance between development/new projects and maintenance work?"
- "How would you describe the leadership style in this team?"
- "What do people who thrive here have in common?"

## Phone/Video Interview Tips
- Have STAR examples written out (use this file)
- Keep a glass of water nearby
- Smile when speaking (it changes your tone)
- Ask for clarification if a question is vague
- It's OK to take 5 seconds to think before answering
- End with: "Is there anything else you'd like to know about my background?"

## After the Application (Best Practice)

### Follow-Up Etiquette
- **Don't call to "stand out"** or to learn more about the role post-submission - this risks a negative impression
- If the employer specified a timeline, respect it and wait
- If no timeline was given and significant time has passed (2+ weeks), a brief call to ask about status is acceptable
- If you have genuinely new, relevant information to share, a short follow-up is fine

### Thank-You Notes
- When you receive any update (interview invitation, rejection, or status update), send a brief thank-you message
- Express appreciation for their time and the process
- Keep it short (2-3 sentences)

## Roleplay Guidelines
When the user asks for interview practice:
1. Ask which role/company to simulate
2. Start with easy warm-up questions ("Tell me about yourself")
3. Progress to role-specific technical questions
4. Include 1-2 behavioral questions using the competencies from the job posting
5. End with a tough question or curveball
6. After each answer, give brief feedback: what worked, what to sharpen
7. Suggest which STAR example would work best for each question
