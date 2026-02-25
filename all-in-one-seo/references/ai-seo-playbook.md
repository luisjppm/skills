# AI SEO Execution Playbook

This file is the operational workflow for AI visibility work.

## Scope

Run end-to-end AI SEO execution: baseline audit, prioritization, rollout,
measurement, and reporting.

## Load When

- You are running an AI visibility project from audit to execution.
- You need a prioritized AI SEO roadmap with owners and cadence.
- You need page-type tactics tied to measurable outcomes.

## Quick Checklist

- [ ] Build baseline visibility for the top 10-20 queries.
- [ ] Diagnose gaps by structure, authority, freshness, and schema.
- [ ] Prioritize fixes by impact, effort, and reuse.
- [ ] Define weekly/monthly monitoring and iteration loops.

## Pair With

- `ai-platform-ranking-factors.md`
- `aeo-content-patterns.md`
- `aeo-considerations.md`

---

## Inputs to collect

1. Business goals tied to AI surfaces (awareness, leads, assisted conversions).
2. Priority query set (10-20 queries by business impact).
3. Existing assets by type (product, docs, comparisons, blog, research).
4. Current visibility baseline by platform.
5. Competitors that are currently cited.

## Baseline AI visibility audit

### Step 1: Query benchmark

Test each priority query in:
- Google AI Overviews
- ChatGPT
- Perplexity
- Optional: Copilot and Claude

Capture:
- Was an AI answer shown?
- Were you cited?
- Which URL was cited?
- Which competitors were cited?
- Tone/sentiment of the answer for your brand

### Step 2: Gap diagnosis

For queries where competitors are cited and you are not, check:
- Extractability: direct answers near the top of sections
- Authority: sources, statistics, expert attribution
- Freshness: update recency and `dateModified`
- Schema: relevant JSON-LD present and valid
- Entity presence: third-party mentions and profile consistency

### Step 3: Page-level extractability checklist

- Clear definition in the first paragraph
- One intent per section with descriptive H2/H3 headings
- Self-contained answer passages
- Tables for comparisons and lists for procedures
- FAQ section where question demand exists
- Author/byline and visible update date
- Appropriate schema types validated

### Step 4: Crawler policy check

If citation visibility is a goal, confirm `robots.txt` permits:
- `GPTBot`
- `ChatGPT-User`
- `PerplexityBot`
- `ClaudeBot`
- `anthropic-ai`
- `Google-Extended`
- `Bingbot`

## Prioritization model

Score each recommended fix:

- Impact on high-value query coverage
- Effort to implement
- Time to measurable signal
- Reuse across multiple pages/templates

Prioritize in this order:
1. High impact, low effort
2. High impact, medium effort
3. Medium impact, low effort
4. Remaining backlog

## Content-type tactics

### SaaS product pages

- Put category definition and ICP in opening copy.
- Add evidence-based claims with explicit numbers.
- Publish transparent pricing and packaging details.
- Include comparison context and buyer FAQs.

### Blog and educational guides

- Answer target query directly in opening section.
- Add primary-source citations and dated statistics.
- Include author expertise and review notes where relevant.
- Link to supporting product/docs pages with clear anchors.

### Comparison and alternatives pages

- Use balanced feature tables and explicit scoring criteria.
- Keep pricing/features current with timestamped updates.
- Give recommendation by use case, not blanket winner claims.

### Documentation and help content

- Use ordered steps and prerequisites.
- Add expected outcomes and failure-mode notes.
- Implement `HowTo` schema where applicable.

## Monitoring and iteration

### Metrics to track

- Citation rate by query and platform
- Share of AI voice vs top competitors
- Cited page mix by content type
- Sentiment framing in AI answers
- AI-related referral and assisted conversion signals

### Cadence

- Weekly: priority query checks
- Monthly: full benchmark refresh and roadmap reprioritization
- Quarterly: content refresh and schema validation cycle

### Tooling

- Manual spreadsheet tracker for early phase
- Optional tools at scale: Otterly AI, Peec AI, ZipTie, LLMrefs
- Use Search Console and analytics for correlated demand/traffic signals

## Common failure modes

- Treating AI SEO as separate from core SEO health
- Over-optimizing for bots with low human clarity
- Publishing generic claims without evidence
- Ignoring freshness and stale comparisons
- Blocking relevant AI crawlers unintentionally
- Failing to monitor outcomes after implementation

## Deliverables

### AI visibility report

- Baseline benchmark table
- Competitor gap analysis
- Prioritized recommendations
- 30/60/90-day execution plan
- Measurement framework and owners

### Implementation brief (per page type)

- Required structure changes
- Required authority signals
- Required schema updates
- Internal linking updates
- Review and publish checklist
