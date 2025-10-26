# New Author Guide for 907.life

Welcome! This guide will help you contribute to 907.life. Whether you're writing about smartphone-free living, sharing personal experiences, or offering practical advice, this guide covers everything you need to get started.

---

## About 907.life

**Purpose**: 907.life documents the practical realities of living without a smartphone — what works, what doesn't, and how to navigate common obstacles. The site offers reviews of alternative devices, guides for specific challenges, and essays on intentional technology use.

**Philosophy**: All content on 907.life reflects four core principles:

1. **Intentionality**: Deliberate choices over defaults and conventions
2. **Accessibility**: Clear, readable content that explains complex ideas thoroughly
3. **Honesty**: Personal experience grounds all claims; transparent about limitations
4. **Focus**: Respect for reader attention; substance over polish

907.life is a multi-author site that values different voices and perspectives. Your writing doesn't need to match other contributors' styles, but it should align with these principles: be specific, honest about trade-offs, and grounded in real experience rather than theory.

---

## How to Submit Your Post

You have two options for submitting content:

### Option 1: Send a Markdown File

Write your post in Markdown (see Markdown basics below) and send the file to the site editor.

**Format Your File:**

Use a Markdown comment at the top of your file for categories, notes, and suggestions:

```markdown
<!--
Categories: guides, parenting
Notes: Not sure if "parenting" is the right category - maybe "school-workarounds"?
Could also work under "communication"
-->

# Managing School Communication Without a Smartphone

Your post content starts here...
```

**Key Points:**
- **Title**: Use a markdown heading (`# Your Title Here`) at the start of your content
- **Categories**: Suggest one or more in the comment (see Category Guide below)
- **New categories**: If existing categories don't fit, suggest a new one in the Notes
- **Author bio**: Include a short bio (see Bio Guidelines below) when sending your file

The HTML comment (`<!-- -->`) won't appear if the file is published, so it's safe to include questions, notes, or alternative category suggestions there.

### Option 2: Use Micro.blog Directly

If you're given access to the Micro.blog interface, you can post directly through the web editor.

**Finding Title and Categories**

These fields are somewhat hidden in the Micro.blog interface:

1. **Title**: Click the "Title" button in the toolbar above the editor (looks like a capital "T" or text formatting icon). This reveals a title field at the top of your post.

2. **Categories**: Click the "..." (three dots) menu button in the toolbar, then select "Categories" from the dropdown. This opens a field where you can type category names, separated by commas.

