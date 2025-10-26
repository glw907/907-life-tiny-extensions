# 907.life Code & CSS Guide

## Purpose

This guide establishes technical standards for templates, CSS, and code organization. All code should align with the core principles in philosophy.md: intentionality, accessibility, honesty, and focus.

**Key emphasis**: High-quality commenting that reflects design philosophy and makes the codebase understandable for future work.

---

## Commenting Standards

### Philosophy of Comments

Comments serve three purposes:
1. **Explain intent** - Why this code exists (not just what it does)
2. **Document context** - Background needed for future changes
3. **Teach patterns** - Help future you understand the approach

**Align with philosophy**:
- **Intentional**: Comments explain deliberate choices
- **Accessible**: Clear language, assume future reader needs context
- **Honest**: Acknowledge workarounds, limitations, technical debt
- **Focused**: Comment what matters, not obvious syntax

### Template Comments

**Use Hugo comment syntax**: `{{/* comment */}}`

#### File-Level Comments

Every template file should start with a header comment:

```go
{{/*
  Template: /layouts/index.html
  Purpose: Tiny homepage that lists posts (Type "post") excluding category "also".
*/}}
```

**Include**:
- Full file path (helps with debugging)
- Clear purpose statement
- Any special behavior or overrides

**Example from archive template**:
```go
{{/*
Archive Page Template

This template divides categories into two groups based on the "also" category:
- "Smartphone-free living": Categories where posts do NOT have "also" tag
- "Personal": Categories where posts DO have "also" tag

The "also" category itself is excluded from display.
*/}}
```

#### Inline Logic Comments

Comment major logic steps, not every line:

```go
{{/* 1) Only posts, newest first */}}
{{ $posts := where .Site.RegularPages "Type" "post" }}
{{ $sorted := $posts.ByDate.Reverse }}

{{/* 2) Exclude posts that have category "also" */}}
{{ $noAlso := slice }}
{{ range $sorted }}
  {{ if not (in .Params.categories "also") }}
    {{ $noAlso = $noAlso | append . }}
  {{ end }}
{{ end }}
```

**When to comment**:
- ✅ Non-obvious filtering or logic
- ✅ Workarounds for Hugo/Micro.blog limitations
- ✅ Complex loops or conditionals
- ✅ Why a microhook check exists
- ❌ Self-explanatory Hugo syntax
- ❌ Standard template patterns

#### Microhook Pattern Comments

When checking for microhook existence, note the purpose:

```go
{{/* Check for custom post list byline, fall back to default date display */}}
{{ if templates.Exists "partials/microhook-post-list-byline.html" }}
  {{ partial "microhook-post-list-byline.html" . }}
{{ else }}
  <a href="{{ .Permalink }}" class="post-date u-url">
    <time class="dt-published" datetime="{{ .Date.Format "2006-01-02 15:04:05 -0700" }}">
      {{ .Date.Format "Jan 2, 2006" }}
    </time> ∞
  </a>
{{ end }}
```

### CSS Comments

**Use block-style section headers** for major sections:

```css
/* ===================================================
   SECTION NAME
   Brief description of purpose
   Specific notes about implementation
   =================================================== */
```

**Example from custom.css**:
```css
/* ===================================================
   CSS VARIABLES
   Centralized color values for easier maintenance
   =================================================== */

:root {
  --color-link: #134d85;
  --color-text: #3a3a3a;
  /* ... */
}
```

```css
/* ===================================================
   HEADING HIERARCHY
   H1–H4 sizing and spacing for posts and pages
   - Post titles (h2.p-name) enlarged and bolded
   - Header title tuned for compact branding
   - h4 uses small caps with bottom rule
   - Reduces spacing between post date and title
   =================================================== */
```

#### CSS Section Organization

Organize CSS logically with clear section headers:

1. **CSS Variables** - All custom properties
2. **Typography + Palette** - Font families and colors
3. **Base Size + Vertical Rhythm** - Root sizing and spacing
4. **Heading Hierarchy** - H1-H6 styles
5. **Inline Text Styles** - Strong, em, etc.
6. **Lists** - UL/OL styling
7. **Links** - Anchor styles and states
8. **Layout** - Page structure, containers
9. **Navigation** - Menu and nav elements
10. **Components** - Specific UI elements (posts, archive, etc.)
11. **Utilities** - Helper classes

