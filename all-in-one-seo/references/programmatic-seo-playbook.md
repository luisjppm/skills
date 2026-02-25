# Programmatic SEO Delivery Playbook

This file defines how to plan and deliver programmatic SEO safely.

## Scope

Define execution workflow, rollout controls, QA gates, and operating model for
programmatic SEO programs.

## Load When

- You are planning or launching a pSEO initiative.
- You need rollout phases and quality-control checkpoints.
- You need delivery artifacts for engineering/content teams.

## Quick Checklist

- [ ] Validate demand, data quality, and maintainability.
- [ ] Define template, URL, canonical, and indexation rules.
- [ ] Launch in phased batches with quality gates.
- [ ] Monitor indexation, engagement, and conversion outcomes.

## Pair With

- `programmatic-playbooks.md`
- `seo-audit-playbook.md`
- `technical-seo-implementation.md`

---

## Readiness criteria

Proceed only if all are true:

- There is proven search demand for a repeatable query pattern.
- You have reliable data to power page-level differentiation.
- You can maintain freshness and quality over time.
- You can connect pages into crawlable internal link architecture.
- You can measure business outcomes beyond raw indexed pages.

## Opportunity sizing

### Pattern validation

- Define the variable pattern (for example: `[service] in [city]`).
- Estimate head and long-tail demand.
- Segment by intent: informational, comparative, transactional.

### Competitive viability

- Evaluate SERP incumbents and content quality.
- Identify value gaps you can fill with defensible data.
- Decide whether to launch narrow or broad first.

## Architecture decisions

### Data model

- Define required fields per page type.
- Set source-of-truth and refresh cadence.
- Add validation rules for missing/invalid fields.

### Template model

Each template should include:
- Intent-matched intro
- Unique data blocks
- Conditional sections driven by available data
- Related entity links
- Conversion path aligned to intent

### URL and indexation model

- Use subfolders, not subdomains.
- Predefine canonical rules.
- Separate sitemap files by page class when volume is high.
- Noindex pages that fail minimum quality thresholds.

## Quality gates

### Pre-launch gate

- Unique value demonstrated on sampled pages
- Non-duplicate titles/meta/H1 combinations
- Schema present for relevant page classes
- Core Web Vitals and crawlability baseline acceptable
- Internal links prevent orphan pages

### Post-launch gate

Monitor:
- Indexation rate and crawl waste
- Rank coverage by cluster
- Engagement and conversion quality
- Cannibalization and duplication signals
- Data staleness and template regressions

## Rollout strategy

Use phased rollout instead of full-batch publishing:

1. Pilot set: 50-200 pages in one high-confidence pattern.
2. Validate indexation, rankings, and conversion quality.
3. Fix template/data issues.
4. Expand in controlled batches.
5. Re-evaluate every expansion wave.

## Failure patterns to avoid

- Mass generation with weak data
- Thin pages created from variable swaps
- Doorway-like location or persona pages
- Overlapping URL targets causing cannibalization
- Stale or inconsistent source data

## Inputs to request

1. Target patterns and expected page count
2. Data sources, ownership, and refresh mechanism
3. CMS/templating stack and publishing workflow
4. Baseline domain authority and internal linking capacity
5. Conversion events to optimize for

## Deliverables

### Programmatic strategy brief

- Opportunity and playbook selection
- Data and template architecture
- URL/indexation/internal linking design
- Rollout and QA plan
- KPI framework

### Template spec

- Required sections and schema
- Field-level content rules
- Uniqueness requirements
- Fallback behavior for missing data
- Publish checklist
