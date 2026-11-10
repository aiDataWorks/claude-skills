---
name: whitepaper
description: Publish a whitepaper on the aiDataWorks website - a landing page plus the downloadable PDF, listed on whitepapers.html. Use when asked to add, publish, or write the landing page for a whitepaper, guide, playbook, or e-book.
---

# Whitepaper

A whitepaper is published as a **PDF** with a short **landing page** that
says what's inside and who it's for. The landing page is not the paper itself.

Read `marketing-skills/README.md` first for the rules that apply to all content.

## 1. Gather before writing

- **The final PDF.** Don't publish a landing page for a paper that isn't finished.
- **Title, topic, and page count.**
- **What's inside** - the 3-6 main sections or findings (take them from the paper's table of contents).
- **Who it's for** - roles and situations.
- **Publish date.**
- Optional: a short excerpt or key finding to quote, and a cover image.

## 2. Create the page

1. Pick a slug (`powercenter-idmc-migration-playbook`).
2. Put the PDF at `assets/whitepapers/<slug>.pdf`. Keep it under 10 MB.
3. Copy `templates/whitepaper-template.html` to `whitepapers/<slug>/index.html`.
4. Fill in every `[BRACKET]`. The download button already points at `../../assets/whitepapers/[slug].pdf` - replacing `[slug]` makes it point at your PDF.

## 3. Add it to the listing

In `whitepapers.html`:

- **First whitepaper only:** delete the `<section class="post-empty">` "Coming soon" block.
- Copy the example card from the comment at the top of the list into `<section class="post-grid" aria-label="Whitepapers">`, newest first, and update the link (`whitepapers/<slug>/index.html`), topic, title, summary, date and page count.

## 4. Writing rules

- **Title**: what the reader will be able to do: "The PowerCenter-to-IDMC migration playbook", not "Modernization Insights".
- **Summary**: 1-2 sentences, under 160 characters, same in the meta description, hero lede and card.
- **What's inside**: concrete items taken from the paper, not teasers.
- Everything on the landing page must be true of the PDF - no claims the paper doesn't make.
- No gated form: the PDF downloads directly (the site has no form backend).

## 5. Check and publish

- [ ] PDF exists at `assets/whitepapers/<slug>.pdf` (the check fails if the download link is broken)
- [ ] No `[BRACKETS]` left; canonical URL matches the folder name
- [ ] Card added to `whitepapers.html`; "Coming soon" block removed if this is the first one
- [ ] `python scripts/check_site.py` shows 0 errors
- [ ] Open a pull request; merge when the check is green