#### Inline CSS Comments

Use inline comments for specific rule explanations:

```css
strong, b {
  font-weight: 550; /* Mid-heavy weight for visible emphasis without harsh bold */
}

h4 {
  font-variant: small-caps;  /* Distinguishes h4 as section divider */
  border-bottom: 1px solid rgba(0, 0, 0, var(--border-opacity));  /* Visual separation */
}
```

**When to comment**:
- ✅ Non-obvious property choices
- ✅ Specific values chosen for design reasons
- ✅ Workarounds for browser quirks
- ✅ Why you're NOT using a seemingly obvious approach
- ❌ Standard CSS patterns
- ❌ Self-explanatory properties

---

## Micro.blog & Hugo Design Patterns

### Template Structure

#### Page Types

Follow Hugo's template lookup order:
- `layouts/index.html` - Homepage
- `layouts/_default/single.html` - Individual posts (usually inherit from Tiny)
- `layouts/_default/list.html` - Section lists
- `layouts/{section}/list.html` - Section-specific lists
- `layouts/{section}/section.html` - Section pages (title + content)
- `layouts/partials/*.html` - Reusable components

#### Section Templates

For category-based sections (reviews, guides):

```go
{{ define "main" }}
<div class="archive">
  <h2>{{ .Title }}</h2>
  <div class="page-content">
    {{ .Content }}
  </div>
</div>
{{ end }}
```

Keep simple—let content drive presentation.

#### List Templates

Pattern for filtered lists:

```go
{{ define "main" }}
{{/* Get current section from URL path */}}
{{ $currentSection := path.Base .RelPermalink }}

{{/* Filter posts by both parent category and specific subcategory */}}
{{ $posts := where .Site.RegularPages "Type" "post" }}
{{ $filtered := where $posts "Params.categories" "intersect" (slice "parent-category" $currentSection) }}

{{/* Display filtered posts */}}
{{ range $filtered }}
  {{/* Post display template */}}
{{ end }}
{{ end }}
```

### Microhooks (Partial Templates)

**Purpose**: Allow customization without overriding entire templates.

**Naming convention**: `microhook-{purpose}.html`

**Common microhooks**:
- `microhook-navigation.html` - Site navigation menu
- `microhook-title.html` - Site title and tagline
- `microhook-footer.html` - Footer content
- `microhook-post-list-byline.html` - Post date/time display
- `microhook-archive-lead.html` - Archive intro text

**Pattern for checking existence**:
```go
{{ if templates.Exists "partials/microhook-name.html" }}
  {{ partial "microhook-name.html" . }}
{{ else }}
  {{/* Fallback default behavior */}}
{{ end }}
```

**Best practices**:
- Only override microhooks you need to customize
- Don't create empty microhooks "just in case"
- Keep microhooks focused (single responsibility)
- Pass appropriate context with `.` parameter

### Context (The Dot)

**Critical**: Understand what `.` represents in each template context.

```go
{{ define "main" }}
  {{/* Here, . is the Page object */}}
  {{ .Title }}

  {{ range .Pages }}
    {{/* Inside range, . is the current page in loop */}}
    {{ .Title }}

    {{ with .Params.author }}
      {{/* Inside with, . is the author value */}}
      {{ . }}
    {{ end }}
  {{ end }}
{{ end }}
```

**When passing to partials**:
```go
{{ partial "name.html" . }}          {{/* Pass current context */}}
{{ partial "name.html" .Page }}      {{/* Pass specific page */}}
{{ partial "name.html" $variable }}  {{/* Pass variable */}}
```

### Variables

**Naming conventions**:
```go
{{ $posts := .Site.RegularPages }}              {{/* CamelCase for page collections */}}
{{ $filtered := where $posts "Type" "post" }}   {{/* Descriptive names */}}
{{ $currentSection := path.Base .RelPermalink }} {{/* Clear purpose */}}
```

**Scope**: Variables scoped to template/block—declare before use.

---

## CSS Standards

### CSS Variables

**Centralize values for maintainability:**

```css
:root {
  --color-link: #134d85;
  --color-text: #3a3a3a;
  --color-bg: #fdfcf9;
}
```

**Dark mode overrides:**
```css
@media (prefers-color-scheme: dark) {
  :root {
    --color-link: #8ac1ff;
    --color-text: #e6e6e6;
    --color-bg: #181818;
  }
}
```

