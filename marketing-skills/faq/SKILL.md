---
name: faq
description: Add, edit, or reorganize questions on the aiDataWorks FAQ page (faq.html). Use when asked to add an FAQ, answer a common customer question on the site, or update the FAQ section.
---

# FAQ

All questions live on one page, `faq.html`, grouped by topic. Each question is
a native `<details>` element, so it opens and closes without any JavaScript.

Read `marketing-skills/README.md` first for the rules that apply to all content.

## 1. Gather before writing

- **The question**, phrased the way a prospect would actually ask it.
- **The answer**, from the requester or an existing page. Don't make up policies, timelines, prices or guarantees.
- **Which topic group** it belongs in (see the `<h2 class="faq-page-group-heading">` headings in `faq.html`), or a new group name.

## 2. Add the question

Copy one `<details>` block inside the right group in `faq.html`:

```html
    <details class="faq-page-item">
      <summary>How long does a typical migration take?</summary>
      <div class="faq-page-answer"><p>Answer in one to three short paragraphs.</p></div>
    </details>
```

To add a new topic group, copy a whole `<section class="faq-page-group">` block and give it a unique `id` and `aria-labelledby` pair:

```html
  <section class="faq-page-group" aria-labelledby="faq-pricing">
    <h2 class="faq-page-group-heading" id="faq-pricing">Pricing &amp; engagement</h2>
    ...questions...
  </section>
```

## 3. Writing rules

- The question is the reader's words, ending in "?". Under ~12 words.
- The first sentence of the answer answers it directly ("Yes &mdash; ...", "Most take 8&ndash;16 weeks ..."). Detail after.
- 40-120 words per answer. Longer means it should be a blog post; link to it instead.
- Link to the page that goes deeper (`services.html#...`, a case study, a blog post).
- Keep groups to 3-8 questions; put the most-asked first.

## 4. The homepage FAQ

`index.html` has its own short FAQ section (`id="faq"`) showing a selection of
questions. If you change the wording of a question that also appears there,
update both so they match.

## 5. Check and publish

- [ ] Each question is in its own `<details class="faq-page-item">` block
- [ ] New group `id`s are unique on the page
- [ ] Links in answers work
- [ ] `python scripts/check_site.py` shows 0 errors
- [ ] Open a pull request; merge when the check is green
