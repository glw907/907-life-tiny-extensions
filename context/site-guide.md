# 907.life Site Architecture Guide

## Purpose

This guide explains the information architecture, content organization, and navigation structure of 907.life. It documents how category tagging affects content display and where posts appear based on their metadata.

---

## Content Taxonomy

### Primary Content Types

**Smartphone-free living** (main content)
- Reviews of devices and tools
- Guides for practical challenges
- Philosophy and research
- Success stories and strategies
- Appears on homepage

**Also** (personal writing)
- Alaska adventures
- Philosophical musings
- Recipes and reviews
- Eclectic interests
- Excluded from homepage, shown in /also/

---

## Category Tagging Logic

### The "also" Category

**Purpose**: Separate personal writing from main smartphone-free content.

**Behavior**:
- Posts tagged "also" are **excluded from homepage**
- Appear in **/also/ section** (15 most recent)
- Appear in **archive page** under "Also" heading
- In full article list, marked with asterisk icon (⚹)

**When to use**:
```yaml
categories:
- also
- alaska adventures  # or any other personal topic
```

**When NOT to use**: For any smartphone-free living content (reviews, guides, philosophy).

### The "reviews" Category

**Purpose**: Organize device/tool reviews by type.

**Behavior**:
- Must pair with **device type** subcategory
- Appears on **/reviews/{device-type}/** pages
- **Requires both tags** to display correctly

**Device type subcategories**:
- `dumbphones`
- `companion-devices`
- `auxiliary-devices`
- `analog-tools`
- `software`

**Correct tagging**:
```yaml
categories:
- reviews
- dumbphones
```

**Incorrect tagging** (won't display on reviews pages):
```yaml
categories:
- reviews  # Missing device type!
```

### The "guides" Category

**Purpose**: Organize practical guides by topic.

**Behavior**:
- Must pair with **topic** subcategory
- Appears on **/guides/{topic}/** pages
- **Requires both tags** to display correctly

**Topic subcategories**:
- `analog-tools`
- `auxiliary-devices`
- `companion-devices`
- `dumbphones`
- `parenting`
- `philosophy`
- `research`
- `social-friction`
- `software`
- `success-stories`
- `workarounds`

**Correct tagging**:
```yaml
categories:
- guides
- parenting
```

**Incorrect tagging** (won't display on guides pages):
```yaml
categories:
- guides  # Missing topic!
```

---

## Two-Tier Architecture Design

### Overview

Reviews and Guides sections use a **two-tier template architecture** that combines manual curation with automatic filtering:

**Tier 1: Editorial Hub Pages** (`section.html`)
- Top-level pages: `/reviews/`, `/guides/`
- Display manually written content from `_index.md`
- Explain philosophy, provide context, link to subcategories
- Full editorial control over messaging and organization

**Tier 2: Auto-Filtered Lists** (`list.html`)
- Subcategory pages: `/reviews/dumbphones/`, `/guides/parenting/`
- Automatically display posts tagged with both parent + subcategory
- No manual maintenance required when adding new posts
- Consistent formatting across all subcategories

### How Hugo Determines Template Selection

Hugo differentiates based on URL depth:

**Section pages** (use `section.html`):
- `/reviews/` → `layouts/reviews/section.html`
- `/guides/` → `layouts/guides/section.html`
- Shows content from section's `_index.md`

**List pages** (use `list.html`):
- `/reviews/dumbphones/` → `layouts/reviews/list.html`
- `/guides/parenting/` → `layouts/guides/list.html`
- Filters and displays posts automatically

### Benefits of This Approach

1. **Editorial control at top level** - Explain review methodology, set expectations
2. **Automation at category level** - New posts appear automatically without template changes
3. **Flexibility** - Update hub page content without touching code
4. **Consistency** - All subcategory pages use same filtering logic
5. **Scalability** - Add new subcategories by creating `_index.md` files

### Example: Reviews Section

**Manual content** (`/reviews/`):
```markdown
All reviews on this site are based on extended real-world use...

## Review Categories

- [Dumbphones](/reviews/dumbphones/) — phones without browsers
- [Companion Devices](/reviews/companion-devices/) — tablets, laptops
...
```

**Automatic filtering** (`/reviews/dumbphones/`):
- Shows all posts tagged `["reviews", "dumbphones"]`
- Displays with icons, titles, dates, summaries
- No manual curation required

---

## Content Display Rules

### Homepage (/)

**Template**: `layouts/index.html`

**Displays**:
- All posts with `Type: "post"`
- **Excluding** posts tagged "also"
- Sorted by date (newest first)
- Paginated

**Logic**:
```go
// Pseudo-code
posts = Site.RegularPages where Type == "post"
filtered = posts where "also" NOT in categories
display(filtered, sorted by date descending)
```

**Purpose**: Show only smartphone-free living content on main feed.

### Also Section (/also/)

**Template**: `layouts/also/list.html`

**Displays**:
- Posts tagged "also"
- 15 most recent only
- Sorted by date (newest first)
- No pagination

**Purpose**: Showcase personal writing separately from main content.

### Reviews Pages (/reviews/{device-type}/)

**Template**: `layouts/reviews/list.html`

**Displays**:
- Posts tagged with **both** "reviews" AND specific device type
- All matching posts (no limit)
- Sorted by date (newest first)

**Example**: `/reviews/dumbphones/`
- Shows posts tagged: `["reviews", "dumbphones"]`
- Excludes posts tagged only `["reviews"]`

### Guides Pages (/guides/{topic}/)

**Template**: `layouts/guides/list.html`

**Displays**:
- Posts tagged with **both** "guides" AND specific topic
- All matching posts (no limit)
- Sorted by date (newest first)

**Example**: `/guides/parenting/`
- Shows posts tagged: `["guides", "parenting"]`
- Excludes posts tagged only `["guides"]`

### Archive Page (/archive.html)

**Template**: `layouts/_default/list.archivehtml.html`

**Displays two sections**:

**1. Article Categories**
- Groups categories into two sections:
  - "Smartphone-free living": Categories where posts do NOT have "also" tag
  - "Also": Categories where posts DO have "also" tag
- Shows post count for each category
- Excludes the "Also" category itself from listing

**2. Full Article List**
- All posts chronologically
- Icons indicating content type:
  - Phone-slash icon (📵): Smartphone-free posts
  - Asterisk icon (⚹): "Also" posts
- Includes date, title, and summary excerpt

**Purpose**: Comprehensive view of all content organized by theme.

---

## Navigation Structure

### Primary Navigation

Located in: `layouts/partials/microhook-navigation.html`

**Menu items**:
1. **Welcome** - Introduction and philosophy
2. **Guides** - Practical how-to content
3. **Reviews** - Device and tool evaluations
4. **Archive** - Complete content listing
5. **About** - Author bio
6. **Also** - Personal writing

**Philosophy**: Minimal, clear, functional. No dropdowns or hidden menus.

### Section Pages

Each major section has an index:
- `/also/` → `content/also/_index.md`
- `/reviews/{type}/` → `content/reviews/{type}/_index.md`
- `/guides/{topic}/` → `content/guides/{topic}/_index.md`

These use `section.html` templates to display section title and content.

---

## Visual Indicators

### Font Awesome Icons

**Purpose**: Quickly distinguish content types in lists.

**Icons used**:
- **Phone-slash** (`fa-solid fa-phone-slash`): Smartphone-free content
- **Asterisk** (`fa-solid fa-asterisk`): "Also" tagged content
- **Calendar** (`fa-regular fa-calendar`): Date indicators

**Where used**:
- Archive page article categories (section headings)
- Archive page full article list (per post)
- Post list bylines (dates)

**Philosophy**: Icons serve meaning, not decoration. Each icon communicates category information efficiently.

### Special Symbols

**Infinity symbol (∞)**
- Appears after post dates
- Suggests timelessness and archival permanence
- Reflects philosophy of creating lasting content

---

## Content Organization Best Practices

### Tagging Guidelines

**For smartphone-free content**:
- Always include relevant primary category: `reviews`, `guides`, `philosophy`, etc.
- Include specific subcategory when using `reviews` or `guides`
- Do NOT tag with "also"

**For personal content**:
- Always include "also"
- Include additional descriptive category
- Will not appear on homepage

**For multi-category content**:
- Posts can have multiple categories
- But `reviews` and `guides` require their specific subcategory pair to display on section pages

### Front Matter Examples

**Review post**:
```yaml
---
title: "Nokia 225 4G Review"
date: 2025-10-15
categories:
- reviews
- dumbphones
---
```

**Guide post**:
```yaml
---
title: "Managing School Communication Without a Smartphone"
date: 2025-10-12
categories:
- guides
- parenting
---
```

**Personal post**:
```yaml
---
title: "First Ski of the Season"
date: 2025-10-10
categories:
- also
- alaska adventures
---
```

---

## Adding New Sections

### To add a new review device type:

1. Create `content/reviews/{device-type}/_index.md`
2. Section will automatically appear in archive if posts exist
3. No template changes needed (uses existing `layouts/reviews/list.html`)

### To add a new guide topic:

1. Create `content/guides/{topic}/_index.md`
2. Section will automatically appear in archive if posts exist
3. No template changes needed (uses existing `layouts/guides/list.html`)

### To add entirely new section:

1. Create `content/{section}/_index.md`
2. Create `layouts/{section}/list.html` template
3. Add to navigation in `layouts/partials/microhook-navigation.html`
4. Update this guide to document tagging logic

---

## Common Scenarios

### "My review post isn't showing up on /reviews/dumbphones/"

**Check**:
- Post has both `reviews` AND `dumbphones` in categories
- File is in correct location (anywhere in content/)
- Post is published (not draft: true)

### "My post appears on homepage but shouldn't"

**Solution**: Add "also" to categories

### "My guide isn't appearing on the guide page"

**Check**:
- Post has both `guides` AND specific topic in categories
- Topic matches existing guide subcategory exactly

### "Archive page grouping looks wrong"

**Cause**: Likely mixing "also" tagged posts with smartphone-free content

**Solution**: Ensure clear separation—posts are either:
- Smartphone-free content (no "also" tag), OR
- Personal content (includes "also" tag)

---

**Version**: 1.0
**Last Updated**: 2025-10-25
**Refer to**: code-guide.md for template implementation details
