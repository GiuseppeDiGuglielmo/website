# Roadmap

Planned work for [gdg.engineer](https://gdg.engineer), ordered by how much new
information each stage makes public. `plan.md` is the underlying content spec;
section references below point into it.

`main` is deliberately minimal and is what deploys. Content is staged on `dev`
first and promoted deliberately, so each stage below is an explicit decision
rather than an automatic next step.

## Done

Technical correctness and reach, publishing no new professional claims:

- `Person.image` is omitted from JSON-LD when no portrait is set, instead of
  resolving to the site root.
- Verified ORCID (`0000-0002-5749-1432`) added to `sameAs` and `llms.txt`.
- Fermilab division corrected to Intelligent Microelectronics Systems Division
  in `profile.json` and `llms.txt`.
- Open Graph and Twitter Card tags plus a 1200x630 preview image, so shared
  links unfurl with a title, summary, and card.
- `favicon.ico` linked alongside the SVG icon.
- Dates added to the roles in "Previously".
- Custom 404 page.
- README replaced with real project documentation.

## Stage 2: make the homepage answer the success criterion

`plan.md` §26 asks that someone reading only the homepage can say who Giuseppe
is, what he is exceptionally good at, what he has built, how senior he is, and
why he fits a senior AI-hardware role. The page currently answers the first
two. It carries no quantitative claims, no expertise list in visible HTML, and
no evidence of technical leadership.

This stage keeps `main` at a single route and edits only `index.astro`,
`profile.json`, and `llms.txt`.

- **Positioning line under the `<h1>`** (§5), so technical framing is visible
  without reading a nine-sentence paragraph.
- **Lead with `bioShort`**, keeping the long bio below it.
- **Visible Expertise section** grouped as Hardware Architecture, AI Hardware,
  Design Methodology, and EDA Tools. `dev`'s `expertise.astro` already has this
  written. It answers §18's "Is he an ASIC engineer? Does he have HLS
  experience?", which today have no answer in visible HTML. They exist only in
  the JSON-LD `knowsAbout` array, which readers never see.
- **Selected Work: three or four quantified achievements** (§10). The largest
  gap, since the page currently has no numbers. `dev`'s `profile.json` already
  holds CV-sourced metrics with a `source` field on each claim, which is the
  verification checklist §10 asks for. Publish as short prose lines; no project
  routes needed.
- **Technical leadership**, using the AXESS co-lead role. Fermilab's newsroom
  describes the role directly, so it is employer-published and independently
  checkable. Link the article: an outbound `fnal.gov` citation also corroborates
  identity for search engines and AI crawlers.
- **Drive `knowsAbout` from `profile.json`** instead of the array hardcoded in
  `index.astro`, so visible text and structured data cannot drift (§16).
- **Update `llms.txt`** with the same quantified highlights.

Out of scope here: publication list, project detail pages, full employment
history, PDF CV.

## Stage 3: full content set

- **Promote the `dev` pages**: `about`, `experience`, `expertise`,
  `publications`, `projects/` and the four project pages, plus the nav
  masthead. This takes the sitemap from one URL to roughly ten, which is the
  real search unlock. One page currently competes for many distinct queries.
  Can be promoted page by page rather than all at once.
- **Fix two defects on `dev` before promoting**: its `llms.txt` advertises a
  downloadable PDF at `/cv/` that does not exist, and repeats the old division
  name.
- **Per-page structured data**: keep `Person` on the homepage only; add
  `CollectionPage` or `ItemList` for `/projects/`, `ScholarlyArticle` for
  publications, `BreadcrumbList` sitewide. `Layout.astro` already takes a
  `jsonLd` prop, so no interface change is needed.
- **Remaining `profile.json` TODOs**: `affiliations[0].url` and
  `sameAs.fermilabProfile`. No public Fermilab staff-directory page appears to
  exist, so consider linking the AXESS announcement instead.
- **More `sameAs` entries**: IEEE Xplore author `37393575000`, ACM Digital
  Library `81313483831`, ResearchGate. Each should be opened and checked
  against known employer and title first, the way the ORCID was. An incorrect
  identifier damages entity resolution rather than helping it.
- **Resolve the duplicate LinkedIn profile.** Search surfaces both
  `/in/giuseppe-diguglielmo/` (used on the site) and
  `/in/giuseppe-di-guglielmo-84743622/`. Two live profiles split the signal for
  recruiters and crawlers alike. Needs a decision on which is canonical.
- **PDF CV**, only after personal contact details are removed from the source
  document. §14 requires it stay supplementary; nothing may exist only there.
- **Search Console and Bing Webmaster** verification, and sitemap submission.
  There is currently no evidence the site is indexed.
- **Freshness signal**: `dateModified` in JSON-LD, or a "last updated" line.

## Deliberately not doing

- No analytics and no cookie banners. §3 rules both out.
- No blog unless it will actually be kept current.
- No keyword stuffing in `knowsAbout`. §19 warns against it and §15 forbids
  fabricating structured metadata for search.
- No Astro content collections or a schema layer for `profile.json` at this
  size. Flat JSON is easier to review line by line for factual accuracy, which
  matters more here than type safety.
- No statement that Giuseppe is looking for a role. §22 is explicit: seniority
  should read from the portfolio instead.

## Known discrepancy

Northwestern's public adjunct directory lists him under the generic heading
"Adjunct Faculty", while the site says Adjunct Associate Professor, a title
that page does use for other people. Worth being aware of; not worth changing.
