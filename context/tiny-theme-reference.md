# Tiny Theme Reference

## Purpose

This document provides reference material for the base Tiny theme that 907.life extends. Use this when working on CSS or templates to ensure custom code interacts properly with the base theme.

**Repository**: https://github.com/MattSLangford/Tiny-Theme-for-Micro.blog

---

## Base Theme CSS (main.css)

The complete CSS from the Tiny theme. Your `custom.css` loads after this and can override any of these styles.

```css
/* Light mode */
:root {
	--text: #000000;
	--link: #1565C0;
	--link_visited: #1565C0;
	--accent1: #333333;
	--accent2: #666666;
	--background: #ffffff;
	--code: #e3e3e3;
	--button-text: #ffffff;
	--blockquote: #fffee0;
	--blockquote-border: #e5d600;
	--aside: #e0f7fa;
	--aside-border: #0097a7;
	--note: #e8f5e9;
	--note-border: #d5e1d6;
	--alert: #ffebee;
	--alert-border: #d32f2f;
	--field: #fffee0;
	--mark: #FFFF99;
	--audio-link: #d32f2f;
}

/* Dark mode */
@media (prefers-color-scheme: dark) {
	:root {
		--text: #f8f8f2;
		--link: #8be9fd;
		--link_visited: #8be9fd;
		--accent1: #f8f8f2;
		--accent2: #f8f8f2;
		--background: #282a36;
		--code: #44475a;
		--button-text: #282a36;
		--blockquote: #44475a;
		--blockquote-border: #6272a4;
		--aside: #6272a4;
		--aside-border: #7797b7	;
		--note: #3f444a;
		--note-border: #4f545a;
		--alert: #ff5555;
		--alert-border: #ff6e6e;
		--field: #44475a;
		--mark: #FFFF99;
		--audio-link: #ff6e6e;
	}
}

/* Font stacks */
:root {
	--font_system_ui: system-ui, sans-serif;
	--font_transitional: Charter, 'Bitstream Charter', 'Sitka Text', Cambria, serif;
	--font_old_style: 'Iowan Old Style', 'Palatino Linotype', 'URW Palladio L', P052, serif;
	--font_humanist: Seravek, 'Gill Sans Nova', Ubuntu, Calibri, 'DejaVu Sans', source-sans-pro, sans-serif;
	--font_geometric_humanist: Avenir, Montserrat, Corbel, 'URW Gothic', source-sans-pro, sans-serif;
	--font_classical_humanist: Optima, Candara, 'Noto Sans', source-sans-pro, sans-serif;
	--font_neo_grotesque: Inter, Roboto, 'Helvetica Neue', 'Arial Nova', 'Nimbus Sans', Arial, sans-serif;
	--font_monospace_slab_serif: 'Nimbus Mono PS', 'Courier New', monospace;
	--font_monospace_code: ui-monospace, 'Cascadia Code', 'Source Code Pro', Menlo, Consolas, 'DejaVu Sans Mono', monospace;
	--font_industrial: Bahnschrift, 'DIN Alternate', 'Franklin Gothic Medium', 'Nimbus Sans Narrow', sans-serif-condensed, sans-serif;
	--font_rounded_sans: ui-rounded, 'Hiragino Maru Gothic ProN', Quicksand, Comfortaa, Manjari, 'Arial Rounded MT', 'Arial Rounded MT Bold', Calibri, source-sans-pro, sans-serif;
	--font_slab_serif: Rockwell, 'Rockwell Nova', 'Roboto Slab', 'DejaVu Serif', 'Sitka Small', serif;
	--font_antique: Superclarendon, 'Bookman Old Style', 'URW Bookman', 'URW Bookman L', 'Georgia Pro', Georgia, serif;
	--font_didone: Didot, 'Bodoni MT', 'Noto Serif Display', 'URW Palladio L', P052, Sylfaen, serif;
	--font_handwritten: 'Segoe Print', 'Bradley Hand', Chilanka, TSCu_Comic, casual, cursive;
}

body {
	max-width: 40em;
	margin: 2em auto;
	font-family: var(--font_system_ui);
	font-size: 18px;
	padding: 0 1em;
	line-height: 1.6;
	background-color: var(--background);
	color: var(--text);
}

header {
	margin-bottom: 2em;
}

.post-header {
	margin-bottom: 0;
}

header h1 a,
header h1 a:visited {
	text-decoration: none;
	color: var(--text);
}

header h1 a:hover {
	color: var(--accent1);
	text-decoration: none;
}

header p {
	margin-top: 0;
}

a {
	color: var(--link);
}

a:hover {
	text-decoration: none;
}

a:visited {
	color: var(--link_visited)
}

a.post-date {
	font-size: 0.8em;
	color: var(--link);
	text-decoration: none;
}

span.post-date {
	font-size: 0.8em;
}

a.post-date:hover {
	text-decoration: none;
}

.p-name {
	text-wrap: balance;
}

.e-content {
	margin-bottom: 2em;
	overflow-wrap: anywhere;
}

.e-content p:first-of-type,
article p:first-of-type {
	margin-top: 0;
}

img.profile_photo {
	border-radius: 80px;
}

nav ul,
ul.reply-buttons {
	list-style-type: none;
	padding: 0;
}

nav ul li,
ul.reply-buttons li {
	display: inline;
	margin-right: 0.2em;
	line-height: 2.15em;
	white-space: nowrap;
}

nav a,
nav a:visited,
nav a:hover,
a.conversation-on-mb,
a.reply-on-mastodon,
a.reply-by-email,
a.read-more {
	text-decoration: none;
	padding: 5px 10px;
	border: 1px solid var(--link);
	color: var(--link);
	border-radius: 5px;
	font-size: 0.9em;
}

nav a:hover,
a.conversation-on-mb:hover,
a.reply-on-mastodon:hover,
a.reply-by-email:hover,
a.read-more:hover {
	background: var(--link);
	color: var(--button-text);
}

button {
	cursor: pointer;
}

.reply-to {
	background: var(--code);
	border-radius: 5px;
	padding: 0 .333em;
	display: inline-block;
	font-size: 0.8em;
}

header h1 {
	margin-top: 0.2em;
	margin-bottom: 0.2em;
}

h1,
h2,
h3 {
	line-height: 1.2em;
}

h2 {
	margin-top: 0;
}

.post-nav {
	margin-top: 2.5em;
	margin-bottom: 2.5em;
	text-align: center;
}

.post-nav span {
	padding: 0 5px;
}

.post-nav a:visited {
	color: var(--link);
}

.post-meta {
	color: var(--accent2);
}

article img,
.e-content img,
.p-summary img {
	width: 100%;
	height: auto;
	border-radius: 5px;
}

ul.post-tags li {
	display: inline;
	font-size: 0.8em;
}

ul.post-tags,
ul.post-list {
	padding-left: 0;
}

ul.post-list {
	list-style-type: none;
}

ul.post-list a.u-url {
	text-decoration: none;
}

.callout {
	background: var(--code);
	padding: 1em;
	border-radius: 5px;
	margin-bottom: 2em;
}

blockquote, aside, .aside, .note, .alert, .blockquote {
	padding: 1em;
	border-left: 4px solid;
	border-radius: 0 5px 5px 0;
	font-size: 0.9em;
	margin: 1em;
}

blockquote, .blockquote {
	background: var(--blockquote);
	border-left: 4px solid var(--blockquote-border);
}

blockquote p:last-of-type, .blockquote p:last-of-type, aside p:last-of-type, .aside p:last-of-type, .alert p:last-of-type, .note p:last-of-type {
	margin-bottom: 0;
}

blockquote p:first-of-type, .blockquote p:first-of-type, aside p:first-of-type, .aside p:first-of-type, .alert p:first-of-type, .note p:first-of-type {
	margin-top: 0;
}

blockquote cite, aside cite, .aside cite {
	display: block;
	text-align: right;
	margin-top: 1em;
}

aside, .aside {
	background: var(--aside);
	border-left: 4px solid var(--aside-border);
}

.note {
	background: var(--note);
	border-left: 4px solid var(--note-border);
	font-style: italic;
}

@keyframes blinkBorder {
  0%, 100% { border-color: var(--alert-border); } /* Default border color */
  50% { border-color: var(--alert); } /* Blink to black */
}

.alert {
	background: var(--alert);
	border-left: 4px solid var(--alert-border);
	font-weight: bold;
	animation: blinkBorder 2s infinite ease-in-out;
}

div.highlight div {
	border-radius: 5px;
}

hr {
	margin: 2em 0;
	border: none;
	text-align: center;
}

hr::before {
	content: "•••••";
	display: block;
	color: var(--link);
}

sup a {
	text-decoration: none;
}

.footnote-backref {
	text-decoration: none;
}

.microblog_conversation {
	margin-top: 2em;
	margin-bottom: 2em;
}

.microblog_post {
	margin-bottom: 1em;
	padding: 1em;
	border: 1px solid var(--code);
	border-radius: 5px;
}

.microblog_user {
	font-weight: bold;
}

.microblog_user img {
	vertical-align: middle;
	width: 40px;
	height: auto;
	border-radius: 40px;
	max-width: 40px !important;
}

.microblog_text img {
	max-width: 100%;
	border-radius: 5px;
}

.microblog_time a,
.microblog_time a:visited {
	color: var(--accent2);
	font-size: 0.8em;
	text-decoration: none;
}

.microblog_narration_button {
	color: var(--audio-link);
}

.microblog_narration_button span {
	vertical-align: baseline !important;
}

footer {
	margin-top: 2em;
	text-align: center;
}

footer .custom_footer {
	font-size: 0.75em;
	color: var(--accent2);
}

footer .attribution {
	display: none;
}

footer i {
	font-size: 1.5em;
	padding: 0 5px;
}

footer a i:hover {
	color: var(--text);
}

.full-archives {
	overflow-wrap: anywhere;
}

p>code,
li>code,
span.tinylytics_hits,
span.tinylytics_uptime {
	background: var(--code);
	padding: 2px 4px;
	font-size: 0.9em;
	border-radius: 5px;
	font-family: var(--font_monospace_code);
}

.tinylytics_countries {
	font-size: 1.5em;
	line-height: 1em;
}

mark {
	background: var(--mark);
	color: var();
}

.tiny-img {
	max-width: 25em;
}

.tiny-text {
	font-size: 0.6em;
}

/* IF USING THE TINY THEME ADD ON FOR SUMMARY POSTS */

.p-summary {
	margin-bottom: 2em;
}

/* IFRAME FIX */
iframe {max-width: 100%;}

/* MAKES VIDEO EMBEDS THAT DON'T USE IFRAME RESPONSIVE. DOES NOT WORK WITH YOUTUBE. */
video {
	width: 100% !important;
	height: auto !important;
	background: var(--code);
	border-radius: 5px;
}

/* Styling specific to Tinylytics Plugin */

.did_select {
	background: var(--link);
	color: var(--button-text);
	opacity: 0.8;
	cursor: not-allowed;
}

.tinylytics_webring {
	align-items: center;
	display: flex;
	flex-direction: row;
	gap: 3px;
	justify-content: center;
}

a.tinylytics_webring {
	text-decoration: none;
}

.tinylytics_webring_avatar {
	width: auto;
	height: 1.75em;
	border-radius: 100%;
}

/* STYLING TO TWEAK CODE BLOCKS (SYNTAX HIGHLIGHTING) */

.highlight {
	font-size: 0.9em;
	line-height: 1em;
}

pre {
	overflow: auto;
	padding: 1em;
}

/* OVERRIDING DEFAULT MICROBLOG AND PLUGIN CSS. Using !important isn't ideal, but it's the most effective for these things. */

.photos-grid-container {
	grid-column-gap: 5px !important;
}

input[type=text],
input[type=password],
input[type=email],
input[type=url],
input[type=tel],
input[type=search],
input[type=number],
textarea {
	padding: 10px;
	font-size: 0.9em;
	border: 1px solid var(--link) !important;
	border-radius: 5px !important;
	color: var(--text);
	display: block;
	height: auto;
	background: var(--field);
	margin: 5px 0;
}

input[type=submit],
button {
	vertical-align: baseline;
	padding: 5px 10px;
	font-size: 0.9em;
	border-radius: 5px;
	border: 1px solid var(--link);
	background: none;
	color: var(--link);
	-webkit-appearance: none;
	margin-top: 5px;
	font-weight: normal;
	cursor: pointer;
}

input[type=submit]:hover,
button:hover {
	background: var(--link);
	color: var(--button-text);
}

label {
	font-weight: bold;
}

form p {
	margin-bottom: 0;
}

#search-space-info {
	font-size: 0.9em;
	font-style: italic;
}

.bookshelf_book {
	margin-bottom: 2em;
}

.bookshelf_title {
	font-weight: bold;
}

.bigfoot-footnote__content {
	color: #000;
}

.microblog_shared_note {
	background: red;
	margin: 0 auto;
	padding: 5px;
	border-radius: 5px;
	color: white;
	width: fit-content;
}

.blogroll li a {
	color: var(--text);
	text-decoration: none;
}

.blogroll li a span {
	color: var(--link);
	text-decoration: underline;
}

.blogroll li a span:hover {
	text-decoration: none;
}

.microblog_reply_textarea textarea {
	width: calc(100% - 2em);
	border-radius: 5px;
	border: 1px solid var(--code);
	padding: 1em;
	font-size: 1em;
}

.microblog_reply_button {
	margin-top: 0;
}

/* Adaptive Photo Layout Feature */

.adaptive_photo_layout ul {
	display: grid;
	grid-template-columns: repeat(auto-fill, minmax(200px, 1fr)); /* Flexible grid items */
	gap: 10px; /* Adds spacing between items */
	padding: 0;
	margin: 0;
	list-style: none;
	align-items: start; /* Aligns items at the top of the container */
}

.adaptive_photo_layout li {
	display: block; /* Block display for better control over individual items */
	width: 100%;
	overflow: hidden; /* Keeps images within the boundaries */
	border-radius:5px;
}

.adaptive_photo_layout img {
	width: 100%; /* Ensures the image scales up to the container width */
	height: auto; /* Allows height to adjust naturally, preserving the image's aspect ratio */
	object-fit: cover; /* Covers the area, ensures no white space around images */
	vertical-align: bottom;
	border-radius: 0;
	transition: transform 0.3s ease, opacity 0.3s ease; /* Smooth transition for transform and opacity */
}

.adaptive_photo_layout img:hover {
	transform: scale(1.05); /* Slightly enlarges the image */
	opacity: 0.9; /* Slightly reduces the opacity */
}

@media (max-aspect-ratio: 1/1) {
	.adaptive_photo_layout li {
		height: auto; /* Auto height for more natural flow */
	}
}

@media (max-height: 480px) {
	.adaptive_photo_layout li {
		height: auto; /* Consistent with masonry style, allowing natural height */
	}
}

@media (max-aspect-ratio: 1/1) and (max-width: 480px) {
	.adaptive_photo_layout ul {
		grid-template-columns: 100%; /* One column layout for very narrow screens */
	}

	.adaptive_photo_layout li {
		height: auto;
	}
}
```

