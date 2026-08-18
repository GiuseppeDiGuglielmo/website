# gdg.engineer — Recruiter & AI-Agent Optimized Personal Website

## Project Goal

Build a professional personal website for **Giuseppe Di Guglielmo** at **gdg.engineer**.

The primary objective is to make Giuseppe's professional profile highly discoverable and understandable by:

1. Human technical recruiters and hiring managers
2. AI recruiting agents and automated candidate-search systems
3. Search engines
4. LLM-based search and research systems
5. Engineers and technical collaborators

This is **not primarily an academic homepage**.

The website should position Giuseppe as a senior technical leader and hands-on engineer working at the intersection of:

- AI hardware
- ASIC design
- FPGA architecture
- High-Level Synthesis (HLS)
- ML-to-silicon systems
- Computer architecture
- Ultra-low-latency computing
- Scientific instrumentation
- Advanced microelectronics

The desired impression is closer to a **Principal/Staff Engineer technical portfolio** than a traditional university faculty webpage.

---

# 1. Primary Design Principle

The site must be simultaneously optimized for:

### Humans

A recruiter should understand within approximately 15–20 seconds:

- Who Giuseppe is
- His current seniority
- His main technical areas
- What he has built
- The scale and impact of his work
- What distinguishes him from a conventional FPGA, ASIC, or ML engineer

### Machines

An automated system should be able to extract the same information directly from the HTML without:

- executing substantial JavaScript
- interpreting visual layouts
- downloading a PDF CV
- inferring expertise from publication titles
- navigating complicated menus

Important professional information should therefore exist as **plain semantic HTML text**.

---

# 2. Technology and Hosting

Domain:

`https://gdg.engineer`

Preferred hosting:

**GitHub Pages**

Preferred implementation:

### Option A — Preferred

Lightweight static site using **Astro** with primarily server/static-rendered HTML.

### Option B

Hand-written HTML/CSS with minimal JavaScript.

Avoid unnecessarily heavy client-side frameworks.

The finished pages should contain the meaningful content directly in the generated HTML.

---

# 3. Performance and Crawlability Requirements

The site should:

- be fully statically generated
- work without JavaScript for core content
- use semantic HTML
- have descriptive page titles
- have useful `<meta name="description">` metadata
- use canonical URLs
- have descriptive internal links
- generate `sitemap.xml`
- provide `robots.txt`
- provide `llms.txt`
- allow normal search-engine and AI crawling
- avoid login walls
- avoid cookie banners unless actually necessary
- avoid content hidden behind interactive UI
- avoid requiring PDF parsing to understand the candidate
- load quickly
- work well on mobile
- meet basic accessibility standards

Example `robots.txt`:

```text
User-agent: *
Allow: /

Sitemap: https://gdg.engineer/sitemap.xml
```

Also provide `llms.txt` at the site root — a plain-text summary of who the
site is about and where the key pages are, aimed at LLM-based crawlers and
research agents that prefer a concise, non-HTML entry point over parsing the
full site.

Do not deliberately block major search engines or legitimate AI/search crawlers unless there is a specific reason to do so.

---

# 4. Information Architecture

Suggested structure:

```text
/
├── about/
├── experience/
├── expertise/
├── projects/
│   ├── smart-detectors/
│   ├── quantum-control/
│   ├── hls4ml/
│   └── advanced-microelectronics/
├── publications/
├── talks/
└── cv/
```

The exact organization can change if a simpler structure improves usability.

Every major page should have a stable, descriptive URL.

---

# 5. Homepage

The homepage is the most important page.

The first screen should immediately establish identity and technical positioning.

Suggested content:

# Giuseppe Di Guglielmo

**Principal Engineer · AI Hardware · ASIC/FPGA · ML-to-Silicon**

> Building intelligent systems from algorithms to silicon.

Include prominent links to:

- Selected Work
- Experience
- CV / Resume
- GitHub
- Google Scholar
- LinkedIn
- ORCID, if appropriate

Do not make publications the dominant homepage element.

---

# 6. Professional Summary

Include an explicit machine-readable and human-readable description rather than expecting visitors to infer expertise.

