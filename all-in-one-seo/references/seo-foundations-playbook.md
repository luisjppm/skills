# SEO Foundations Implementation (HTML-first)

This file contains implementation snippets for common SEO markup.

## Scope

Provide HTML-first implementation examples for core SEO tags and technical page
signals.

## Load When

- You need concrete markup examples for page-level SEO implementation.
- You are validating metadata, robots, canonical, and hreflang setup.
- You need quick baseline snippets independent of framework.

## Quick Checklist

- [ ] Confirm unique title, description, and robots directives.
- [ ] Confirm canonical and robots.txt policies are coherent.
- [ ] Confirm mobile, HTTPS, and internal-link foundations are sound.
- [ ] Confirm hreflang and language declarations where applicable.

## Pair With

- `seo-audit-playbook.md`
- `structured-data-patterns.md`
- `technical-seo-implementation.md`

---

## Metadata

### Title and description

```html
<title>Primary Keyword | Clear Value | Brand</title>
<meta name="description" content="Concise benefit statement with intent match and CTA.">
```

Guidelines:
- Title: 50-60 characters
- Description: 150-160 characters
- Unique values per indexable page

### Meta robots

```html
<meta name="robots" content="index, follow">
<meta name="robots" content="noindex, nofollow">
<meta name="robots" content="max-snippet:150, max-image-preview:large">
```

Use `noindex` only with explicit intent and internal tracking.

### Open Graph

```html
<meta property="og:title" content="Page Title">
<meta property="og:description" content="Page Description">
<meta property="og:image" content="https://example.com/og-image.jpg">
<meta property="og:url" content="https://example.com/page">
<meta property="og:type" content="article">
```

## Canonicalization

```html
<link rel="canonical" href="https://example.com/current-page">
```

Rules:
- Prefer self-referencing canonical on unique pages.
- Keep protocol/host/slash conventions consistent.
- Avoid canonical chains.

## Robots and crawl policy

```text
# /robots.txt
User-agent: *
Allow: /
Disallow: /admin/
Disallow: /private/
Sitemap: https://example.com/sitemap.xml
```

Do not block CSS/JS required for rendering.

If AI citation is a goal, evaluate policy for:
- GPTBot
- ChatGPT-User
- PerplexityBot
- ClaudeBot
- anthropic-ai
- Google-Extended
- Bingbot

## XML sitemaps

```xml
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
  <url>
    <loc>https://example.com/</loc>
    <lastmod>2026-01-15</lastmod>
  </url>
</urlset>
```

Rules:
- Maximum 50,000 URLs or 50MB per sitemap file
- Include only canonical, indexable URLs
- Keep `lastmod` meaningful and updated

## URL and internal linking conventions

Good URL patterns:
- `https://example.com/category/page-slug`
- `https://example.com/blog/intent-focused-topic`

Guidelines:
- Lowercase with hyphens
- Keep concise and descriptive
- Avoid unnecessary query parameters for canonical pages
- Use descriptive anchor text for internal links

## Mobile foundations

### Viewport

```html
<meta name="viewport" content="width=device-width, initial-scale=1">
```

### Tap target and text baseline

```css
.interactive-target {
  min-height: 48px;
  min-width: 48px;
}

body {
  font-size: 16px;
  line-height: 1.5;
}
```

Ensure content parity between desktop and mobile rendering.

## HTTPS and trust signals

Serve all resources over HTTPS and avoid mixed content.

Recommended headers:

```text
Strict-Transport-Security: max-age=31536000; includeSubDomains
X-Content-Type-Options: nosniff
X-Frame-Options: DENY
```

## International SEO basics

### Hreflang

```html
<link rel="alternate" hreflang="en" href="https://example.com/en/page">
<link rel="alternate" hreflang="es" href="https://example.com/es/page">
<link rel="alternate" hreflang="x-default" href="https://example.com/en/page">
```

### Language declaration

```html
<html lang="en">
```

Keep canonical and hreflang mappings aligned across locale variants.

## Structured data routing

Do not duplicate schema definitions in this file.

For JSON-LD examples and `@graph` usage, load:
- `structured-data-patterns.md`