---

## Base Theme Templates

Full template source code from the Tiny theme. Use these for reference when creating overrides or understanding template inheritance.

**Repository**: https://github.com/MattSLangford/Tiny-Theme-for-Micro.blog/tree/main/layouts

### layouts/_default/baseof.html

Base HTML structure. All other templates extend this.

```html
<!DOCTYPE html>
<html lang="en">

{{ partial "head.html" . }}

<body>
  {{ partial "header.html" . }}

  <div class="page-content">
    <div class="wrapper">
      {{ block "main" . }}{{ end }}
    </div>
    {{ if templates.Exists "partials/microhook-below-wrapper.html" }}
          {{ partial "microhook-below-wrapper.html" . }}
    {{ end }}
  </div>
  {{ partial "footer.html" . }}

  {{ range .Site.Params.plugins_js }}
  <script src="{{ . }}"></script>
  {{ end }}

  {{ if templates.Exists "partials/microhook-before-closing-body.html" }}
  {{ partial "microhook-before-closing-body.html" . }}
  {{ end }}
</body>

</html>
```

### layouts/_default/single.html

Individual post/page display.

```html
{{ define "main" }}
<div class="page">

  {{ if templates.Exists "partials/microhook-before-page-content.html" }}
  {{ partial "microhook-before-page-content.html" . }}
  {{ end }}

  {{ if .Title }}
  <h2 class="p-name">{{ .Title }}</h2>
  {{ end }}

  {{ if .Params.reply_to_url }} <a href="{{ .Permalink }}" class="post-date u-url"><time class="dt-published" datetime="{{ .Date.Format "2006-01-02 15:04:05 -0700" }}">{{ .Date.Format "Jan 2, 2006" }}</time> ∞</a>
  <div class="reply-to"> Replying to: {{ if eq .Params.reply_to_hostname "micro.blog" }} <a href="{{ .Params.reply_to_url }}" class="u-in-reply-to">@{{ .Params.reply_to_username }}</a> {{ else }} <a href="{{ .Params.reply_to_url }}" class="u-in-reply-to">{{ .Params.reply_to_hostname }}</a> {{ end }} </div> {{ end }}

  <article class="post-content">
    {{ .Content }}
  </article>

  {{ if templates.Exists "partials/microhook-after-page-content.html" }}
  {{ partial "microhook-after-page-content.html" . }}
  {{ end }}

</div>
{{ end }}
```

