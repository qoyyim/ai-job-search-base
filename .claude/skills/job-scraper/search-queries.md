# Search Queries for Job Scraper

## Installed portal CLIs (primary for `/scrape`)

`/scrape` discovers every portal skill under `.agents/skills/*/SKILL.md` and runs its CLI first. Shipped country-agnostic CLIs include `linkedin-search` and `freehire-search`; Danish demos and any skill you add with `/add-portal` are included the same way. You do **not** need a matching `site:` line below for those CLIs to run.

The `site:` query templates in this file are the **WebSearch fallback** — for portals without a CLI, company career pages, or when a CLI fails.

**Language scope:** English and Indonesian are candidate working languages. Queries are optimized in English for global/regional tech search.

## Search Sites

Primary:
- **linkedin.com/jobs** - LinkedIn job listings (Global Remote, Singapore, Europe, Australia, NZ, Japan, Indonesia); covered by `linkedin-search` CLI
- **freehire.me** - Aggregator across 50+ ATS platforms (Lever, Greenhouse, Ashby, Workable, etc.); covered by `freehire-search` CLI
- **tech in asia / glints / jobstreet** - Regional tech job boards in Southeast Asia

Secondary (company career pages via Google):
- Direct Google searches with `site:` filters for known tech scale-ups and global companies offering visa sponsorship

## Query Categories

Queries are grouped by priority. Write **each category in every language from your Languages table** (see Language scope above). Combine each query with your location terms (e.g. `remote`, `Singapore`, `Europe`, `Australia`, `Japan`, etc.) where the site supports it.

Each priority has two kinds of block. **Plain terms** blocks are what the portal CLIs consume: one term per line, one CLI call per term, no `OR`, no `site:` prefix, and no location (the CLI's location flag, or the city in `--query` where that portal's SKILL.md says so, carries it). Quote a multi-word phrase only if the portal's `Query syntax:` line says quoting is honoured. **WebSearch-only** blocks are Google syntax (`site:`, quotes, `OR`) for the fallback path and are never passed to a CLI.

**Organize by function, not job title.** The same underlying work carries different titles across companies and markets (a "Data Scientist" role at one employer may be posted as "Insights Analyst" or "Data Consultant" at another). Name each priority category after the function it covers, and list several plausible job titles as query variants within that category rather than betting an entire priority tier on one exact title string.

### Priority 1: Principal Software Engineer / Software Architect / Backend Engineer (primary direction)

These match your strongest career direction and deep architectural experience.

```
site:linkedin.com/jobs "Principal Software Engineer" ("Remote" OR "Worldwide")
site:linkedin.com/jobs "Software Architect" (Golang OR "Ruby on Rails" OR Cloud) "Remote"
site:linkedin.com/jobs "Principal Software Engineer" ("visa sponsorship" OR "relocation")
site:linkedin.com/jobs "Software Architect" (Singapore OR Europe OR Australia) "visa"
site:linkedin.com/jobs "Senior Backend Engineer" (Golang OR "Ruby on Rails") "Remote"
site:linkedin.com/jobs "Backend Engineer" "visa sponsorship" Singapore
site:linkedin.com/jobs "Backend Engineer" "visa sponsorship" Japan
site:linkedin.com/jobs "Backend Engineer" "visa sponsorship" Australia
site:linkedin.com/jobs "Backend Engineer" "visa sponsorship" "New Zealand"
site:linkedin.com/jobs "Backend Engineer" "visa sponsorship" Europe
site:linkedin.com/jobs "Backend Engineer" "visa sponsorship" "Middle East"
```

### Priority 2: Distributed Systems & Cloud (domain expertise)

These match your domain expertise.

#### Plain terms (portal CLIs)

```
[YOUR_PRIMARY_JOB_TITLE_1]
[YOUR_PRIMARY_JOB_TITLE_2]
[YOUR_KEY_SKILL]
```

#### WebSearch-only (`site:` fallback)

```
site:linkedin.com/jobs "Distributed Systems" "Golang" Indonesia
site:linkedin.com/jobs "Cloud" "Backend" "Golang" Singapore
site:linkedin.com/jobs "Microservices" "Ruby on Rails" Indonesia
site:linkedin.com/jobs "High-throughput" "Backend" "visa sponsorship"
site:linkedin.com/jobs "Platform Engineer" "Golang" "visa sponsorship"
site:linkedin.com/jobs "Staff Engineer" (Backend OR "Distributed Systems" OR Go) "Remote"
site:linkedin.com/jobs "Staff Software Engineer" ("visa sponsorship" OR relocation)
site:linkedin.com/jobs "Senior Backend Developer" (GCP OR Microservices) (Singapore OR "Remote")
```

