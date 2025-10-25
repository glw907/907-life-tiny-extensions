# Documentation for Claude Assistance

## Purpose

This documentation repository provides context for AI assistance (primarily Claude Code) when working on the 907.life Micro.blog plugin. It enables Claude to provide maximally useful help with:

- Writing and editing blog posts
- Drafting site content (pages, descriptions)
- Modifying CSS and design elements
- Adding or updating template files
- Making architectural decisions
- Maintaining consistency across writing and design

## How to Use These Documents

When assisting with tasks, reference the relevant documents to understand context and maintain consistency:

### For Writing Tasks
**Load**: `PHILOSOPHY.md` + `WRITING-GUIDE.md` + `WRITING-EXAMPLES.md`

- Drafting new posts or pages
- Editing existing content
- Providing feedback on writing
- Suggesting structural improvements
- Ensuring voice and tone consistency

### For Design/CSS Tasks
**Load**: `PHILOSOPHY.md` + `CODE-GUIDE.md`

- Modifying custom.css
- Adjusting typography or colors
- Implementing new visual elements
- Maintaining design consistency
- Understanding CSS organization

### For Site Architecture Tasks
**Load**: `PHILOSOPHY.md` + `SITE-GUIDE.md` + `CODE-GUIDE.md`

- Adding new sections or categories
- Modifying navigation
- Changing content organization
- Understanding category tagging logic
- Creating new templates

### For Any Task
**Always consider**: `PHILOSOPHY.md`

The philosophy document provides the foundational principles that inform all decisions. When in doubt, choices should align with intentionality, accessibility, honesty, and focus.

## Document Overview

### PHILOSOPHY.md
**What**: Core principles and values that guide all work on 907.life

**Contains**:
- Guiding principles (intentionality, accessibility, honesty, focus)
- How these principles manifest in writing, design, and code
- The philosophical connection between content and design
- Why certain choices are made

**Use when**: Making any significant decision, understanding the "why" behind existing patterns, resolving ambiguity

### WRITING-GUIDE.md
**What**: Standards and patterns for all written content

**Contains**:
- Voice and tone guidelines
- Structural patterns by content type (reviews, guides, essays, pages)
- Sentence rhythm and style patterns
- Specificity and evidence standards
- What to avoid in writing

**Use when**: Creating or editing any written content, maintaining voice consistency, structuring posts

### SITE-GUIDE.md
**What**: Information architecture and content organization

**Contains**:
- Category tagging logic (also, reviews, guides)
- Content display rules (homepage, archive, section pages)
- Navigation structure
- Content taxonomy and organization
- How categories affect where posts appear

**Use when**: Working with post categories, understanding content flow, adding new sections, modifying navigation

### CODE-GUIDE.md
**What**: Technical standards for CSS, templates, and implementation

**Contains**:
- CSS organization and conventions
- Typography implementation details
- Color system and variables
- Template structure and patterns
- File naming conventions
- Front matter standards
- Technical best practices

**Use when**: Writing or modifying CSS, creating templates, implementing design changes, maintaining code consistency

### WRITING-EXAMPLES.md
**What**: Concrete examples demonstrating writing style

**Contains**:
- Excerpts from key pages showing different content types
- Before/after examples showing improvements
- Pattern demonstrations for different voices/structures
- Real samples from the actual site

**Use when**: Understanding writing style through examples rather than description, seeing patterns in action, calibrating tone

## Key Principles for Claude Assistance

1. **Consistency First**: All suggestions should align with established patterns in these documents
2. **Philosophy Grounded**: When unsure, defer to core principles in PHILOSOPHY.md
3. **Context Aware**: Load relevant documents before making suggestions
4. **Pattern Recognition**: Use WRITING-EXAMPLES.md to understand patterns, not just rules
5. **Purposeful Changes**: Every change should have a reason rooted in the philosophy
6. **Question Ambiguity**: If a request conflicts with documented principles, ask for clarification
7. **Maintain Voice**: Writing assistance should sound like the site author, not generic AI output
8. **Respect Minimalism**: Don't suggest additions unless they serve a clear purpose

## Maintenance Notes

- These documents reflect the site as of creation date
- Update documents when making deliberate philosophical or stylistic shifts
- If patterns in these docs conflict with actual site content, discuss with site owner
- Revision history tracked at bottom of each document

## Directory Structure

```
context/
├── README.md                # This file - instructions for using context docs
├── PHILOSOPHY.md           # Core principles and design philosophy
├── WRITING-GUIDE.md        # Content creation standards
├── WRITING-EXAMPLES.md     # Actual excerpts demonstrating style
├── SITE-GUIDE.md          # Information architecture and navigation
└── CODE-GUIDE.md          # Technical standards and commenting

../
├── README.md              # Plugin files and technical documentation
├── static/custom.css      # Full CSS implementation
└── layouts/               # Template files referenced in CODE-GUIDE.md
```

---

**Created**: 2025-10-25
**For**: Claude Code assistance with 907.life Micro.blog plugin