### layouts/_default/list.html

Archive and category pages with pagination.

```html
{{ define "main" }}
{{ if templates.Exists "partials/microhook-archive-post-list.html" }}
{{ partial "microhook-archive-post-list.html" . }}
{{ else }}
<div class="archive h-feed {{ .Title }}">

  <h2 class="p-name category-title">{{ .Title }}</h2>
{{ if templates.Exists "partials/microhook-category-header.html" }}
  {{ partial "microhook-category-header.html" . }}
{{ end }}
{{ if .Description }}
<div class="list-description">{{ .Description | markdownify }}</div>
{{ end }}
  <ul class="post-list">
    {{ $paginator := .Paginate (where .Pages.ByDate.Reverse "Type" "post") }}
    {{ range .Paginator.Pages  }}
    <div class="post-preview h-entry {{ range .Params.categories }} {{ . | urlize | lower }}{{ end }}">
      {{ if templates.Exists "partials/microhook-post-list-byline.html" }}
      {{ partial "microhook-post-list-byline.html" . }}
      {{ else }}
      <a href="{{ .Permalink }}" class="post-date u-url"><time class="dt-published" datetime="{{ .Date.Format "2006-01-02 15:04:05 -0700" }}">{{ .Date.Format "Jan 2, 2006" }}</time> ∞</a>
      {{ end }}
      {{ if .Title }}
          <h2 class="post-title p-name"><a href="{{ .Permalink }}">{{ .Title }}</a></h2>
              {{ if in .RawContent "<!--more-->" }}
              <div class="p-summary">
                  {{ $splitContents := split .RawContent "<!--more-->" }}
                  {{ index $splitContents 0 | markdownify }}
                  <p><a class="read-more" href="{{ .Permalink }}">
                      {{ if templates.Exists "partials/microhook-read-more-text.html" }}
                      {{ partial "microhook-read-more-text.html" . }}
                      {{ else }}
                      Read More →
                      {{ end }}
                  </a></p>
              </div>
              {{ else if .Params.custom_summary }}
              <div class="p-summary">
                  <p>{{ .Summary | safeHTML }}<p>
              </div>
              {{ else }}
              <div class="e-content">
                  {{ .Content }}
              </div>
              {{ end }}
      {{ else }}
          <div class="e-content">
              {{ .Content }}
          </div>
      {{ end }}
      {{ if templates.Exists "partials/microhook-below-post-in-list.html" }}
      {{ partial "microhook-below-post-in-list.html" . }}
      {{ end }}
      {{ if .Params.bluesky }}
      <a class="u-syndication" {{ printf "href=%q" .Params.bluesky.url | safeHTMLAttr }} style="display: none;">Also on Bluesky</a>
      {{ end }}
    </div>
    {{ end }}
  </ul>
</div>
{{ if templates.Exists "partials/microhook-pagination.html" }}
{{ partial "microhook-pagination.html" . }}
{{ else }}
<div class="post-nav">
  {{ if $paginator.HasPrev }}
  <span class="prev">
    <a href="{{ $paginator.Prev.URL }}" title="Previous Page"><span class="arrow">← Newer Posts</span></a>
  </span>
  {{ end }}
  {{ if $paginator.HasNext }}
  <span class="next">
    <a href="{{ $paginator.Next.URL }}"><span class="arrow">Older Posts →</span></a>
  </span>
  {{ end }}
</div>
{{ end }}
{{ end }}
{{ end }}
```

