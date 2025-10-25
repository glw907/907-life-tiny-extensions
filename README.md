# 907.life Tiny Extensions

Personal Micro.blog plugin extending the Tiny theme for [907.life](https://907.life).

## Category Logic

**also**
Posts tagged "also" are excluded from the homepage but appear in the /also/ section and archive page.

**reviews**
Posts must be tagged with both "reviews" AND a device type (dumbphones, companion-devices, auxiliary-devices, analog-tools, or software) to appear on the corresponding /reviews/{device-type}/ page.

**guides**
Posts must be tagged with both "guides" AND a topic (parenting, philosophy, research, social-friction, software, success-stories, workarounds, etc.) to appear on the corresponding /guides/{topic}/ page.

**Homepage**
Shows all posts except those tagged "also". Main smartphone-free living content appears here.

**Archive Page**
Displays two sections:
- "Article Categories": Groups categories into "Smartphone-free living" (categories without "also" posts) and "Also" (categories with "also" posts), with post counts
- "Full Article List": All posts chronologically with Font Awesome icons indicating content type (phone-slash icon for smartphone-free posts, asterisk icon for "also" posts)

## Files and Purposes

### Layouts

**layouts/index.html**
Homepage template. Lists posts excluding "also" category.

**layouts/_default/list.archivehtml.html**
Archive page template. Groups posts into "Smartphone-free living" and "Also" sections.

**layouts/also/list.html**
Lists 15 most recent posts tagged "also" (personal writing).

**layouts/guides/list.html**
Lists posts tagged with both "guides" and a specific guide subcategory.

**layouts/guides/section.html**
Displays section title and content for guides sections.

**layouts/reviews/list.html**
Lists posts tagged with both "reviews" and a specific device type.

**layouts/reviews/section.html**
Displays section title and content for reviews sections.

### Partials (Microhooks)

**layouts/partials/custom_footer.html**
Empty file to disable default Tiny footer.

**layouts/partials/microhook-archive-lead.html**
Introductory text for archive page.

**layouts/partials/microhook-footer.html**
Custom footer with navigation and copyright.

**layouts/partials/microhook-navigation.html**
Site navigation menu (Reviews, Guides, Archive, About, Also).

**layouts/partials/microhook-post-list-byline.html**
Post date/time display for post lists.

**layouts/partials/microhook-title.html**
Site title and tagline.

### Content

**content/also/_index.md**
Section index for /also/

**content/guides/{subcategory}/_index.md**
Section indexes for guide subcategories (analog-tools, auxiliary-devices, companion-devices, dumbphones, parenting, philosophy, research, social-friction, software, success-stories, workarounds).

**content/reviews/{device-type}/_index.md**
Section indexes for review subcategories (analog-tools, auxiliary-devices, companion-devices, dumbphones, software).

### Static Assets

**static/custom.css**
All custom styling: typography, colors, dark mode, layout, navigation, icons.