A starting point:

> Giuseppe Di Guglielmo is a Principal Engineer specializing in AI hardware, ASIC and FPGA architecture, high-level synthesis, computer architecture, and ultra-low-latency computing systems. His work focuses on translating algorithms and machine-learning models into efficient hardware implementations, from FPGA prototypes to custom silicon.

This text should eventually be refined for accuracy and recruiter positioning.

---

# 7. Expertise

Create a clearly marked **Technical Expertise** section.

Potential categories include:

## Hardware Architecture

- ASIC design
- FPGA design
- SoC architecture
- Computer architecture
- RTL design
- Digital design

## AI Hardware

- Machine-learning accelerators
- Quantized neural networks
- ML-to-silicon
- Edge AI
- Ultra-low-latency inference

## Hardware Design Methodology

- High-Level Synthesis
- RTL
- ASIC synthesis and physical implementation
- FPGA implementation
- Hardware/software co-design

## EDA / Tools

Include important tools and ecosystems where useful, without turning the page into a keyword dump.

Examples may include:

- hls4ml
- Siemens Catapult
- AMD/Xilinx Vitis HLS
- Vivado
- Cadence Genus
- RTL simulation and verification tools

The final list should accurately reflect actual expertise.

---

# 8. Selected Work

The site should emphasize **3–5 flagship engineering projects**.

Each project should be a small engineering case study.

Use approximately this structure:

```text
Project
Problem
My Role
Technical Approach
Results / Impact
Technologies
Related Publications / Code
```

Quantitative results should be included wherever meaningful.

Avoid describing projects primarily through funding-program terminology.

A recruiter should understand the engineering accomplishment without needing domain-specific scientific knowledge.

---

# 9. Candidate Flagship Projects

Initial candidates include:

## Smart Detectors / SmartPixels

Focus on:

- machine learning directly in detector readout
- ASIC implementation
- extreme latency/power constraints
- ML-to-silicon workflow
- quantitative hardware results

## hls4ml / ML-to-Silicon

Focus on:

- translating machine-learning models into FPGA/ASIC implementations
- High-Level Synthesis
- quantization
- latency/resource optimization
- contributions to the ecosystem

## Quantum Readout and Control

Focus on:

- FPGA/RFSoC implementation
- machine-learning inference
- ultra-low latency
- real-time quantum control/readout

## Advanced Microelectronics / SoC / eFPGA

Potential topics:

- embedded FPGA
- RISC-V
- heterogeneous SoCs
- 3D integration
- intelligent sensing
- advanced microelectronics

Only projects with a clear personal contribution should be presented as flagship work.

---

# 10. Quantitative Impact

Where possible, replace generic claims with measurable outcomes.

For example, instead of:

> Developed low-latency machine-learning hardware.

Prefer:

> Implemented machine-learning inference on FPGA with approximately 32 ns end-to-end latency.

Instead of:

> Designed efficient ASIC architectures.

Prefer statements containing relevant:

- latency
- area
- power
- throughput
- FPGA resource utilization
- clock frequency
- model size
- bandwidth reduction
- number of collaborators/users
- tapeouts
- deployments

All numbers must be verifiable before publication.

## Verification Checklist

Before any quantitative claim ships on the site, it must be traceable to a
source: a publication, a measured result, or explicit sign-off from
Giuseppe. Track this per flagship project (§9) as numbers are gathered, so
verification is a visible deliverable rather than an implicit constraint:

```text
[ ] Claim — Source
[ ] Claim — Source
```

Example:

```text
[x] ~32 ns end-to-end inference latency — arXiv:XXXX.XXXXX, Table 2
[ ] N tapeouts — pending confirmation
```

---

# 11. Experience

The experience section should emphasize increasing technical responsibility and leadership.

Current positioning should prominently identify Giuseppe as a:

**Principal Engineer**

Relevant professional affiliations can include:

- Fermilab
- Northwestern University
- previous research/engineering institutions

Avoid making the page resemble an academic CV chronology.

For each important position, emphasize:

- technical responsibility
- systems designed
- leadership
- architecture ownership
- collaborations
- measurable impact

