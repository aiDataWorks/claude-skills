---
name: news-release
description: Publish a press release or company announcement in the aiDataWorks Newsroom - a page under news/ plus a card on newsroom.html. Use when asked to post a press release, partnership announcement, certification, award, or other company news.
---

# News release

Each announcement gets its own page under `news/` and a card on `newsroom.html`.

Read `marketing-skills/README.md` first for the rules that apply to all content.

## 1. Gather before writing

- **The approved release text.** Press releases - especially joint ones with a partner - are usually approved word for word by both companies. **Publish the approved text exactly; don't edit, shorten or "improve" it.** If there's no approved text yet, you can draft one, but mark it as a draft for approval.
- **Headline, subheadline, release date, and dateline city.**
- **Quotes**: exact wording and the speaker's approved name and title.
- **Boilerplates**: the "About" paragraph for each company. Ours is in `templates/news-template.html`; a partner supplies theirs.
- **Media contacts** for each company.
- Whether it's a **Press Release** (formal, distributed) or **Company News** (a short update, e.g. a new certification).

## 2. Create the page

1. Pick a slug describing the news: `fortra-partnership`, `informatica-platinum-renewal-2027`.
2. Copy `templates/news-template.html` to `news/<slug>/index.html`.
3. Fill in every `[BRACKET]`. For a partner release, add their "About" section after ours, plus their media contact and any trademark notice they require (as `<p class="post-fineprint">`).
4. Short company news can drop the quote and the boilerplate.

## 3. Add it to the listing

In `newsroom.html`, copy an existing `<article class="post-card">` block, paste
it **at the top** of the grid, and update the link (`news/<slug>/index.html`),
label, headline, summary, and date.

Give the card an `id` matching the slug (`id="fortra-partnership"`) so links
like `newsroom.html#fortra-partnership` land on it.

## 4. Writing rules (when drafting, not when publishing approved text)

- Headline: who did what. "Fortra and aiDataWorks Enter into a 360&deg; Partnership", not "Exciting News".
- First paragraph: who, what, when, where, why - complete on its own.
- One or two quotes, each from a named person with their title, saying something the body doesn't.
- Use the existing aiDataWorks boilerplate unchanged.
- No claims about partner products beyond what the partner has approved.

## 5. Check and publish

- [ ] Text matches the approved version exactly (for press releases)
- [ ] Names, titles and partner product names spelled as the partner spells them
- [ ] No `[BRACKETS]` left; canonical URL matches the folder name
- [ ] Card added at the top of `newsroom.html`
- [ ] Publishing date coordinated with the partner (embargo?)
- [ ] `python scripts/check_site.py` shows 0 errors
- [ ] Open a pull request; merge when the check is green
