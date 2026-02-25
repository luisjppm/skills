---
name: master-seo
description: >
  Unified end-to-end SEO system for technical audits, on-page optimization,
  programmatic SEO at scale, AI/AEO optimization (AEO, GEO, LLMO, AI
  Overviews), structured data, E-E-A-T, international SEO, and reporting. Use
  when users ask for SEO audits, ranking issues, metadata, robots.txt, sitemaps,
  canonicals, schema markup, AI citation visibility, or scalable SEO content.
---

# Master SEO

Use this skill as the single SEO operating system. Keep the top-level workflow
in this file and load detailed references only when needed.

Goal: Improve traditional rankings and maximize AI citation visibility while
maintaining content quality and business relevance.

## Start Here

Check for product marketing context first. If
`.claude/product-marketing-context.md` exists, read it before asking questions.
Reuse that context and only ask what is missing.

Collect:

1. Site type: SaaS, ecommerce, marketplace, media, local, docs.
2. Primary objective: rankings, qualified traffic, leads, revenue, AI citations.
3. Target queries/topics and priority pages.
4. Baseline metrics: organic sessions, rankings, indexed pages, AI citations.
5. Scope: full audit, focused fix, growth strategy, or pSEO rollout.

## Reference Loading Map

Load only the file needed for the task. These references intentionally capture
the full depth of the other SEO folders.

| File | Use for |
|---|---|
| [references/seo-audit-playbook.md](references/seo-audit-playbook.md) | Full technical + on-page audit flow and report structure |
| [references/seo-foundations-playbook.md](references/seo-foundations-playbook.md) | HTML implementation snippets for metadata, robots, canonical, mobile, and hreflang |
| [references/programmatic-seo-playbook.md](references/programmatic-seo-playbook.md) | pSEO delivery workflow, rollout controls, and QA gates |
| [references/programmatic-playbooks.md](references/programmatic-playbooks.md) | Detailed 12 pSEO playbooks with value requirements |
| [references/ai-seo-playbook.md](references/ai-seo-playbook.md) | AI SEO execution workflow, prioritization, monitoring, and page-type tactics |
| [references/ai-platform-ranking-factors.md](references/ai-platform-ranking-factors.md) | Platform-specific ranking/citation behavior |
| [references/aeo-content-patterns.md](references/aeo-content-patterns.md) | Reusable answer blocks and GEO patterns |
| [references/aeo-considerations.md](references/aeo-considerations.md) | AI selection criteria and AEO/SEO balance |
| [references/structured-data-patterns.md](references/structured-data-patterns.md) | JSON-LD implementations and `@graph` patterns |
| [references/technical-seo-implementation.md](references/technical-seo-implementation.md) | Technical implementation examples (Next.js/Sanity style) |
| [references/eeat-principles.md](references/eeat-principles.md) | E-E-A-T and YMYL requirements |
| [references/ai-writing-detection.md](references/ai-writing-detection.md) | Editorial quality guardrails for human-sounding output |

Each reference has a defined scope to minimize overlap. Prefer loading one
domain file at a time, then load a second file only when the task explicitly
needs cross-domain detail.

## Core Workflow

1. Diagnose crawl/index issues first.
2. Fix technical blockers before content expansion.
3. Align page-level targeting (title/H1/URL/intent).
4. Add structured data and entity signals.
5. Improve E-E-A-T and citation quality.
6. Expand with pSEO only where data supports unique value.
7. Run AI visibility audits and platform-specific improvements.
8. Report prioritized actions with measurable outcomes.

## 1. Technical SEO Audit

Audit in this order:

1. Crawlability and indexation.
2. Canonicalization and duplicate control.
3. Performance and Core Web Vitals.
4. Mobile usability and rendering parity.
5. Metadata, redirects, and international targeting.

### Schema detection caveat (non-negotiable)

`web_fetch` and `curl` cannot reliably detect JS-injected JSON-LD.
Never report "no schema found" from static HTML alone.

Validate schema with:

1. Browser runtime check: `document.querySelectorAll('script[type="application/ld+json"]')`
2. Google Rich Results Test.
3. Screaming Frog rendered crawl export.

### Crawlability

