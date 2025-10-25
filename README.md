# 907.life Tiny Extensions

Personal Micro.blog plugin for [907.life](https://907.life) that extends Tiny theme with content organization.

## What It Does

- **Homepage**: Shows only smartphone-free living posts (excludes "also" tagged posts)
- **Archive page**: Groups categories into "Smartphone-free living" and "Also" sections
- **Also section** (`/also/`): Lists personal writing (15 most recent)
- **Reviews pages**: `/reviews/{device-type}/` shows posts tagged with both "reviews" and device type
- **Guides pages**: `/guides/{topic}/` shows posts tagged with both "guides" and topic
- **Custom styling**: Typography, colors, dark mode, navigation, icons

## Installation

1. Push to GitHub (public repo)
2. Micro.blog → Posts → Design → Plug-ins → Find Plug-ins
3. Add repo URL
4. Set base design to Tiny

## Tagging Rules

**Main content** (appears on homepage):
```yaml
categories:
- reviews
- dumbphones
```

**Personal writing** (excluded from homepage):
```yaml
categories:
- also
- alaska adventures
```

**Reviews** (requires both tags):
```yaml
categories:
- reviews
- dumbphones  # or companion-devices, auxiliary-devices, analog-tools, software
```

**Guides** (requires both tags):
```yaml
categories:
- guides
- parenting  # or philosophy, research, social-friction, success-stories, workarounds, etc.
```

## Files

- `layouts/` - Templates overriding Tiny defaults
- `static/custom.css` - All styling (526 lines)
- `content/` - Section definitions (`_index.md` files)
- `layouts/partials/` - Microhooks (navigation, footer, title, etc.)

## Customization

**Colors**: Edit CSS variables in `static/custom.css`
**Navigation**: Edit `layouts/partials/microhook-navigation.html`
**Footer**: Edit `layouts/partials/microhook-footer.html`

## How It Works

Plugin files override Tiny theme defaults. When Tiny updates, your customizations stay intact because they're isolated in the plugin.
