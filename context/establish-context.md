# Documentation for Claude Assistance

## Starting Prompt for Claude Code

**When this file path is provided at the start of a session, follow these steps:**

1. **Ask what type of work is being done** using the AskUserQuestion tool with these options:
   - **Writing/Content** - Drafting or editing blog posts, pages, or site content
   - **CSS/Design** - Modifying styles, typography, colors, or visual elements
   - **Templates/Architecture** - Working with Hugo templates, site structure, or navigation
   - **General/Exploratory** - Multiple tasks or exploring the codebase

2. **Load context files based on the response**:

   **For Writing/Content:**
   - `philosophy.md` - Core principles
   - `writing-guide.md` - Writing standards
   - `writing-examples.md` - Style examples

   **For CSS/Design:**
   - `philosophy.md` - Core principles
   - `code-guide.md` - Technical standards
   - `tiny-theme-reference.md` - Base theme CSS for compatibility checking

   **For Templates/Architecture:**
   - `philosophy.md` - Core principles
   - `site-guide.md` - Information architecture
   - `code-guide.md` - Technical standards
   - `tiny-theme-reference.md` - Base theme templates for reference

   **For General/Exploratory:**
   - `philosophy.md` - Core principles
   - `writing-guide.md` - Writing standards
   - `writing-examples.md` - Style examples
   - `site-guide.md` - Information architecture
   - `code-guide.md` - Technical standards
   - Optionally offer to load `tiny-theme-reference.md` if user indicates template/CSS work may be involved

3. **Understand the project**: This is a Micro.blog plugin for 907.life that extends the Tiny Hugo theme. All work must align with four core principles: intentionality, accessibility, honesty, and focus.

4. **Confirm readiness**: Briefly summarize:
   - What files were loaded based on the work type
   - Your understanding of the project
   - That you're ready to assist with the specified task

---

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
**Load**: `philosophy.md` + `writing-guide.md` + `writing-examples.md`

- Drafting new posts or pages
- Editing existing content
- Providing feedback on writing
- Suggesting structural improvements
- Ensuring voice and tone consistency

### For Design/CSS Tasks
**Load**: `philosophy.md` + `code-guide.md`

- Modifying custom.css
- Adjusting typography or colors
- Implementing new visual elements
- Maintaining design consistency
- Understanding CSS organization

### For Site Architecture Tasks
**Load**: `philosophy.md` + `site-guide.md` + `code-guide.md`

- Adding new sections or categories
- Modifying navigation
- Changing content organization
- Understanding category tagging logic
- Creating new templates

### For Any Task
**Always consider**: `philosophy.md`

The philosophy document provides the foundational principles that inform all decisions. When in doubt, choices should align with intentionality, accessibility, honesty, and focus.

## Document Overview

### philosophy.md
**What**: Core principles and values that guide all work on 907.life

**Contains**:
- Guiding principles (intentionality, accessibility, honesty, focus)
- How these principles manifest in writing, design, and code
- The philosophical connection between content and design
- Why certain choices are made

**Use when**: Making any significant decision, understanding the "why" behind existing patterns, resolving ambiguity

### writing-guide.md
**What**: Standards and patterns for all written content

**Contains**:
- Voice and tone guidelines
- Structural patterns by content type (reviews, guides, essays, pages)
- Sentence rhythm and style patterns
- Specificity and evidence standards
- What to avoid in writing

**Use when**: Creating or editing any written content, maintaining voice consistency, structuring posts

### site-guide.md
**What**: Information architecture and content organization

**Contains**:
- Category tagging logic (also, reviews, guides)
- Content display rules (homepage, archive, section pages)
- Navigation structure
- Content taxonomy and organization
- How categories affect where posts appear

**Use when**: Working with post categories, understanding content flow, adding new sections, modifying navigation

### code-guide.md
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

### writing-examples.md
**What**: Concrete examples demonstrating writing style

**Contains**:
- Excerpts from key pages showing different content types
- Before/after examples showing improvements
- Pattern demonstrations for different voices/structures
- Real samples from the actual site

**Use when**: Understanding writing style through examples rather than description, seeing patterns in action, calibrating tone

### tiny-theme-reference.md
**What**: Base Tiny theme CSS and template source code

**Contains**:
- Complete main.css from Tiny theme (651 lines)
- Full source code for key templates (baseof, single, list, index, archive)
- Microhook reference and availability
- Template override documentation
- CSS override strategy

**Use when**: Working on CSS to ensure compatibility with base theme, creating or modifying templates, understanding template inheritance, checking what base theme provides

**Note**: This file is loaded conditionally based on work type to conserve tokens. Not automatically loaded for writing tasks.

## Key Principles for Claude Assistance

1. **Consistency First**: All suggestions should align with established patterns in these documents
2. **Philosophy Grounded**: When unsure, defer to core principles in philosophy.md
3. **Context Aware**: Load relevant documents before making suggestions
4. **Pattern Recognition**: Use writing-examples.md to understand patterns, not just rules
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
├── establish-context.md      # This file - starting prompt and context instructions
├── philosophy.md             # Core principles and design philosophy
├── writing-guide.md          # Content creation standards
├── writing-examples.md       # Actual excerpts demonstrating style
├── site-guide.md            # Information architecture and navigation
├── code-guide.md            # Technical standards and commenting
└── tiny-theme-reference.md  # Base Tiny theme CSS and templates (loaded as needed)

../
├── README.md              # Plugin files and technical documentation
├── static/custom.css      # Full CSS implementation
└── layouts/               # Template files referenced in code-guide.md
```

---

**Created**: 2025-10-25
**For**: Claude Code assistance with 907.life Micro.blog plugin
