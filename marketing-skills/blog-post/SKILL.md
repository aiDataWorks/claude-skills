---
name: blog-post
description: Write and publish a blog post on the aiDataWorks website. Use when asked to write, draft, add, or publish a blog post or article for blog.html, or to turn notes, a talk, or an engagement learning into a blog post.
---

# Blog post

A blog post is a practitioner's field note: one problem, what we've learned
about it, and what the reader should do. It is not a sales page and not a
case study (no single client story - that's the case-study skill).

Read `marketing-skills/README.md` first for the rules that apply to all content.

## 1. Gather before writing

Ask the requester for anything missing:

- **Topic and reader** - who is this for (role, situation) and what will they be able to do or decide after reading?
- **Source material** - notes, a recording, an engagement debrief, an outline. Claims must come from here.
- **Author** - name and role as they should appear. Use "aiDataWorks Team" only if the requester says so.
- **Category** - reuse one already on `blog.html` if it fits (e.g. "Data Modernization", "Data Governance", "AI &amp; Agentic", "Integration").
- **Publish date.**
- **Images** (optional) - files plus what each one shows.

## 2. Create the page

1. Pick a slug: short, lowercase, hyphenated, describing the topic (`powercenter-to-idmc-what-breaks`).
2. Copy `templates/blog-post-template.html` to `blog/<slug>/index.html`.
3. Fill in every `[BRACKET]` - the `<head>` (title, description, canonical, og tags), the hero, and the article. Delete template sections you don't use (figure, quote, callout).
4. Images go in `assets/blog/`; reference them from the post as `../../assets/blog/<file>`.

## 3. Add it to the listing

In `blog.html`, copy an existing `<article class="post-card">` block, paste it **at the top** of the post grid, and update the link (`blog/<slug>/index.html`), category, title, summary and date.

## 4. Writing rules

- **Title**: specific and in sentence case. Say what the reader gets: "What actually breaks in a PowerCenter-to-IDMC migration", not "Thoughts on Migration".
- **Summary** (meta description, hero lede, card text - same sentence in all three): 1-2 sentences, under 160 characters.
- **Length**: 700-1,500 words.
- **Opening paragraph**: the problem, and who this is for. No throat-clearing.
- Use `<h2>` section headings a skimmer can follow on their own; `<h3>` for sub-points.
- Paragraphs of 2-4 sentences. Bulleted lists for parallel items, numbered lists for ordered steps.
- An optional `post-summary` "Key takeaways" box near the top: three bullets, each a conclusion.
- Link to relevant case studies (`../../case-studies/<slug>/index.html`) or service pages (`../../services.html#...`) where they back up a point.
- Close with a concrete next step.
- No invented statistics, client names, or quotes.

## 5. Check and publish

- [ ] No `[BRACKETS]` left
- [ ] Canonical URL is `https://www.aidata.works/blog/<slug>/` and matches the folder name
- [ ] Title, description and card all agree
- [ ] Card added at the top of `blog.html`
- [ ] Every image has `alt` text and exists in `assets/blog/`
- [ ] `python scripts/check_site.py` shows 0 errors
- [ ] Open a pull request; merge when the check is green