- Review `robots.txt` for accidental blocks.
- Ensure sitemap location is declared.
- Keep important pages within three clicks.
- Prevent orphan pages via internal links and XML sitemaps.
- Control faceted/parameter URLs on large sites.

AI crawler policy check:

- Allow `GPTBot`, `ChatGPT-User`, `PerplexityBot`, `ClaudeBot`,
  `anthropic-ai`, `Google-Extended`, and `Bingbot` if AI citation is a goal.
- Decide separately on training-only crawlers such as `CCBot`.

### Indexation and canonicals

- Compare indexed vs expected URLs (Search Console + `site:` checks).
- Detect noindex misuse, canonical conflicts, redirect chains, soft 404s.
- Enforce consistency for protocol, host, and trailing slash.
- Use self-referencing canonical on unique pages.

### Performance and Core Web Vitals

Targets:

- LCP < 2.5s
- INP < 200ms
- CLS < 0.1

Focus on:

- TTFB and CDN usage.
- Image optimization and sizing.
- JS/CSS payload and execution cost.
- Font loading strategy to reduce layout shift.

### Mobile, security, and reliability

- Use responsive layouts (not separate `m.` unless required).
- Ensure viewport, tap target size, and readable base font size.
- Keep desktop/mobile content parity for mobile-first indexing.
- Enforce HTTPS everywhere, remove mixed content, configure HSTS.

### Metadata, social, and redirects

- Unique title tags and meta descriptions.
- Meta robots directives aligned with indexation intent.
- Open Graph metadata for share previews and consistency.
- Stable redirect map during migrations and URL changes.

### International SEO

- Use language-region `hreflang` and `x-default` where relevant.
- Keep canonical and hreflang coherent across locale variants.
- Ensure localized URLs are indexable and linked in sitemaps.

## 2. On-Page SEO and Content Quality

### On-page essentials

- One primary keyword/theme per page.
- Align title, H1, URL, intro paragraph, and intent.
- Use clear heading hierarchy (H1 > H2 > H3).
- Add descriptive internal links and breadcrumbs.
- Use optimized image names, alt text, and dimensions.

### Intent and coverage

- Match query intent exactly: informational, comparative, transactional.
- Answer core query quickly, then cover follow-up questions.
- Prevent cannibalization with a keyword-to-URL map.
- Build topical clusters: hub page with linked support pages.

### E-E-A-T and YMYL

Show:

- Experience: real examples, first-hand evidence, case studies.
- Expertise: qualified authors and accurate technical detail.
- Authoritativeness: external mentions and quality backlinks.
- Trustworthiness: transparent business info, policies, security.

For YMYL topics (health, finance, legal, safety), require expert review and
clear disclaimers where applicable.

### Editorial quality and AI-writing guardrails

- Keep language specific and natural, not generic or inflated.
- Avoid repetitive "AI-sounding" connectors and filler.
- Prefer concrete claims with evidence over vague adjectives.
- Use the detection checklist in
  [references/ai-writing-detection.md](references/ai-writing-detection.md)
  when polishing copy.

## 3. Programmatic SEO at Scale

Use pSEO only when pages can provide real user value.

### Core principles

1. Deliver unique value per page, not variable swaps.
2. Prioritize proprietary or defensible data sources.
3. Match search intent and conversion intent.
4. Launch quality-first; avoid mass thin-page generation.
5. Prevent doorway behavior and duplicate clusters.

### 12 playbooks

- Templates
- Curation
- Conversions
- Comparisons
- Examples
- Locations
- Personas
- Integrations
- Glossary
- Translations
- Directory
- Profiles

Load
[references/programmatic-playbooks.md](references/programmatic-playbooks.md)
for requirements, URL patterns, and combination strategies.

### Implementation sequence

1. Validate keyword pattern demand.
2. Validate data quality, ownership, and refresh cadence.
3. Design template sections with conditional and unique components.
4. Build hub-spoke internal links and sitemap segmentation.
5. Set indexation rules for thin/low-demand variants.
6. Monitor indexation, rankings, engagement, and conversions.

### Common pSEO failure modes

- Thin, repetitive pages.
- Cannibalization across near-identical templates.
- Over-generation without demand.
- Outdated source data.
- Poor UX on pages created for bots rather than users.

## 4. AI and AEO Optimization

Traditional SEO gets pages ranked. AI SEO gets sources cited.