### layouts/index.html

Homepage template with post list.

```html
{{ define "main" }}
{{ if templates.Exists "partials/microhook-post-list.html" }}
{{ partial "microhook-post-list.html" . }}
{{ else }}

{{ if templates.Exists "partials/microhook-before-post-list.html" }}
{{ partial "microhook-before-post-list.html" . }}
{{ end }}
<div class="posts h-feed">
    <div class="post_list" role="main">
        {{ $paginator := .Paginate (where .Site.Pages.ByDate.Reverse "Type" "post") }}
        {{ range .Paginator.Pages }}
        <div class="post-preview h-entry {{ range .Params.categories }} {{ . | urlize | lower }}{{ end }}">
            {{ if templates.Exists "partials/microhook-post-list-byline.html" }}
            {{ partial "microhook-post-list-byline.html" . }}
            {{ else }}
            <a href="{{ .Permalink }}" class="post-date u-url"><time class="dt-published" datetime="{{ .Date.Format "2006-01-02 15:04:05 -0700" }}">{{ .Date.Format "Jan 2, 2006" }}</time> ∞</a>
            {{ end }}
            {{ if .Title }}
                <h2 class="post-title p-name"><a href="{{ .Permalink }}">{{ .Title }}</a></h2>
                    {{ if in .RawContent "<!--more-->" }}
                        <div class="p-summary">
                            {{ $splitContents := split .RawContent "<!--more-->" }}
                            {{ $summary := index $splitContents 0 }}
                            {{ $summary := replaceRE "\\[\\^.*?\\]" "" $summary }}
                            {{ $summary := replaceRE "\\n\\[\\^.*?\\]:.*" "" $summary }}
                            {{ $summary | markdownify }}
                            <p><a class="read-more" href="{{ .Permalink }}">
                                {{ if templates.Exists "partials/microhook-read-more-text.html" }}
                                {{ partial "microhook-read-more-text.html" . }}
                                {{ else }}
                                Read More →
                                {{ end }}
                            </a></p>
                        </div>
                    {{ else if .Params.custom_summary }}
                    <div class="p-summary">
                        <p>{{ .Summary | safeHTML }}<p>
                    </div>
                    {{ else }}
                        <div class="e-content">
                            {{ .Content }}
                        </div>
                    {{ end }}
            {{ else }}
                <div class="e-content">
                    {{ .Content }}
                </div>
            {{ end }}
            {{ if templates.Exists "partials/microhook-below-post-in-list.html" }}
            {{ partial "microhook-below-post-in-list.html" . }}
            {{ end }}
        </div>
        {{ end }}
    </div>
</div>
{{ if templates.Exists "partials/microhook-after-post-list.html" }}
{{ partial "microhook-after-post-list.html" . }}
{{ end }}
{{ if templates.Exists "partials/microhook-pagination.html" }}
{{ partial "microhook-pagination.html" . }}
{{ else }}
<div class="post-nav">
    {{ if $paginator.HasPrev }}
    <span class="prev">
        <a href="{{ $paginator.Prev.URL }}" title="Previous Page"><span class="arrow">← Newer Posts</span></a>
    </span>
    {{ end }}
    {{ if $paginator.HasNext }}
    <span class="next">
        <a href="{{ $paginator.Next.URL }}"><span class="arrow">Older Posts →</span></a>
    </span>
    {{ end }}
</div>
{{ end }}
{{ end }}
{{ end }}
```

