---
name: all-in-one-copy-and-content
description: Unified copy and content operating system for strategy, ideation, drafting, rewriting, conversion copywriting, and editing. Use when users ask for content plans, topic clusters, blog/social/email content, website page copy, headline/CTA options, or line-by-line copy improvement.
---

# All-in-One Copy and Content

Use this skill as the default end-to-end system for content and copy.
Keep this file focused on workflow and routing. Load references only as needed.

Goal: produce clear, persuasive, audience-aligned content that drives measurable outcomes.

## Start Here

Check for product marketing context first.
If `.claude/product-marketing-context.md` exists, read it before asking questions.
Reuse that context and ask only for missing, task-specific inputs.

Collect the minimum context required:

1. Business: what the product does and the primary growth goal.
2. Audience: ICP, pain points, desired outcomes, objections, and voice-of-customer language.
3. Offer: what is being sold, differentiation, and proof available.
4. Channel: where this asset will live and what readers already know.
5. Outcome: one primary action to optimize for (click, signup, demo, reply, share, purchase).

If key context is missing, ask 1-3 focused questions, then proceed with explicit assumptions.

## Mode Selection

Pick the mode that matches user intent:

1. `strategy`: content strategy, topic planning, clusters, prioritization.
2. `create`: blog, social, newsletter, and marketing content drafting.
3. `copywrite`: conversion-focused page copy (homepage, landing, pricing, feature, product, about).
4. `edit`: improve existing copy while preserving core intent.
5. `hybrid`: strategy + drafting/copywriting + editing in one sequence.

For mixed tasks, run `strategy -> create/copywrite -> edit -> QA`.

## Mode-to-Reference Contract

Use one primary file per task.

| Mode | Primary reference | Optional secondary references |
|---|---|---|
| `strategy` | `references/content-strategy-playbook.md` | `references/content-creation-formats.md` (only for production planning examples) |
| `create` | `references/content-creation-formats.md` | `references/natural-transitions.md`, `references/plain-english-alternatives.md`, `references/copy-editing-seven-sweeps.md` |
| `copywrite` | `references/conversion-copywriting-playbook.md` | `references/copy-editing-seven-sweeps.md`, `references/plain-english-alternatives.md`, `references/natural-transitions.md` |
| `edit` | `references/copy-editing-seven-sweeps.md` | `references/plain-english-alternatives.md`, `references/natural-transitions.md` |
| `hybrid` | Sequence by phase | Phase-specific file per step; do not load all files at once |

Boundary rules:

1. Do not use `content-creation-formats` for homepage/landing/pricing structure decisions.
2. Do not use `conversion-copywriting-playbook` for editorial calendars or social content ideation.
3. Do not use `copy-editing-seven-sweeps` as a replacement for strategy or first-draft generation.
4. Load `natural-transitions` and `plain-english-alternatives` only during polish passes.

## Reference Loading Map

Load only what the task needs.

| File | Load when |
|---|---|
| [references/content-strategy-playbook.md](references/content-strategy-playbook.md) | Planning pillars, clusters, searchable vs shareable strategy, idea prioritization |
| [references/content-creation-formats.md](references/content-creation-formats.md) | Writing blog/social/email assets, hooks, headline formulas, content publishing checks |
| [references/conversion-copywriting-playbook.md](references/conversion-copywriting-playbook.md) | Building high-converting page copy, section structures, CTA frameworks, page-specific guidance |
| [references/copy-editing-seven-sweeps.md](references/copy-editing-seven-sweeps.md) | Running systematic editing passes and quick-pass checks for existing copy |
| [references/natural-transitions.md](references/natural-transitions.md) | Improving flow and signposting while avoiding repetitive AI transition patterns |
| [references/plain-english-alternatives.md](references/plain-english-alternatives.md) | Replacing complex language with plain alternatives and cutting filler phrases |

Reference loading rules:

1. Start with one primary file based on mode.
2. Add a second file only when the task explicitly needs it.
3. For final polish, optionally load transitions and plain-English references.
4. Avoid loading all references by default.

## Core Workflow

1. Frame the job: audience, channel, and primary conversion event.
2. Choose the mode and load the matching reference file.
3. Produce first-pass output in the requested format.
4. Validate for clarity, specificity, benefit focus, and proof strength.
5. If editing is requested, run the seven-sweep process.
6. Deliver final output with alternatives and rationale when useful.

## Non-Negotiable Standards

Apply these in every mode:

1. Clarity over cleverness.
2. Benefits over features.
3. Specificity over vague claims.
4. Customer language over internal jargon.
5. Honest claims only; never invent proof.
6. One core idea per section.
7. Active voice and concise phrasing by default.
8. Keep the author's intent intact when editing.

## Fast Routing Rules

Use these shortcuts when intent is obvious:

1. "Plan content" or "what should we publish" -> load `content-strategy-playbook`.
2. "Write a blog/post/thread/newsletter" -> load `content-creation-formats`.
3. "Write homepage/landing/pricing copy" -> load `conversion-copywriting-playbook`.
4. "Edit/review/proofread this copy" -> load `copy-editing-seven-sweeps`.
5. "Polish tone/flow" -> add `natural-transitions`.
6. "Simplify language" -> add `plain-english-alternatives`.

## Output Contracts

### Strategy Mode

Return:

1. 3-5 content pillars with rationale.
2. Priority topic list with buyer stage and intent type.
3. Cluster map and internal-linking logic.
4. Production order (now/next/later).
5. Success metrics and tracking plan.

### Create Mode

Return:

1. Production-ready draft in channel format.
2. 2-3 headline/hook options.
3. Clear CTA options.
4. Brief rationale for major choices.

### Copywrite Mode

Return:

1. Section-by-section page copy.
2. 2-3 headline alternatives with rationale.
3. 2-3 CTA alternatives with rationale.
4. Optional SEO metadata when useful.

### Edit Mode

Return:

1. Edited copy.
2. Key issues and fixes by sweep.
3. Remaining risks (missing proof, weak offer, unclear audience, etc.).

### Hybrid Mode

Return in order:

1. Strategy summary.
2. Draft or page copy.
3. Edit notes by sweep.
4. Final polished version.

## Final QA Checklist

Before delivery, confirm:

- Audience and intent are explicit.
- Core promise is clear in the opening.
- Claims map to credible proof or are softened.
- Copy is scannable and logically sequenced.
- Tone is consistent with brand context.
- Language is plain where precision is not lost.
- CTA is specific, low-friction, and context-appropriate.
- No contradictions, grammar issues, or dead sections.

## Scope Boundary

This skill is self-contained inside `all-in-one-copy-and-content/`.
Do not depend on external folders or cross-skill references to execute the workflow.