**Benefits**:
- Single source of truth for colors
- Easy theme adjustments
- Automatic dark mode support

### Typography Implementation

**Use Micro.blog font variables:**

```css
body {
  font-family: var(--font_classical_humanist);  /* Readable serif for body */
}

h1, h2, h3, h4, h5, h6 {
  font-family: var(--font_neo-grotesque);  /* Clean sans for headings */
}
```

**Font pairing philosophy**:
- Body: Humanist/serif for comfortable long-form reading
- Headings: Neo-grotesque/sans for clear hierarchy and contrast

**Hierarchy implementation**:
```css
h1 {
  font-size: 2rem;
  line-height: 1.2;        /* Tighter for headings */
  font-weight: 650;        /* Variable font weight for nuance */
  letter-spacing: -0.02em; /* Optical adjustment for large sizes */
}
```

**Key principles**:
- Use `rem` for scalable sizing
- Tighter `line-height` for headings (1.2-1.4)
- Comfortable `line-height` for body (1.6)
- Negative `letter-spacing` for large headings
- Variable font weights (550, 650) for nuance

### Color System

**Semantic naming:**
```css
--color-link: #134d85;        /* Not --color-blue */
--color-heading-dark: #050505; /* Not --color-black */
--color-text-light: #666;     /* Not --color-gray */
```

**Opacity for borders:**
```css
--border-opacity: 0.12;

h4 {
  border-bottom: 1px solid rgba(0, 0, 0, var(--border-opacity));
}
```

**Benefits**: Adapts to dark mode automatically.

### Responsive Design

**Mobile-first approach:**

```css
html { font-size: 16px; }  /* Base size */

@media (min-width: 48rem) {
  html { font-size: 17px; }  /* Slightly larger on desktop */
}
```

**Use `rem` breakpoints** to respect user font size preferences.

### Spacing & Rhythm

**Consistent vertical spacing:**
```css
h2 { margin: 1.8rem 0 0.7rem; }  /* Top, bottom */
h3 { margin: 2rem 0 0.6rem; }
p  { margin: 0 0 1.1em; }
```

**Philosophy**: Create visual breathing room, guide eye flow.

---

## File Organization

### Directory Structure

```
layouts/
├── _default/
│   └── list.archivehtml.html      # Archive page template
├── also/
│   └── list.html                  # Also section list
├── guides/
│   ├── list.html                  # Guide filtered list
│   └── section.html               # Guide section page
├── reviews/
│   ├── list.html                  # Review filtered list
│   └── section.html               # Review section page
├── partials/
│   ├── custom_footer.html         # Empty (disables Tiny default)
│   ├── microhook-*.html           # Custom microhooks
└── index.html                     # Homepage template

static/
└── custom.css                     # All custom styles

content/
├── also/
│   └── _index.md                  # Also section index
├── guides/
│   ├── parenting/_index.md        # Guide subcategory index
│   └── ...
└── reviews/
    ├── dumbphones/_index.md       # Review subcategory index
    └── ...
```

### Naming Conventions

**Template files**:
- `list.html` - Lists of posts
- `section.html` - Section pages (title + content)
- `single.html` - Individual post pages
- `index.html` - Homepage
- `microhook-{purpose}.html` - Custom partial templates

**Content files**:
- `_index.md` - Section index files (note underscore)
- `kebab-case.md` - Post files

### What Goes Where

**layouts/**
- Template overrides for Tiny theme
- Section-specific templates
- Microhook partials

**static/**
- `custom.css` only (no CSS frameworks)
- Images if needed
- Other static assets

**content/**
- All post markdown files
- `_index.md` files for sections
- Organized by section/category if desired

---

## Micro.blog Conventions

### Semantic HTML & Microformats

**Use microformats classes** for proper Micro.blog integration:

```html
<div class="h-entry">
  <a href="{{ .Permalink }}" class="u-url">
    <time class="dt-published" datetime="{{ .Date.Format "2006-01-02 15:04:05 -0700" }}">
      {{ .Date.Format "Jan 2, 2006" }}
    </time>
  </a>
  <h2 class="p-name">{{ .Title }}</h2>
  <div class="e-content">{{ .Content }}</div>
</div>
```

**Key classes**:
- `h-entry` - Individual post wrapper
- `h-feed` - Feed of posts
- `p-name` - Post title
- `e-content` - Full post content
- `p-summary` - Post summary/excerpt
- `dt-published` - Publication date
- `u-url` - Post permalink

**Why**: These enable proper parsing by Micro.blog and IndieWeb tools.

### Date Formatting

**Standard format**:
```go
{{ .Date.Format "Jan 2, 2006" }}  /* Display format */
{{ .Date.Format "2006-01-02 15:04:05 -0700" }}  /* ISO datetime attribute */
```

**Always include ISO datetime attribute** for proper parsing:
```html
<time class="dt-published" datetime="{{ .Date.Format "2006-01-02 15:04:05 -0700" }}">
  {{ .Date.Format "Jan 2, 2006" }}