### layouts/_default/list.archivehtml.html

Archive page with category list and full post listing.

```html
{{ define "main" }}
<div class="archive">
	<h2 class="p-name">Archive</h2>
	{{ if templates.Exists "partials/microhook-archive-lead.html" }}
	{{ partial "microhook-archive-lead.html" . }}
	{{ end }}
	{{ $list := ($.Site.GetPage "taxonomyTerm" "categories").Pages }}
	{{ if gt (len $list) 0 }}
	<div class="archive-categories">
		<h3>Categories</h3>
		<ul>
			{{ range $list }}
			<li><a href="{{ .Permalink }}">{{ .Title }}</a></li>
			{{ end }}
		</ul>
	</div>
	{{ end }}
	<div class="full-archives h-feed">
		<h3>Full Post List</h3>
		{{ $list := (where .Site.Pages "Type" "post") }}
		{{ range $list }}

		<p class="h-entry">
			<a href="{{ .Permalink }}" class="u-url"><span class="dt-published" datetime="{{ .Date.Format "2006-01-02T15:04:05-0700" }}">{{ .Date.Format "Jan 2, 2006" }}</span></a>:
			{{ if .Title }}
			<span class="p-name"><b>{{ .Title }}</b></span>
			{{ end }}
			<span class="p-summary">{{ .Summary | truncate 150 }}</span>
		</p>

		{{ end }}
	</div>

</div>
{{ end }}
```