---

# 12. Technical Leadership

Include a dedicated section explaining leadership beyond job titles.

Possible themes:

- technical direction of multidisciplinary engineering efforts
- mentoring engineers and students
- architecture decisions
- cross-institution collaborations
- ASIC/FPGA/AI project leadership
- bridging research algorithms and production-quality hardware
- interactions with EDA and semiconductor industry partners

The purpose is to establish suitability for senior individual-contributor and technical-leadership positions.

---

# 13. Publications

Publications are important evidence of technical depth but should not dominate the website.

Provide:

- selected publications
- link to complete Google Scholar profile
- optionally a complete publication page

Selected publications should preferably be grouped by technical theme rather than presented as one enormous chronological list.

Where possible, connect publications to corresponding project pages.

---

# 14. CV / Resume

Provide both:

### HTML professional profile

Important information must be crawlable directly from the website.

### Downloadable PDF

Provide a conventional CV/resume for human recruiters.

The PDF must supplement the website rather than contain information unavailable elsewhere.

---

# 15. Structured Data

Use Schema.org JSON-LD.

At minimum, represent the homepage as a `ProfilePage` whose `mainEntity` is a `Person`.

Example starting point:

```json
{
  "@context": "https://schema.org",
  "@type": "ProfilePage",
  "url": "https://gdg.engineer/",
  "mainEntity": {
    "@type": "Person",
    "name": "Giuseppe Di Guglielmo",
    "url": "https://gdg.engineer/",
    "jobTitle": "Principal Engineer",
    "knowsAbout": [
      "ASIC Design",
      "FPGA Design",
      "AI Hardware",
      "High-Level Synthesis",
      "Machine Learning Accelerators",
      "Computer Architecture",
      "Ultra-Low-Latency Computing"
    ]
  }
}
```

Expand this carefully with verified information.

Potential properties include:

- `affiliation`
- `worksFor`
- `alumniOf`
- `sameAs`
- `knowsAbout`

`sameAs` should connect authoritative profiles such as:

- GitHub
- LinkedIn
- Google Scholar
- ORCID
- Fermilab profile
- university profile

Do not fabricate structured metadata merely for SEO.

---

# 16. Canonical Data Source

The same facts — name, title, affiliations, `sameAs` links, and each flagship
project's metrics — need to appear consistently in at least three places:
homepage prose, the JSON-LD structured data (§15), and the downloadable PDF
CV (§14). Authoring these independently risks drift (e.g. a latency number
updated on the homepage but not in the CV).

Define one canonical data file as the single source of truth, e.g.:

```text
src/content/profile.json
```

or, if richer typing is useful, `src/data/profile.ts` using Astro content
collections.

It should hold:

- name, current title, short and long bio variants
- affiliations and `worksFor`/`alumniOf` entries
- `sameAs` links (GitHub, LinkedIn, Google Scholar, ORCID, Fermilab, etc.)
- per-project verified metrics (latency, resource utilization, tapeouts,
  etc.)

