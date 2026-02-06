# HTML Tags Cheatsheet (HTML Living Standard)

Notes:
- Most elements are **not** self-closing. Only **void elements** (listed below) have no end tag.
- Many elements are **obsolete** (deprecated) and should not be used in new pages.
- Use semantic elements (`<main>`, `<nav>`, `<article>`, `<section>`, etc.) to improve accessibility and SEO.

## Global Attributes (work on most elements)
- `id`: Unique identifier in the document (used by CSS/JS and `#hash` links).
- `class`: Space-separated CSS/JS hooks.
- `style`: Inline CSS (avoid for large styling; prefer stylesheets).
- `title`: Advisory text (often shown as a tooltip).
- `lang`: Language code, e.g. `en`, `en-US` (important for screen readers).
- `dir`: Text direction: `ltr`, `rtl`, `auto`.
- `hidden`: Hides element from rendering and accessibility tree.
- `tabindex`: Keyboard focus order (`0` = focusable; `-1` = programmatic focus).
- `contenteditable`: Makes content editable (`true`/`false`).
- `draggable`: Enables drag-and-drop (`true`/`false`).
- `spellcheck`: Spellchecking hint (`true`/`false`).
- `translate`: Translation hint (`yes`/`no`).
- `data-*`: Custom data attributes accessible via JS (`dataset`).

## ARIA (accessibility quick note)
- Prefer native semantics first (e.g., a real `<button>`).
- Common attributes: `aria-label`, `aria-labelledby`, `aria-describedby`, `aria-hidden`.
- Only add `role` when the element’s native role isn’t suitable.

## Document / Metadata
- `<!doctype html>`: Standards mode.
- `<html>`: Root element.
  - Useful: `lang`.
- `<head>`: Metadata container (not rendered).
- `<title>`: Browser tab title.
- `<base>`: Sets base URL for relative links.
  - Useful: `href`, `target`.
- `<link>`: External resource relationship.
  - Common: `rel="stylesheet"`, `href`, `media`, `as` (preload).
- `<meta>`: Metadata; charset, viewport, SEO.
  - Common: `charset="utf-8"`, `name="viewport" content="width=device-width, initial-scale=1"`, `name="description"`.
- `<style>`: Embedded CSS.
  - Useful: `media`.
- `<body>`: Rendered document content.

## Sectioning / Structure
- `<main>`: Main content (generally 1 per page).
- `<section>`: Thematic grouping; usually with a heading.
- `<nav>`: Major navigation block.
- `<article>`: Self-contained piece (post, comment, card).
- `<aside>`: Complementary content (sidebar, callout).
- `<header>`: Intro content for a page/section/article.
- `<footer>`: Footer content (copyright, related links).
- `<address>`: Contact info for nearest article or page.
- `<h1>`…`<h6>`: Headings; don’t skip levels unnecessarily.

## Grouping Content
- `<p>`: Paragraph.
- `<hr>` (void): Thematic break.
- `<pre>`: Preformatted text; preserves whitespace.
- `<blockquote>`: Quoted block.
  - Useful: `cite` (URL to source).
- `<ol>`: Ordered list.
  - Useful: `start`, `reversed`, `type`.
- `<ul>`: Unordered list.
- `<li>`: List item.
  - Useful (in `<ol>`): `value`.
- `<dl>`: Description list.
- `<dt>`: Term/name.
- `<dd>`: Description/value.
- `<figure>`: Self-contained content (image, code, diagram).
- `<figcaption>`: Caption for a figure.
- `<div>`: Generic block container (use semantic elements first).

## Text-Level Semantics
- `<a>`: Hyperlink/anchor.
  - Common: `href`, `target`, `rel` (`noopener noreferrer` for `target="_blank"`), `download`.
- `<em>`: Stress emphasis.
- `<strong>`: Strong importance.
- `<small>`: Side comments, fine print.
- `<s>`: No longer accurate/relevant text.
- `<cite>`: Title of a work.
- `<q>`: Inline quotation.
  - Useful: `cite`.
- `<dfn>`: Defining instance of a term.
- `<abbr>`: Abbreviation.
  - Useful: `title` for expansion.
- `<ruby>`: Ruby annotation container.
- `<rt>`: Ruby text (annotation).
- `<rp>`: Fallback parentheses for ruby.
- `<data>`: Machine-readable value.
  - Useful: `value`.
- `<time>`: Date/time.
  - Useful: `datetime` (ISO 8601).
- `<code>`: Code fragment.
- `<var>`: Variable.
- `<samp>`: Program output.
- `<kbd>`: User input.
- `<sub>` / `<sup>`: Subscript / superscript.
- `<i>`: Idiomatic text (thoughts, taxonomy).
- `<b>`: Stylistic offset (keywords) without importance.
- `<u>`: Unarticulated annotation (rare; often underlined).
- `<mark>`: Highlighted reference text.
- `<bdi>`: Isolates bidirectional text.
- `<bdo>`: Overrides text direction.
  - Useful: `dir`.
