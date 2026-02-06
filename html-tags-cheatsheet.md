# HTML Cheatsheet: Elements + Attributes (Practical)

This is a **practical reference**: global attributes, then the most-used elements with their key attributes and short examples.

## 1) Global attributes (work on most elements)

### Core
- `id`: Unique identifier in the document.
- `class`: Space-separated tokens for CSS/JS hooks.
- `style`: Inline CSS (avoid at scale).
- `title`: Advisory text (tooltip).
- `hidden`: Hide visually + from accessibility tree.

### Language / direction
- `lang`: Language code like `en`, `en-US`.
- `dir`: `ltr` | `rtl` | `auto`.

### Focus / input behavior
- `tabindex`: `0` focusable, `-1` programmatic focus.
- `contenteditable`: `true` | `false`.
- `spellcheck`: `true` | `false`.
- `draggable`: `true` | `false`.
- `translate`: `yes` | `no`.

### Data + semantics
- `data-*`: Custom attributes readable via JS `element.dataset`.
- `role`: ARIA role override (use only when needed).
- `aria-*`: Accessible name/description/state; prefer native elements first.

### Common ARIA attributes (quick reference)
- `aria-label`: Provide an accessible name.
- `aria-labelledby`: Reference another element’s `id` as the label.
- `aria-describedby`: Reference element(s) that describe it.
- `aria-hidden="true"`: Hide from assistive tech (be careful).

---

## 2) Document & metadata

### `<!doctype html>`
- Standards mode.

### `<html>`
- Common: `lang`.

### `<meta>`
- Charset: `<meta charset="utf-8">`
- Viewport: `<meta name="viewport" content="width=device-width, initial-scale=1">`
- Description: `<meta name="description" content="...">`

### `<link>`
- CSS: `<link rel="stylesheet" href="styles.css">`
- Preconnect: `<link rel="preconnect" href="https://example.com">`
- Preload: `<link rel="preload" as="font" href="font.woff2" crossorigin>`

### `<script>`
- External: `<script src="app.js" defer></script>`
- Module: `<script type="module" src="app.js"></script>`
- Tips: use `defer` for most classic scripts; `async` only for independent scripts.

---

## 3) Sectioning & layout

### `<main>`
- Usually **one per page**; main content.

### `<section>` / `<article>` / `<nav>` / `<aside>`
- Use for semantics; typically include a heading.

### `<header>` / `<footer>`
- Can appear per-page or per-section.

### `<h1>`…`<h6>`
- Keep a sensible outline; don’t skip levels without reason.

---

## 4) Text & links

### `<a>`
- Key: `href`, `target`, `rel`, `download`, `hreflang`.
- New tab safely:
  - `<a href="..." target="_blank" rel="noopener noreferrer">...</a>`

### Emphasis
- `<strong>` importance, `<em>` stress emphasis.

### `<code>` / `<pre>`
- `<code>` inline code; `<pre>` preserves whitespace.

### `<br>` and `<wbr>` (void)
- `<br>` line break; `<wbr>` optional break point.

---

## 5) Images & responsive images

### `<img>` (void)
- Key: `src`, `alt`, `width`, `height`, `loading`, `decoding`, `srcset`, `sizes`.
- Accessible image:
  - `<img src="cat.jpg" alt="Gray cat sleeping" width="640" height="480" loading="lazy">`
- Decorative image:
  - `<img src="divider.svg" alt="" aria-hidden="true">`

### `<picture>` + `<source>` (void)
- Art direction:
  - `<picture>`
    - `<source media="(min-width: 768px)" srcset="hero-desktop.jpg">`
    - `<img src="hero-mobile.jpg" alt="...">`
    - `</picture>`

---

## 6) Embedded content

### `<iframe>`
- Key: `src`, `title`, `loading`, `referrerpolicy`, `allow`, `sandbox`.
- Safer baseline:
  - `<iframe src="..." title="Map" loading="lazy" sandbox></iframe>`

### `<video>` / `<audio>`
- Key: `controls`, `autoplay`, `muted`, `loop`, `preload`, (`poster` for video).
- Captions:
  - `<track kind="subtitles" src="subs.vtt" srclang="en" label="English" default>`

---

## 7) Lists

### `<ol>`
- Key: `start`, `reversed`, `type`.

### `<li>`
- In ordered lists: `value` can set explicit numbering.

---

## 8) Tables

Core elements:
- `<table>`, `<caption>`, `<thead>`, `<tbody>`, `<tfoot>`, `<tr>`, `<th>`, `<td>`

### `<th>`
- Key: `scope` (`col`, `row`, `colgroup`, `rowgroup`), `colspan`, `rowspan`.

Accessibility tips:
- Prefer `<caption>` for a table title.
- Use `<th scope="col">` / `<th scope="row">` for clear headers.

---

## 9) Forms (common attributes)

### `<form>`
- Key: `action`, `method`, `enctype`, `autocomplete`, `novalidate`.
- File upload: `enctype="multipart/form-data"`

### `<label>`
- Pair with a control via `for="..."` + matching `id`.

### `<input>` (void)
Common attributes:
- Identity: `name`, `value`
- UX: `placeholder`, `autocomplete`, `inputmode`
- State: `required`, `disabled`, `readonly`
- Validation: `min`, `max`, `step`, `minlength`, `maxlength`, `pattern`

Common `type` values:
- Text: `text`, `email`, `password`, `search`, `tel`, `url`
- Numbers/dates: `number`, `range`, `date`, `time`, `datetime-local`, `month`, `week`
- Picks: `checkbox`, `radio`, `color`, `file`
- Buttons: `submit`, `reset`, `button`, `image`
- Other: `hidden`

### `<button>`
- Key: `type` (`button` | `submit` | `reset`), `disabled`.

### `<select>` / `<option>` / `<optgroup>`
- `<select>` key: `name`, `multiple`, `size`, `required`, `disabled`.
- `<option>` key: `value`, `selected`, `disabled`.

### `<textarea>`
- Key: `name`, `rows`, `cols`, `minlength`, `maxlength`, `placeholder`, `required`.

### `<datalist>`
- Use with `<input list="someId">`.

---

## 10) Interactive / components

### `<details>` / `<summary>`
- `<details open>` starts expanded.

### `<dialog>`
- Controlled via JS (`showModal()`, `close()`).

---

## 11) Void elements (no closing tag)
- `area`, `base`, `br`, `col`, `embed`, `hr`, `img`, `input`, `link`, `meta`, `param`, `source`, `track`, `wbr`

---

## 12) Obsolete/deprecated elements (avoid)
- `acronym`, `applet`, `basefont`, `bgsound`, `big`, `blink`, `center`, `dir`, `font`, `frame`, `frameset`, `isindex`, `keygen`, `marquee`, `menuitem`, `nobr`, `noembed`, `noframes`, `plaintext`, `rb`, `rtc`, `spacer`, `strike`, `tt`, `xmp`
