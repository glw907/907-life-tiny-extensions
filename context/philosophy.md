# 907.life Design Philosophy

## Core Purpose

This document establishes the foundational principles that guide all work on 907.life—from writing style to CSS implementation to template architecture. These principles reflect the site's core message: **intentional choices over defaults, substance over polish, focus over distraction**.

Just as the site advocates for deliberate technology use rather than passive smartphone dependence, every aspect of the site reflects conscious decisions about what to include and—more importantly—what to exclude.

---

## Guiding Principles

### 1. Intentionality

**Principle**: Every design and content choice must be deliberate. Nothing exists by default or convention alone.

**In Practice**:
- **Writing**: Even test posts acknowledge their purpose transparently rather than disguising themselves
- **Design**: Each CSS rule serves a specific purpose; no "just in case" styles
- **Code**: Comments explain *why* decisions were made, not just what the code does
- **Templates**: Only include microhook checks when actually used; don't cargo-cult patterns

**Questions to Ask**:
- Why does this element exist?
- What happens if we remove it?
- Is this serving the user or just convention?

### 2. Accessibility

**Principle**: Both writing and design must prioritize clarity, readability, and usability. Complex ideas receive full explanation. Design serves reading comfort.

**In Practice**:
- **Writing**: No jargon without explanation; concepts get full treatment with examples
- **Typography**: Humanist fonts for reading comfort, generous line-height (1.6), scalable sizing
- **Color**: High contrast ratios, dark mode support, warm (not harsh) backgrounds
- **Structure**: Clear hierarchy, scannable content, semantic HTML
- **Code**: Well-commented so anyone (including future you) can understand

**Questions to Ask**:
- Can someone unfamiliar with the topic understand this?
- Is this readable in different lighting conditions?
- Does the structure guide or confuse?

### 3. Honesty

**Principle**: Personal experience grounds all claims. Credibility comes through vulnerability and transparency, not credentials or marketing.

**In Practice**:
- **Writing**: First-person perspective, biographical grounding, acknowledgment of limitations
- **Reviews**: No affiliate links, no sponsorships, honest assessment of trade-offs
- **Design**: No dark patterns, no hidden functionality, straightforward navigation
- **Code**: Comments acknowledge workarounds or limitations; don't hide technical debt

**Questions to Ask**:
- Am I being transparent about limitations?
- Does this serve the reader or my ego?
- Would I feel comfortable explaining this choice publicly?

### 4. Focus

**Principle**: Remove distraction and respect reader attention. What's absent is as important as what's present.

**In Practice**:
- **Writing**: Concise paragraphs, clear structure, no ornamental language
- **Design**: Minimal navigation, no sidebars, single-column layout
- **Visual Elements**: Icons serve meaning (phone-slash = smartphone-free), not decoration
- **Code**: Clean file structure, organized CSS, no unused code

**Questions to Ask**:
- Does this add value or just noise?
- What can we remove without losing function?
- Does this respect the reader's attention?

---

## How Principles Connect Across Domains

### Writing ↔ Design

**Minimalism Reflects Philosophy**
- Reduced UI mirrors smartphone-free values: what's absent matters
- Design removes distraction just as content advocates removing triggers
- Both prioritize substance over polish

**Typography Serves Content**
- Humanist body text supports long-form reading engagement
- Heading hierarchy matches content structure (problem → solution → implementation)
- Generous spacing creates mental breathing room

**Pacing and Rhythm**
- Visual rhythm (whitespace, margins) mirrors content's message about intentional pacing
- Sentence rhythm (short declarative + longer explanatory) matches visual hierarchy
- Both create contemplative experience, not rushed consumption

### Design ↔ Code

**Structure Reflects Purpose**
- CSS organized by function (variables, typography, layout) not arbitrary
- Template comments explain *why* logic exists, not just what it does
- File naming is clear and purposeful

**Maintainability = Intentionality**
- Well-commented code allows future intentional changes
- CSS variables centralize decisions for easier iteration
- Clear template structure makes customization straightforward

**Performance = Respect**
- Minimal CSS (no frameworks) = faster load times
- Single-column layout = simpler rendering
- Efficient template logic = less server processing

### Writing ↔ Code

**Comments as Content**
- Template comments follow same clarity standards as body text
- CSS comments explain purpose, providing context for future edits
- Both should teach, not just document

**Structure as Hierarchy**
- Content sections (h2, h3, h4) map to template structure
- Category logic in code reflects editorial taxonomy in writing
- Both create navigable, understandable systems

---

## Decision-Making Framework

When facing any choice (writing, design, code), apply this hierarchy:

1. **Does it serve the user?** (Accessibility, clarity, respect for attention)
2. **Is it intentional?** (Not just convention or default)
3. **Is it honest?** (Transparent about purpose and limitations)
4. **Does it maintain focus?** (Add value or just noise?)

If the answer to any question is "no" or "I'm not sure," reconsider the choice.

### When Principles Conflict

Occasionally principles may tension with each other. Resolution order:

1. **Honesty** trumps everything (never sacrifice transparency)
2. **Accessibility** over aesthetics (readable > beautiful)
3. **Focus** over features (less is more)
4. **Intentionality** as the tiebreaker (can you explain the choice?)

**Example**: A complex animation might look interesting (aesthetics) but reduces accessibility (motion sensitivity) and focus (distraction). Principle hierarchy says: don't add it.

---

## What This Philosophy Rejects

Understanding what we *don't* do is as important as what we do:

### In Writing
- ❌ Marketing language and sales pitches
- ❌ Preachy or absolutist tone
- ❌ Vague generalizations without examples
- ❌ Perfectionism over publishing
- ❌ Ornamental language for its own sake

### In Design
- ❌ Trends over timelessness
- ❌ Novelty over usability
- ❌ Visual complexity for "interest"
- ❌ Hidden or clever navigation
- ❌ Auto-playing anything

### In Code
- ❌ Frameworks when vanilla works
- ❌ Clever code over clear code
- ❌ Cargo-culted patterns
- ❌ Uncommented "magic"
- ❌ Premature optimization

---

## Living Document

This philosophy should evolve as the site grows, but changes should be:
1. **Deliberate** - not accidental drift
2. **Documented** - update this file with reasoning
3. **Consistent** - reflected across writing, design, and code

If you find yourself repeatedly violating a principle, either:
- Recommit to the principle, or
- Revise the principle with clear reasoning

Don't let silent erosion happen.

---

**Version**: 1.0
**Last Updated**: 2025-10-25
**Next Review**: When making significant changes to site direction