### Baseline AI visibility audit

1. Test 10-20 priority queries across Google AI Overviews, ChatGPT, and Perplexity.
2. Record citation presence, cited pages, and competitor share.
3. Check extractability, freshness, structured data, and author signals.
4. Verify AI crawler access in `robots.txt`.

### Three pillars

1. Structure: Direct answers, self-contained blocks, clear headings.
2. Authority: Sources, statistics, expert attribution, dated updates.
3. Presence: Third-party mentions, review ecosystems, entity visibility.

Use reusable formats from
[references/aeo-content-patterns.md](references/aeo-content-patterns.md):
definition blocks, how-to steps, comparisons, FAQs, listicles, evidence blocks.

### Platform-specific focus

- Google AI Overviews: strong schema, E-E-A-T, topical clusters.
- ChatGPT: domain authority, freshness cadence, answer-format fit.
- Perplexity: FAQ schema, public PDF assets, self-contained paragraphs.
- Copilot: Bing index health, IndexNow, page speed, entity clarity.
- Claude: Brave index visibility, factual density, precise sourcing.

Load
[references/ai-platform-ranking-factors.md](references/ai-platform-ranking-factors.md)
for detailed platform behavior.

### AI-ready content by page type

- Product pages: clear definition, pricing transparency, comparison context.
- Blog guides: direct answers, original data, expert bios, update dates.
- Comparison pages: balanced tables and explicit decision criteria.
- Docs/help pages: step-by-step structure and HowTo schema.

### Monitoring

Track:

- Citation rate by platform and query set.
- Share of AI voice vs competitors.
- Sentiment/positioning in AI responses.
- Zero-click trends and snippet capture.
- Referral signals from AI surfaces where available.

## 5. Structured Data Strategy

Prioritize:

- `Organization`
- `Article` or `BlogPosting`
- `FAQPage`
- `HowTo`
- `Product`
- `Review` and `AggregateRating`
- `BreadcrumbList`
- `ItemList` for comparison/list pages

Implementation rules:

1. Align schema fields with visible page content.
2. Use `datePublished` and `dateModified` for freshness signals.
3. Combine multiple entities with `@graph` when appropriate.
4. Sanitize any user-generated data before JSON-LD serialization.

Use implementation references:

- [references/structured-data-patterns.md](references/structured-data-patterns.md)
- [references/technical-seo-implementation.md](references/technical-seo-implementation.md)
- [references/seo-foundations-playbook.md](references/seo-foundations-playbook.md)

## 6. Output Formats

### SEO audit report

- Executive summary with top issues and expected impact.
- Findings grouped by technical, on-page, and content quality.
- For each finding: issue, impact, evidence, fix, priority.
- Prioritized roadmap: critical blockers, high impact, quick wins, longer-term.

### Programmatic SEO strategy

- Opportunity and playbook selection.
- Data and template architecture.
- URL/internal link/indexation design.
- Quality gates and rollout phases.

### AI visibility report

- Query-by-platform citation baseline.
- Competitor gap analysis.
- Recommended actions by structure/authority/presence.
- 30/60/90-day measurement plan.

## 7. Task-Specific Questions

For audit projects:

1. Which pages and keywords matter most now?
2. Is Search Console and analytics access available?
3. Were there migrations or major releases recently?
4. Who are the main organic competitors?
5. What is current baseline traffic and conversion performance?

For AI/AEO projects:

1. For which queries are AI citations most important?
2. Which AI platforms matter most to the audience?
3. Are AI bots currently allowed in `robots.txt`?
4. Is structured data already implemented and validated?
5. Is there existing third-party entity presence (Wikipedia, reviews, forums)?

For pSEO projects:

1. What repeatable keyword pattern is being targeted?
2. Which data sources populate each page type?
3. How many pages are planned at launch vs later phases?
4. What prevents these pages from being thin or duplicative?
5. What stack and publishing workflow will generate and maintain pages?

## 8. Related Skills

- `schema-markup`: deep structured data implementation.
- `page-cro`: conversion optimization after traffic growth.
- `analytics-tracking`: measurement and attribution setup.
- `competitor-alternatives`: comparison-page frameworks.
- `content-strategy`: editorial planning and topic portfolio.
- `copywriting`: human-sounding, conversion-ready copy.