Homepage components, the JSON-LD block, and the CV generation step (or, at
minimum, the CV's manual authoring checklist) should all read from this file
rather than duplicating the facts inline.

---

# 17. Entity Resolution

An important objective is making it easy for automated systems to determine that different professional profiles correspond to the same person.

The site should consistently use:

**Giuseppe Di Guglielmo**

External professional profiles should be linked clearly.

The homepage should contain enough context to distinguish this person from others with similar names.

---

# 18. AI-Agent Friendly Content

Write important professional facts explicitly.

Bad:

> See my work below.

Better:

> I design ASIC and FPGA systems for ultra-low-latency machine-learning inference and real-time scientific instrumentation.

Bad:

> SmartPixels

Better:

> SmartPixels — Machine-learning accelerator architectures for intelligent particle-detector readout implemented in custom ASIC technology.

Pages should answer likely machine/recruiter questions directly:

- Who is Giuseppe Di Guglielmo?
- What does he specialize in?
- Is he an ASIC engineer?
- Is he an FPGA expert?
- Does he work on AI hardware?
- Does he have HLS experience?
- Has he designed custom silicon?
- Does he have technical leadership experience?
- What systems has he built?
- What measurable results has he achieved?
- What tools and technologies does he use?

---

# 19. SEO Metadata

Each page should have:

```html
<title>...</title>
<meta name="description" content="...">
<link rel="canonical" href="...">
```

Titles should be descriptive.

Examples:

```text
Giuseppe Di Guglielmo | Principal Engineer — AI Hardware, ASIC & FPGA

AI Hardware & ML-to-Silicon Projects | Giuseppe Di Guglielmo

ASIC & FPGA Expertise | Giuseppe Di Guglielmo
```

Avoid keyword stuffing.

---

# 20. Accessibility and Semantic HTML

Prefer semantic elements:

```html
<header>
<nav>
<main>
<article>
<section>
<h1>
<h2>
<ul>
<footer>
```

Use exactly one clear primary `<h1>` per page.

Use logical heading hierarchy.

Images must have meaningful `alt` text.

Links should have descriptive text rather than generic "click here."

---

# 21. Visual Design

The visual style should communicate:

- senior engineer
- technical authority
- clarity
- precision
- modern hardware/technology
- understated professionalism

Avoid:

- flashy animations
- excessive gradients
- skill percentage bars
- animated typing effects
- large hero illustrations
- generic stock photography
- excessive icons
- startup-style marketing language
- academic-template clutter

Favor:

- excellent typography
- generous whitespace
- concise technical diagrams
- real chip/board/system imagery when useful
- engineering figures
- simple project cards
- quantitative results

---

# 22. Recruiter Positioning

The site should naturally support consideration for positions such as:

- Principal Engineer
- Staff / Senior Staff Engineer
- AI Hardware Architect
- ASIC Architect
- FPGA Architect
- Hardware Accelerator Architect
- SoC Architect
- Technical Lead
- Advanced R&D / Microelectronics leadership

The website should **not** explicitly state that Giuseppe is looking for a job unless that decision is made separately.

Instead, the quality and organization of the portfolio should make the professional level obvious.

---

# 23. What Makes the Profile Distinctive

The website should communicate the intersection of:

```text
Machine Learning
       ↓
Algorithms / Quantization
       ↓
High-Level Synthesis
       ↓
RTL / Architecture
       ↓
FPGA
       ↓
ASIC / Silicon
       ↓
Real-Time Physical Systems
```

This end-to-end capability is more important than presenting Giuseppe simply as an FPGA engineer, ASIC engineer, ML researcher, or academic researcher.

---

# 24. Repository Structure

A possible Astro implementation:

```text
gdg.engineer/
├── public/
│   ├── robots.txt
│   ├── llms.txt
│   ├── images/
│   └── cv/
├── src/
│   ├── components/
│   ├── content/
│   │   ├── profile.json
│   │   └── projects/
│   ├── layouts/
│   └── pages/
│       ├── index.astro
│       ├── about.astro
│       ├── experience.astro
│       ├── expertise.astro
│       ├── projects/
│       ├── publications.astro
│       └── cv.astro
├── astro.config.mjs
└── package.json
```

Deploy automatically to GitHub Pages using GitHub Actions.

Custom domain:

```text
gdg.engineer
```

---

# 25. Initial Deliverable

The first implementation should prioritize a polished homepage rather than attempting to populate the entire career history.

Version 1 should contain:

1. Homepage
2. Professional summary
3. Technical expertise
4. 3–4 selected projects
5. Experience summary
6. Technical leadership
7. Selected publications
8. External professional profiles
9. CV link
10. JSON-LD structured data
11. sitemap
12. robots.txt
13. GitHub Pages deployment

After the basic site is live, individual project pages and deeper technical content can be added incrementally.

---

# 26. Success Criterion

A human recruiter or AI agent visiting only:

`https://gdg.engineer/`

should be able to accurately answer:

> **Who is Giuseppe Di Guglielmo, what is he exceptionally good at, what has he built, how senior is he, and why might he be relevant for a senior AI-hardware / ASIC / FPGA / computer-architecture role?**

without needing to open the PDF CV or infer those answers from publications.