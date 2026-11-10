---
name: post-case-study
description: Write and publish a client case study on the aiDataWorks website - a page under case-studies/ plus an entry in the case-studies.html listing data. Use when asked to write up an engagement, turn a project summary into a case study, or add a case study to the site.
---

# Case study

A case study tells one engagement's story: the client's problem, what we
built, and what changed - with numbers. Each one is a page under
`case-studies/` and an entry in the data list on `case-studies.html`, which
builds the filterable cards.

Read `marketing-skills/README.md` first for the rules that apply to all content.

## 1. Gather before writing

Get these from the delivery team or the requester - never estimate or invent them:

- **Client**: name *only if* written approval exists; otherwise an anonymized description ("a Tier 1 regional bank"). Industry, region, company size.
- **Duration** and **services** delivered.
- **Technologies** used (product names as the vendor spells them).
- **The challenge**: 3-6 specific problems, each with its consequence.
- **The solution**: what we built, in 3-4 workstreams with 2-3 points each.
- **Results**: 3 metrics, each with a before and after. Plus 2-3 qualitative outcomes.
- **Quote** (optional): exact approved wording and an approved attribution (a role is fine: "VP of Risk &amp; Compliance, the client").
- **Architecture diagram** (optional): SVG preferred, PNG fine.

If there are no real metrics, say so and use concrete qualitative results ("Self-sufficient team", "Zero partner disruption") - several existing case studies do this.

## 2. Create the page

There is no fill-in-the-blanks template for case studies: **copy the existing
case study closest in shape** and replace its content. (`templates/case-study-template.html`
is an old wireframe that doesn't match the live pages - don't use it.)

1. Pick a slug: `<industry>-<what-was-done>`, e.g. `healthcare-hl7-realtime-integration`. Don't put the client's name in the slug unless it's approved.
2. Copy `case-studies/<closest-existing>/index.html` to `case-studies/<slug>/index.html`.
3. Replace, top to bottom:
   - `<head>`: `<title>`, meta description, canonical (`https://www.aidata.works/case-studies/<slug>/`), `og:` tags, and the JSON-LD block (headline, description, image, dates, URL).
   - Hero: breadcrumb, industry eyebrow, `<h1>` title, subtitle, one-line outcome statement.
   - Executive Summary, The Challenge (bullets as "problem &rarr; consequence"), Architecture diagram, Solution &amp; Approach (subsections), the "At a glance" sidebar, Outcomes (3 metric tiles + bullets), quote, Related Case Studies.
   - Keep the `data-cs-field="..."` attributes on the elements you edit.
4. Diagram files go in `assets/case-studies/`. If there's no diagram, remove the whole diagram `<section>` **and** the zoom overlay `<div class="case-study-zoom-overlay">` near the end of the page.
5. Leave the header, footer and `<script src="../../site.js"></script>` untouched.

## 3. Add it to the listing

In `case-studies.html`, find `<script type="application/json" id="case-studies-data">` and add an entry (the list sorts itself by `published`, newest first):

```json
  {
    "slug": "the-slug",
    "title": "Same title as the page's h1",
    "industry": "Healthcare",
    "service": "Data Integration & Interoperability",
    "technologies": ["Informatica IDMC", "Snowflake"],
    "challenge": "One sentence.",
    "solution": "One sentence.",
    "results": [
      {"metric": "3 days", "label": "Reporting cycle"},
      {"metric": "92%", "label": "Fewer duplicates"},
      {"metric": "2.5 hrs", "label": "Close window"}
    ],
    "thumbnail": "assets/industries/healthcare.png",
    "published": "YYYY-MM-DD",
    "detailUrl": "case-studies/the-slug/index.html"
  },
```

- Reuse an existing `industry` and `service` value exactly where one fits - they become the filter options, so a typo creates a duplicate filter.
- This is JSON: double quotes, a comma between entries, no comma after the last one. A mistake here blanks the whole listing page, so check it renders.
- `thumbnail` can be `null` (shows "Image coming soon") or one of `assets/industries/*.png`.

## 4. Writing rules

- Title: the outcome, not the technology. "Five disconnected systems, one governed lakehouse", not "Snowflake Implementation".
- Every metric needs a before and after, and must come from the client or delivery team.
- Challenge bullets: specific problem &rarr; business consequence.
- Write about the client's problem, not our process, in the first half.
- 600-1,000 words of body copy.

## 5. Check and publish

- [ ] Client name used only with written approval
- [ ] Every number traceable to the delivery team
- [ ] Canonical URL and JSON-LD URL match the folder name
- [ ] Entry added to `case-studies-data`, and `case-studies.html` still shows all cards in the browser
- [ ] `python scripts/check_site.py` shows 0 errors
- [ ] Open a pull request; merge when the check is green