- `<span>`: Generic inline container.
- `<br>` (void): Line break (use sparingly).
- `<wbr>` (void): Optional word break opportunity.

## Edits
- `<ins>`
- `<del>`

## Embedded Content / Media
- `<img>` (void): Image.
  - Common: `src`, `alt` (required for accessibility), `width`, `height`, `loading="lazy"`.
- `<iframe>`: Embedded page.
  - Common: `src`, `title` (important), `loading`, `referrerpolicy`, `allow`, `sandbox`.
- `<embed>` (void): Generic embedded content.
  - Common: `src`, `type`.
- `<object>`: External resource (SVG, PDF, etc.).
  - Common: `data`, `type`.
- `<param>` (void): Parameter for `<object>`.
  - Common: `name`, `value`.
- `<video>`: Video player.
  - Common: `src`, `controls`, `autoplay` (often blocked), `muted`, `loop`, `poster`, `preload`.
- `<audio>`: Audio player.
  - Common: `src`, `controls`, `autoplay`, `muted`, `loop`, `preload`.
- `<source>` (void): Media source in `<picture>/<audio>/<video>`.
  - Common: `src`, `type`, `media`, `srcset`, `sizes`.
- `<track>` (void): Captions/subtitles for media.
  - Common: `kind`, `src`, `srclang`, `label`, `default`.
- `<map>`: Image map container.
  - Common: `name`.
- `<area>` (void): Clickable region in a map.
  - Common: `shape`, `coords`, `href`, `alt`.
- `<picture>`: Responsive images wrapper.

## Tabular Data
- `<table>`: Data table.
- `<caption>`: Table title/summary (first child of table).
- `<colgroup>`: Group columns for styling.
  - Useful: `span`.
- `<col>` (void): Column definition.
  - Useful: `span`.
- `<thead>` / `<tbody>` / `<tfoot>`: Table sections.
- `<tr>`: Row.
- `<th>`: Header cell.
  - Common: `scope` (`col`, `row`, `colgroup`, `rowgroup`), `colspan`, `rowspan`.
- `<td>`: Data cell.
  - Common: `colspan`, `rowspan`.

## Forms
- `<form>`: Form submission container.
  - Common: `action`, `method` (`get`/`post`), `enctype`, `autocomplete`, `novalidate`.
- `<label>`: Label for a control.
  - Use `for="id"` or wrap the input.
- `<input>` (void): Single-line control.
  - Common: `type`, `name`, `value`, `placeholder`, `required`, `disabled`, `readonly`, `min`, `max`, `step`, `minlength`, `maxlength`, `pattern`, `autocomplete`.
  - Frequent `type`s: `text`, `email`, `password`, `number`, `date`, `checkbox`, `radio`, `file`, `hidden`, `search`, `tel`, `url`, `range`, `color`, `submit`.
- `<button>`: Button.
  - Common: `type` (`button`, `submit`, `reset`), `disabled`.
- `<select>`: Dropdown.
  - Common: `name`, `multiple`, `size`, `required`, `disabled`.
- `<datalist>`: Autocomplete options for an `<input list="...">`.
  - Common: `id`.
- `<optgroup>`: Option group.
  - Common: `label`, `disabled`.
- `<option>`: Select option.
  - Common: `value`, `selected`, `disabled`.
- `<textarea>`: Multi-line input.
  - Common: `name`, `rows`, `cols`, `placeholder`, `minlength`, `maxlength`, `required`.
- `<output>`: Calculation result.
  - Common: `for` (space-separated ids), `name`.
- `<progress>`: Task progress.
  - Common: `value`, `max`.
- `<meter>`: Scalar measurement.
  - Common: `value`, `min`, `max`, `low`, `high`, `optimum`.
- `<fieldset>` / `<legend>`: Group controls with a caption.

## Interactive / UI
- `<details>`: Disclosure widget.
  - Useful: `open`.
- `<summary>`: Summary/label for `<details>` (first child).
- `<dialog>`: Modal/non-modal dialog.
  - Useful: `open` (JS usually controls), use `showModal()`.

## Scripting
- `<script>`: JavaScript.
  - Common: `src`, `type`, `defer`, `async`, `module` (`type="module"`).
- `<noscript>`: Fallback content when JS disabled.
- `<template>`: Inert DOM fragment used by JS.
- `<canvas>`: Bitmap drawing surface.
  - Common: `width`, `height`.

## Web Components
- `<slot>`

## Inline Frames / Resources (already above)
- `<iframe>`

