# Marketing skills

Instructions for creating each kind of content on www.aidata.works. Each
folder holds one `SKILL.md`, written so a person or an AI assistant (such as
Claude) can follow it start to finish.

| Skill | Creates | Lives in | Listed on |
|---|---|---|---|
| [blog-post](blog-post/SKILL.md) | Blog article | `blog/<slug>/index.html` | `blog.html` |
| [faq](faq/SKILL.md) | Question & answer | `faq.html` | `faq.html` |
| [whitepaper](whitepaper/SKILL.md) | Whitepaper landing page + PDF | `whitepapers/<slug>/index.html` | `whitepapers.html` |
| [case-study](case-study/SKILL.md) | Client case study | `case-studies/<slug>/index.html` | `case-studies.html` |
| [event](event/SKILL.md) | Event or webinar page | `events/<slug>/index.html` | `webinars.html` |
| [news-release](news-release/SKILL.md) | Press release / company news | `news/<slug>/index.html` | `newsroom.html` |

## How publishing works

1. Make the change on a branch and open a pull request.
2. The **Build and check site** GitHub check fills in the shared site header,
   footer and sitemap, and fails with a plain-English message if something is
   wrong (leftover `[PLACEHOLDER]` text, a page missing from its listing, a
   broken link or image, a folder name typo...).
3. Merge once the check is green. `main` deploys to www.aidata.works within
   about a minute.

To run the same check on your own machine: `python scripts/check_site.py`.
To preview locally: `python3 -m http.server 4173`, then open
http://localhost:4173/. (Pages copied from a template show no header/footer
locally until you run `python scripts/build_nav.py` or the check runs on the PR.)

## Rules for every kind of content

- **Never invent facts.** Client names, quotes, metrics, dates, speakers,
  partner claims and certifications must come from the person requesting the
  content or an existing page. If something is missing, ask - don't fill it
  with something plausible.
- **Client names need approval.** Unless the requester confirms written
  approval, describe clients by industry and size ("a Tier 1 regional bank").
- **Quotes need approval** from the person quoted, word for word.
- Write "aiDataWorks" exactly like that.
- Plain, specific language: what happened, what it changed, for whom. No
  "revolutionary", "cutting-edge", "seamless", "unlock the power of".
- Slugs (folder names) are lowercase words joined by hyphens, and become the
  URL. Don't rename one after it's published - links to it will break.
- Images go in `assets/<section>/`, under 500 KB where possible, always with
  `alt` text describing what the image shows.
- Write special characters as HTML entities, like the rest of the site:
  `&mdash;` (—), `&rsquo;` (’), `&ldquo;`/`&rdquo;` (“ ”), `&amp;` (&).