### Priority 3: Applied AI & Cloud Platform Architecture & DevOps (adjacent roles)

Adjacent roles you could pivot into.

Cutting-edge roles at the intersection of systems architecture, cloud optimization, and applied AI.

#### Plain terms (portal CLIs)

```
[YOUR_DOMAIN_KEYWORD_1]
[YOUR_DOMAIN_KEYWORD_2]
```

#### WebSearch-only (`site:` fallback)

```
site:linkedin.com/jobs "Cloud Solutions Architect" (GCP OR "Cost Optimization") "Remote"
site:linkedin.com/jobs "AI Systems Engineer" OR "Applied AI Engineer" (Backend OR Python OR Go) "Remote"
site:linkedin.com/jobs ("Platform Engineer" OR "Infrastructure Architect") "Remote"
site:linkedin.com/jobs "Software Architect" "Golang" "visa sponsorship"
site:linkedin.com/jobs "Solutions Architect" "Cloud" "visa sponsorship"
site:linkedin.com/jobs "DevOps Engineer" "GCP" "visa sponsorship"
site:linkedin.com/jobs "Cloud Engineer" "AWS" "visa sponsorship"
site:linkedin.com/jobs "Technical Lead" "Backend" "visa sponsorship"
```

### Priority 4: Web Developer & Broader Technical

Wider net for general technical roles.

```
site:linkedin.com/jobs "Web Developer" "Ruby on Rails" Indonesia
site:linkedin.com/jobs "Full Stack" "Golang" "visa sponsorship"
site:linkedin.com/jobs "Backend Developer" "Ruby" "visa sponsorship"
```
### Priority 5: Technical Leadership & Engineering Management

Broader technical leadership roles leveraging 15+ years of software delivery.

#### Plain terms (portal CLIs)

```
[YOUR_KEY_SKILL] developer
technical consultant
```

#### WebSearch-only (`site:` fallback)

```
site:linkedin.com/jobs "Lead Software Engineer" "Remote"
site:linkedin.com/jobs "Engineering Lead" OR "Technical Lead" (Backend OR Cloud) "Remote"
site:linkedin.com/jobs "Head of Engineering" OR "Engineering Manager" (Backend OR Cloud)
## Location Filter

When evaluating results:
- **Ideal:** Remote Global / Worldwide, Remote APAC, or Surabaya, Indonesia
- **Acceptable (Relocation):** Europe, New Zealand, Australia, Middle East, Singapore, Japan — **requires verified visa sponsorship**
- **Borderline:** Roles requiring frequent international travel (>30%)
- **Deal-breaker (FAIL):** Mandatory on-site outside Surabaya without visa sponsorship; unverified work rights requirement without sponsorship

verify the job location is within reasonable commute distance from your home or offers visa sponsorship. Define acceptable areas:
- Surabaya / Indonesia (home base — no visa needed)
- Singapore (visa sponsorship required)
- Japan (visa sponsorship required)
- Australia (visa sponsorship required)
- New Zealand (visa sponsorship required)
- Middle East (visa sponsorship required)
- Europe (visa sponsorship required)
- Remote (full remote, anywhere) — PASS

## Language Filter

Candidate declared working languages:
- Indonesian (Native)
- English (Professional Working)

Apply `04-job-evaluation.md`'s Language Gate:
- A role requiring a language not declared (e.g. fluent German, fluent Japanese) is excluded as FAIL unless the job only requires English on the job.
- A role requiring fluent/native English is scored and flagged for candidate judgment.

Borderline: roles requiring relocation without explicit sponsorship — verify before applying.
Too far: roles requiring citizenship/PR without sponsorship pathway.

## Date Filter

Only include jobs posted within the last 14 days, matching `/scrape` Step 1b.3: use a supported recency filter or filter the returned publication dates client-side. A future application deadline does not bypass this discovery window; `/rank` handles deadline expiry and urgency separately after discovery. If a posting date cannot be determined, include it but flag as "date unknown".

## Adapting Queries

If the user specifies a focus area, select queries from the matching category and also generate 2-3 custom queries for that focus. For example:
- `/scrape "Golang remote"` -> Priority 1 & 2 Go queries filtered by remote
- `/scrape "Singapore visa sponsorship"` -> Priority 1 & 2 queries targeted to Singapore with sponsorship filters