**Tips:**
- Without a title, your post will be treated as a short "micro" post
- Categories must be typed exactly as they appear in the [archive](https://907.life/archive.html)
- Multiple categories are separated by commas: `reviews, dumbphones`

See [Micro.blog's posting guide](https://help.micro.blog/t/posting-from-the-web/46) for more details on using the web interface.

---

## Writing Your Post

### Title and Categories

**Title**: Use a clear, descriptive title that indicates what the post is about. Avoid clickbait or vague titles.

- ✅ Good: "Managing School Communication Without a Smartphone"
- ❌ Avoid: "You Won't Believe This One Weird Trick"

**Categories**: Every post needs at least one category. Categories determine where your post appears on the site. If you don't see a good match in the existing categories, suggest a new one — the site evolves based on contributor needs.

#### Basic Categories

Choose the most relevant category for your post:

- `philosophy` - Conceptual thinking about technology and attention
- `workarounds` - Practical solutions to specific smartphone-dependency problems
- `success-stories` - Personal accounts of what works
- `social-friction` - Navigating social expectations and peer pressure
- `research` - Academic or scientific perspectives
- `parenting` - Challenges and solutions for parents
- And others - see the [site archive](https://907.life/archive.html) for all categories

#### Meta-Categories (Special Handling)

Some categories require additional tags and follow specific formats:

**Reviews**: Evaluations of devices, apps, or tools
- Must include: `reviews` + device type (`dumbphones`, `companion-devices`, `auxiliary-devices`, `analog-tools`, or `software`)
- Example: `categories: [reviews, dumbphones]`
- Structure:
  - Establish credibility
  - Explain your evaluation framework
  - Assess features
  - Discuss trade-offs

**Guides**: Step-by-step or practical how-to content
- Must include: `guides` + topic (e.g., `parenting`, `navigation`, `communication`)
- Example: `categories: [guides, parenting]`
- Structure:
  - Problem
  - Solution
  - Practical steps
  - Troubleshooting

**Also**: Personal or off-topic content
- Include `also` tag to exclude from main homepage
- Example: `categories: [also, alaska-adventures]`
- Note: "Also" content appears in a separate section, not the main feed

---

## Site Navigation & Content

The site is organized into several key sections:

- **Welcome** - Introduction and philosophy
- **Guides** - Practical how-to content organized by topic
- **Reviews** - Device and tool evaluations organized by type
- **Archive** - Complete chronological listing with category filters
- **About** - Site owner bio
- **Also** - Personal writing separate from main content

When writing, consider where your post will appear and what readers in that section expect to find.

---

## Style Guidelines

### Voice and Tone

Write in your own voice, but aim for:

- **Conversational authority** - Demonstrate knowledge through specificity, not credentials
- **Honesty** - Acknowledge limitations and trade-offs; avoid absolutes
- **Practical focus** - Ground claims in real experience with concrete examples

### Structure

- Keep paragraphs short (3-5 sentences typically)
- Use bullet points for lists and parallel ideas
- Start with the problem before offering solutions

### Heading Hierarchy

Use headings to organize your content into clear sections:

- **# H1**: Post title only (use once at the top)
- **## H2**: Main sections of your post (Introduction, The Problem, Solution, etc.)
- **### H3**: Subsections within a main section
- **#### H4**: Rarely needed; use only for deep nested content

**Example structure:**
```markdown
# Post Title

## Introduction

## The Core Problem

### Why This Matters
### Common Obstacles

## My Solution

### Step 1: Initial Setup
### Step 2: Daily Practice
```

Don't skip levels (e.g., don't jump from ## to ####).

### Text Emphasis

Use bold and italic sparingly for actual emphasis:

- **Bold (`**text**`)**: For important terms, key concepts, or strong emphasis. Use when you'd raise your voice slightly if speaking.
  - Example: "The **Light Phone II** has no browser at all."
  - Example: "This is **not** a minor inconvenience."

- *Italic (`*text*`)* or _Italic (`_text_`)_: For gentle emphasis, titles of works, or technical terms being introduced.
  - Example: "What I call *intentional friction* — the deliberate choice to add resistance."
  - Example: "The app uses a protocol called *XMPP*."

**Don't use formatting for:**
- Entire sentences (just makes text harder to read)
- Decoration or variety (every word becomes less meaningful)
- Section headings (use proper heading levels instead)

### Specificity

- Name actual products, situations, and obstacles
- Provide real examples from your experience
- Include numbers when relevant ("three months," "15 minutes")
- Avoid vague generalizations like "many people find..."

### What to Avoid

- ❌ Marketing language ("revolutionary," "game-changing")
- ❌ Preachy tone ("you must," "everyone should")
- ❌ Affiliate links or product promotions
- ❌ Ornamental language for its own sake

For detailed style guidance, ask the site editor for access to the internal writing documentation.

---

## About Markdown

**What is Markdown?** Markdown is a simple way to format text using plain characters. Instead of clicking formatting buttons, you type simple symbols around your text. For example, `**bold**` becomes **bold** and `*italic*` becomes *italic*.

**Why use it?** Micro.blog (the platform 907.life uses) formats all posts using Markdown. It's designed to be readable even before it's formatted — so `# Heading` looks like a heading even in plain text.

**The good news:** You probably already know most of it from texting and email. If you've ever used `*asterisks*` for emphasis or dashes for lists, you're halfway there.

---

## Markdown Quick Reference

Here are the formatting options you'll use most often:

| What You Want | What You Type | What You Get |
|---------------|---------------|--------------|
| **Heading 1** (title) | `# Heading` | <h1 style="font-size: 1.5em; margin: 0;">Heading</h1> |
| **Heading 2** (section) | `## Heading` | <h2 style="font-size: 1.3em; margin: 0;">Heading</h2> |
| **Heading 3** (subsection) | `### Heading` | <h3 style="font-size: 1.1em; margin: 0;">Heading</h3> |
| **Bold text** | `**bold**` or `__bold__` | **bold** |
| **Italic text** | `*italic*` or `_italic_` | *italic* |
| **Link** | `[link text](https://example.com)` | [link text](https://example.com) |
| **Bulleted list** | `- Item` (dash + space) | • Item |
| **Numbered list** | `1. Item` (number + period + space) | 1. Item |
| **Quote** | `> Quote text` | Indented quote block |
| **Inline code** | `` `code` `` (backticks) | `code` |

### Common Patterns

**Paragraph breaks:** Leave a blank line between paragraphs.
```markdown
First paragraph here.

Second paragraph here.
```

**Multiple list items:**
```markdown
- First item
- Second item
- Third item

1. First numbered item
2. Second numbered item
3. Third numbered item
```

**Adding images:** Upload to Micro.blog first, then insert:
```markdown
![Description of image](https://yourdomain.com/uploads/image.jpg)
```

**Block quotes:**
```markdown
> This is a quote from someone else.
> It can span multiple lines.
```

---

## Learning More

**Start here for complete documentation:**
[Markdown Guide](https://www.markdownguide.org/basic-syntax/) — Clear explanations with examples for every element

**Micro.blog-specific help:**
[Micro.blog Markdown guide](https://help.micro.blog/t/markdown-basics/45) — Platform-specific tips and features

**Quick reference:**
[CommonMark reference](https://commonmark.org/help/) — One-page cheat sheet for fast lookup

---

## Recommended Markdown Writing Tools

### macOS
- **[iA Writer](https://ia.net/writer)**: Distraction-free editor with beautiful typography and cross-platform sync.
- **[BBEdit](https://www.barebones.com/products/bbedit/)**: Professional-grade text editor with powerful search and free tier available.

### iOS/iPadOS
- **[iA Writer](https://ia.net/writer)**: Clean interface with iCloud sync to desktop versions.
- **[Drafts](https://getdrafts.com/)**: Quick-capture focused app ideal for starting posts on mobile.

### Windows
- **[Typora](https://typora.io/)**: Elegant live preview that shows formatting as you type.
- **[Obsidian](https://obsidian.md/)**: Knowledge-base focused with powerful linking and organization features.

### Linux
- **[Typora](https://typora.io/)**: Same clean live-preview experience, available across platforms.
- **[Zettlr](https://www.zettlr.com/)**: Academic-oriented editor with citation support and advanced organization.

---

## Writing Your Author Bio

All authors need a short bio (2-3 paragraphs) for the contact/contributors page.

### Guidelines

- Use first-person, active voice
- Include geographic location if comfortable
- Share relevant interests or background
- Explain your connection to the site's themes
- Keep it concise but personal

### Example Bio

Here's an example bio from one of the site's contributors:

> I'm Geoff Wright, living in Anchorage, Alaska. I grew up in Iowa, spent time in Nebraska and Maryland, and eventually settled in Alaska where I've been for [years].
>
> I love snow, cross country skiing, biking, and the kind of quiet that comes from winter darkness and sub-zero temperatures. I haven't used a smartphone in three years, which shapes how I navigate both technology and daily life.
>
> This site documents that experience — not as prescription, but as one person's experiment in reclaiming attention and building a more intentional relationship with technology.

**Your bio should**:
- Establish who you are and where you're from
- Share personal interests that paint a picture
- Connect to the site's themes (smartphone-free living, intentional technology, etc.)
- Use specific details rather than abstractions

---

## Questions?

If you have questions about contributing, reach out to the site editor. The goal is to make contributing as straightforward as possible while maintaining the site's quality and focus.

Welcome to 907.life!

---

**Last Updated**: 2025-10-25
