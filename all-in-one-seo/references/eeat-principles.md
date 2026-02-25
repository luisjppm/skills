# EEAT Principles

Google's EEAT framework (Experience, Expertise, Authoritativeness, Trustworthiness) guides how content quality is evaluated. This applies to both SEO rankings and AI answer selection.

## Scope

Define trust and credibility requirements for content quality, including YMYL
constraints and author-level signals.

## Load When

- You are evaluating content quality and trust gaps.
- You are designing author/reviewer and evidence requirements.
- You are publishing in health, finance, legal, or other YMYL categories.

## Quick Checklist

- [ ] Confirm visible authorship, credentials, and review ownership.
- [ ] Confirm claims are accurate, sourced, and up to date.
- [ ] Confirm trust pages and business transparency are present.
- [ ] Confirm YMYL content has qualified expert oversight.

## Pair With

- `seo-audit-playbook.md`
- `ai-seo-playbook.md`
- `structured-data-patterns.md`

---

## The Four Pillars

### Experience
First-hand or life experience with the topic.

**Signals:**
- Personal anecdotes and case studies
- "I tested this" content
- Real-world results and screenshots
- User-generated reviews

**Implementation:**
- Include author bios with relevant experience
- Add "About the Author" sections
- Feature customer testimonials
- Show real examples, not just theory

### Expertise
Knowledge and skill in the subject area.

**Signals:**
- Credentials and qualifications
- Depth of content coverage
- Technical accuracy
- Citations to authoritative sources

**Implementation:**
- Display author credentials
- Link to primary sources
- Cover topics comprehensively
- Keep content technically accurate and updated

### Authoritativeness
Recognition as a go-to source in the field.

**Signals:**
- Backlinks from respected sites
- Mentions in industry publications
- Social proof and follower counts
- Brand recognition

**Implementation:**
- Build thought leadership content
- Contribute to industry publications
- Maintain consistent publishing
- Develop recognizable brand voice

### Trustworthiness
Accuracy, transparency, and legitimacy.

**Signals:**
- Clear authorship and contact info
- Accurate, fact-checked content
- Secure website (HTTPS)
- Privacy policy and terms

**Implementation:**
- Display clear author attribution
- Include publication and update dates
- Provide contact information
- Use HTTPS and maintain security

## Sanity Implementation

```typescript
// Author schema with EEAT signals
defineType({
  name: 'author',
  type: 'document',
  fields: [
    defineField({ name: 'name', type: 'string' }),
    defineField({ name: 'role', type: 'string' }),
    defineField({ name: 'bio', type: 'text' }),
    defineField({ name: 'credentials', type: 'array', of: [{ type: 'string' }] }),
    defineField({ name: 'image', type: 'image' }),
    // sameAs: used for schema.org Person structured data output
    defineField({ name: 'sameAs', type: 'array', of: [{ type: 'url' }],
      description: 'Canonical profile URLs (LinkedIn, Twitter, etc.) for schema.org Person'
    }),
    // socialLinks: used for display purposes (platform icons, labels)
    defineField({
      name: 'socialLinks',
      type: 'array',
      of: [{ type: 'object', fields: [
        defineField({ name: 'platform', type: 'string' }),
        defineField({ name: 'url', type: 'url' })
      ]}],
      description: 'Social links for display in the UI. Use sameAs for structured data output.'
    }),
  ]
})

// Content with EEAT metadata
defineType({
  name: 'post',
  fields: [
    defineField({ name: 'author', type: 'reference', to: [{ type: 'author' }] }),
    defineField({ name: 'publishedAt', type: 'datetime' }),
    defineField({ name: 'updatedAt', type: 'datetime' }),
    defineField({ 
      name: 'reviewedBy', 
      type: 'reference', 
      to: [{ type: 'author' }],
      description: 'Expert reviewer for fact-checking'
    }),
    defineField({
      name: 'sources',
      type: 'array',
      of: [{ type: 'url' }],
      description: 'Citations and references'
    }),
  ]
})
```

## YMYL Considerations

"Your Money or Your Life" topics (health, finance, legal, safety) require extra EEAT rigor:

- Medical content reviewed by healthcare professionals
- Financial advice from certified experts
- Legal content reviewed by attorneys
- Clear disclaimers where appropriate
