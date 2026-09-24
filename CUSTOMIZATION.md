# Editing SOLVIX Research Hub

Use a plain-text code editor such as VS Code. Make one change at a time, save and preview before committing. Content edited in JavaScript template strings is trusted site-author content: do not paste unreviewed scripts or embed confidential material.

## 1. Logo and background

Replace `assets/research-emblem.png` with your chosen emblem using the same filename. The supplied logo has a 3:2 aspect ratio; its original proportions and white background are preserved. Header size is controlled by `.emblem`; hero size by `.hero-emblem` in `style.css`. If using a different filename, update both references in `app.js` and the favicon in `index.html`.

Replace `assets/network.png` to change the scientific backdrop. `.hero-art` controls position and opacity; `.hero:after` controls the overlay. Keep sufficient contrast for the heading.

## 2. Mission, vision and introductory text

Search `app.js` for `Our mission`, `Our vision`, `From a question` or `Bring your questions`. Edit the corresponding text inside the HTML template. Keep opening and closing tags and backticks intact. The hero line break is `<br>`.

## 3. Services

Edit `window.SOLVIX_SERVICES` in `site-config.js`. Each row contains its displayed number, title and description:

```js
['07', 'Proposal development', 'Build a feasible proposal with clear objectives, methods and milestones.']
```

Add a comma between rows. Remove a complete row to remove a service. The responsive grid automatically accommodates more or fewer cards.

## 4. Research pathways and topic lists

Each `window.SOLVIX_PATHWAYS` row contains:

```js
['01', 'Research guidance', 'Short card description.', 'guidance',
 'Detailed section heading', 'Detailed section introduction.',
 ['First topic', 'Second topic', 'Third topic']]
```

The fourth field is the section ID. Keep IDs unique, simple and free of spaces. Changing `guidance`, `writing` or `methods` also requires updating corresponding `href="#..."` links in `app.js`. The pathway cards and detailed sections are generated together.

## 5. Contact and social links

In `window.SOLVIX_CONTACTS`, replace the empty value for each available channel:

```js
Email: 'mailto:YOUR-EMAIL@YOUR-DOMAIN',
LinkedIn: 'https://www.linkedin.com/company/YOUR-PAGE/',
WhatsApp: 'https://wa.me/COUNTRYCODEANDNUMBER'
```

These are placeholders: replace them with your actual details. Use full `https://` URLs, or `mailto:` for email. Empty values show a coming-soon dialog. Delete a channel's full entry if it should not appear. Do not publish a private phone number unless it is intended as a public contact channel.

## 6. Events, dates and registration

Add objects to `window.SOLVIX_EVENTS`:

```js
{
  date: '2026-11-12',
  title: 'Scientific writing workshop',
  type: 'Hands-on workshop',
  description: 'Write a clear abstract and receive structured feedback.',
  format: 'Online',
  details: '15:00–17:00 UTC · Speaker: confirmed name · Fee: confirmed amount',
  status: 'confirmed',
  example: false,
  registrationUrl: 'https://YOUR-CONFIRMED-REGISTRATION-LINK'
}
```

This is an editing example, not a real event. Use `status: 'planned'` while details are provisional, then `status: 'confirmed'` when final. Real planned events use `example: false`; fictional examples use `example: true`. Put timezone information in `details`; the calendar stores dates, not time-zone-converted meeting times. Keep `registrationUrl: ''` until available. Registration buttons appear only when `status: 'confirmed'`, `example: false` and a valid link are set.

Use ISO dates `YYYY-MM-DD`. Multiple events may share a date: select that date and click the individual event card. To remove every event use `window.SOLVIX_EVENTS = [];`; the calendar will show its empty state. To remove an event delete its entire object and maintain commas between remaining entries.

## 7. Colours and fonts

Change variables at the start of `style.css`:

```css
:root {
  --bg: #030d20;
  --panel: #09172c;
  --line: #ffffff18;
  --text: #eef5ff;
  --muted: #9baec9;
  --blue: #438aff;
  --cyan: #7bdcf7;
}
```

Some accents and gradients also use literal hex colours; search the stylesheet if changing the entire palette. The top `@import` loads DM Sans and Manrope from Google Fonts. Remove it and set `font-family: system-ui, sans-serif` in the relevant rules for a system-font design with no font request.

## 8. Spacing, layout and movement

- `.wrap`: maximum content width and side margins.
- `.section`: vertical spacing between sections.
- `.hero` and `.hero h1`: first-screen height and heading size.
- `.topic-grid`, `.service-grid`, `.detail-grid`: card and section columns.
- `.hero-art`: background styling.
- Final pointer-movement block in `app.js`: subtle mouse interaction; remove that block to disable it.
- `@media` rules: mobile and tablet layouts. Reduced-motion preferences already disable the pointer animation and transitions.

## 9. Navigation and new pages

The current Research Hub is intentionally one page with section anchors. Add `<a href="#new-section">Section name</a>` in the header and a matching `<section id="new-section">...</section>` for a new section.

For a separate page, create `about.html` at the root, link with `href="./about.html"` and reuse the relative CSS and asset paths. If adding pages inside subfolders, adjust relative paths with `../`. Do not reintroduce unrelated astronomy or natural-science hub pages unless that is a deliberate scope change.

## 10. Search appearance and accessibility

Edit `<title>` and `<meta name="description">` in `index.html`. Retain its viewport tag. Replace image alternative text if the emblem changes. Keep visible keyboard focus, labelled controls, heading order and readable contrast. Check the layout at 200% browser zoom.

## 11. Changes requiring additional development

A booking calendar synced with Google Calendar, mailing-list signup, accounts, persistent data, paid courses or payments require external integrations or a backend. Do not place API keys or passwords in any published JavaScript file. Choose those services when their requirements are known.