### Other Templates

For additional templates (post/single.html, section/replies.html, partials), see the [layouts directory on GitHub](https://github.com/MattSLangford/Tiny-Theme-for-Micro.blog/tree/main/layouts).

---

## Microhooks Available in Tiny

Microhooks are optional partials that the Tiny theme checks for. You can override these to customize specific parts of the page without replacing entire templates.

Key microhooks in base theme:
- `microhook-below-wrapper.html` - Content below main wrapper
- `microhook-before-closing-body.html` - Before closing body tag
- `microhook-before-archive-list.html` - Before archive list
- `microhook-post-list-byline.html` - Custom post date/time display
- `microhook-below-post.html` - Content below each post
- `microhook-after-pagination.html` - After pagination controls

See code-guide.md for your custom microhook implementations.

---

## Template Overrides in 907.life Plugin

These templates are overridden in the 907.life plugin:

- `layouts/index.html` - Custom homepage excluding "also" category
- `layouts/_default/list.archivehtml.html` - Custom archive with category grouping
- `layouts/reviews/list.html` - Filtered review lists
- `layouts/reviews/section.html` - Reviews section page
- `layouts/guides/list.html` - Filtered guide lists
- `layouts/guides/section.html` - Guides section page
- `layouts/also/list.html` - "Also" category list (15 most recent)
- `layouts/partials/custom_footer.html` - Empty (disables default footer)
- `layouts/partials/microhook-navigation.html` - Custom navigation menu
- `layouts/partials/microhook-title.html` - Custom site title

---

## CSS Override Strategy

Your `static/custom.css` loads after Tiny's `main.css`, so you can:

1. **Redefine CSS variables** - Override color scheme, fonts
2. **Add new selectors** - Style elements not in base theme
3. **Override existing rules** - More specific selectors take precedence
4. **Extend base styles** - Build on top of Tiny's foundation

**Key areas you override**:
- CSS variables (colors, fonts)
- Typography hierarchy (heading sizes, weights)
- Navigation styling
- Archive page layout
- Post list formatting

See `static/custom.css` for your complete overrides.

---

**Version**: 1.0
**Last Updated**: 2025-10-25
**Base Theme Version**: Current as of October 2025
**Refer to**: code-guide.md for your custom implementations