</time>
```

### Plugin Integration

**How plugins work**:
1. Base theme (Tiny) provides foundation
2. Plugin templates override specific parts
3. Static files (CSS) augment base styles
4. Content structure adds sections

**Override strategy**:
- Only override what you need to customize
- Don't duplicate entire templates for small changes
- Use microhooks when possible
- Keep overrides minimal and documented

---

## Best Practices

### Template Patterns

**✅ Good Patterns**:
```go
{{/* Clear purpose, efficient logic */}}
{{ $posts := where .Site.RegularPages "Type" "post" }}
{{ $filtered := where $posts "Params.categories" "intersect" (slice "reviews" $currentSection) }}
```

**❌ Avoid**:
```go
{{/* Unclear purpose, inefficient nested loops */}}
{{ range .Site.RegularPages }}
  {{ range .Params.categories }}
    {{ if eq . "reviews" }}
      {{/* Multiple nested loops slow rendering */}}
    {{ end }}
  {{ end }}
{{ end }}
```

### CSS Patterns

**✅ Good Patterns**:
```css
/* Semantic naming, maintainable values */
.post-title {
  color: var(--color-heading-dark);
  font-size: 1.85rem;
}
```

**❌ Avoid**:
```css
/* Magic numbers, unclear purpose */
.post-title {
  color: #050505;
  font-size: 31.45px;
}
```

### Comment Patterns

**✅ Good Comments**:
```go
{{/* Filter posts to only those with both "guides" and specific topic tags.
     This ensures guide pages only show relevant posts, not all guides. */}}
```

```css
/* Mid-heavy font weight provides visible emphasis without harsh bold,
   maintaining reading comfort in long-form content. */
strong { font-weight: 550; }
```

**❌ Avoid**:
```go
{{/* Get posts */}}  /* Too obvious */

/* Make it bold */  /* Describes what, not why */
```

---

## Technical Conventions

### Front Matter Standards

**Required fields**:
```yaml
---
title: "Post Title"
date: 2025-10-25
categories:
- primary-category
- secondary-category
---
```

**Optional fields**:
```yaml
---
draft: true          # Exclude from builds
custom_summary: true # Use .Summary instead of .Content in lists
---
```

### Markdown Content

**Use standard Markdown**:
- Headers: `#`, `##`, `###`, `####`
- Lists: `-` for unordered, `1.` for ordered
- Links: `[text](url)`
- Images: `![alt](url)`

**More tag for excerpts**:
```markdown
This appears in summary view.

<!--more-->

This only appears in full post view.
```

---

## Maintenance Checklist

### Adding New Template

- [ ] File-level comment with path and purpose
- [ ] Inline comments for non-obvious logic
- [ ] Proper context (`.`) handling
- [ ] Microformat classes if applicable
- [ ] Test with actual content

### Modifying CSS

- [ ] Section header if adding new section
- [ ] Inline comments for specific choices
- [ ] Use CSS variables for colors
- [ ] Test in light and dark mode
- [ ] Check responsive behavior

### Code Review Questions

- [ ] Does this align with philosophy (intentional, accessible, honest, focused)?
- [ ] Are comments helpful for future understanding?
- [ ] Is the code as simple as possible (but no simpler)?
- [ ] Does this follow Micro.blog/Hugo conventions?
- [ ] Is this maintainable six months from now?

---

**Version**: 1.0
**Last Updated**: 2025-10-25
**Refer to**: philosophy.md for core principles, site-guide.md for content architecture