## Obsolete/Deprecated (avoid)
- `<acronym>`
- `<applet>`
- `<basefont>`
- `<bgsound>`
- `<big>`
- `<blink>`
- `<center>`
- `<dir>`
- `<font>`
- `<frame>`
- `<frameset>`
- `<isindex>`
- `<keygen>`
- `<marquee>`
- `<menuitem>`
- `<nobr>`
- `<noembed>`
- `<noframes>`
- `<plaintext>`
- `<rb>`
- `<rtc>`
- `<spacer>`
- `<strike>`
- `<tt>`
- `<xmp>`

## Common Void Elements (no closing tag)
- `area`, `base`, `br`, `col`, `embed`, `hr`, `img`, `input`, `link`, `meta`, `param`, `source`, `track`, `wbr`

## Common attributes by use-case (quick reference)
- Links: `href`, `target`, `rel`, `download`, `hreflang`.
- Images: `src`, `alt`, `loading`, `srcset`, `sizes`, `width`, `height`.
- Media: `controls`, `autoplay`, `muted`, `loop`, `preload`, `poster`.
- Forms: `name`, `value`, `required`, `disabled`, `readonly`, `placeholder`, `min`, `max`, `pattern`.

## Attribute “Keyword” Lookups (what to type when you need X)

### Links (`<a>`)
- Link to a page/section: `href="..."` (use `#id` for same-page)
- Open in new tab: `target="_blank"` + `rel="noopener noreferrer"`
- Download a file: `download` (optionally `download="filename"`)
- Mark relationship: `rel="nofollow"`, `rel="external"`, `rel="help"` (varies by use)

### Images (`<img>`, `<picture>`, `<source>`)
- Image URL: `src="..."`
- Accessibility text: `alt="..."` (empty `alt=""` if decorative)
- Set size to prevent layout shift: `width=""` and `height=""`
- Lazy-load: `loading="lazy"`
- Responsive images: `srcset="..."` + `sizes="..."`
- Art direction: `<picture>` + `<source media="(min-width: ...)" srcset="...">`

### Video / Audio (`<video>`, `<audio>`, `<track>`)
- Show player controls: `controls`
- Autoplay (usually requires muted): `autoplay muted`
- Loop: `loop`
- Poster image (video): `poster="..."`
- Captions/subtitles: `<track kind="subtitles" srclang="en" label="English" src="...">`

### Iframes (`<iframe>`)
- URL: `src="..."`
- Accessible name: `title="..."`
- Restrict capabilities: `sandbox` (add exceptions like `allow-scripts` carefully)
- Allow features: `allow="fullscreen; autoplay"` (feature-policy style)

### Lists (`<ol>`, `<li>`)
- Start numbering at N: `<ol start="5">`
- Count down: `<ol reversed>`
- Force a specific number on an item: `<li value="10">`

### Tables (`<th>`, `<td>`)
- Make headers clear to screen readers: `<th scope="row">` / `<th scope="col">`
- Span cells: `rowspan="2"`, `colspan="3"`

### Forms (most used)

#### Form (`<form>`)
- Where to send: `action="/path"`
- How to send: `method="get"` or `method="post"`
- File upload: `enctype="multipart/form-data"`
- Turn off validation: `novalidate`

#### Input basics (`<input>`)
- Label it: `<label for="id">` + `<input id="id">`
- Server key name: `name="..."`
- Default value: `value="..."`
- Hint text: `placeholder="..."`
- Required field: `required`
- Disable: `disabled`
- Read-only: `readonly`
- Autofill hint: `autocomplete="email"`, `autocomplete="name"`, etc.

#### Input types (pick by task)
- Email keyboard/validation: `type="email"`
- Hidden value: `type="hidden"`
- Password field: `type="password"`
- Numeric field: `type="number"` + `min/max/step`
- Slider: `type="range"` + `min/max/step`
- Checkbox: `type="checkbox"` (`checked` for default)
- Radio group: `type="radio"` + same `name` for group (`checked` default)
- Date picker: `type="date"`
- File upload: `type="file"` + `accept="image/*"` + `multiple`

#### Validation attributes
- Text length: `minlength`, `maxlength`
- Number/date range: `min`, `max`, `step`
- Pattern match: `pattern="[A-Za-z]+"`

#### Textarea (`<textarea>`)
- Size: `rows`, `cols`

#### Select (`<select>`, `<option>`)
- Option value to submit: `<option value="...">`
- Default selected: `selected`
- Multi-select: `<select multiple size="5">`

#### Button (`<button>`)
- Make it submit: `type="submit"`
- Make it not submit: `type="button"`

### Script (`<script>`)
- External file: `src="app.js"`
- Don’t block parsing: `defer` (best for most non-module scripts)
- Load in parallel: `async` (for independent scripts)
- ES modules: `type="module"`

---
If you want, I can also generate this as an HTML page with anchors/examples.
