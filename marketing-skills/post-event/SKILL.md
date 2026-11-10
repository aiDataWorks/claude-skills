---
name: post-event
description: Add an event or webinar to the aiDataWorks website - a page under events/ plus a card on webinars.html - or move a finished event to Past events. Use when asked to announce a conference appearance, webinar, meetup, or booth, or to update the events page.
---

# Event

Each event gets its own page and a card on `webinars.html` (the Events page),
which has two lists: **Upcoming** and **Past events**.

Read `marketing-skills/README.md` first for the rules that apply to all content.

## 1. Gather before writing

- **Event name, type** (conference, webinar, meetup), **dates**, **city or "Online"**, and time zone for webinars.
- **Official event page or registration link.**
- **Our role**: attending, booth (number?), speaking (session title, time, room?), hosting.
- **Who's going** from aiDataWorks: names and roles as they should appear.
- **What we'll talk about** there.
- Optional: an event logo or banner (check we're allowed to use it).

## 2. Create the page

1. Pick a slug with the year: `dreamforce-2027`, `idmc-migration-webinar-2027-03`.
2. Copy `templates/event-template.html` to `events/<slug>/index.html`.
3. Fill in every `[BRACKET]`. Delete the registration button if there's no link.
4. Images go in `assets/events/`.

## 3. Add it to the listing

In `webinars.html`, copy the card format from Past events into the
**Upcoming** grid (soonest event first). Link to `events/<slug>/index.html`.
If Upcoming was empty, delete its `<section class="post-empty">` "No events on the calendar" note.

## 4. After the event

- Move its card from **Upcoming** to the top of **Past events**, and change future-tense wording on the card to past tense.
- Update the event page's wording to past tense ("We were at..."), or add a short recap.
- If Upcoming is now empty, put the "No events on the calendar" note back:

```html
<section class="post-empty">
  <p class="page-section-body">No events on the calendar right now. Subscribe to our newsletter from the <a href="index.html#insights">homepage</a> and we'll let you know when the next one is scheduled.</p>
</section>
```

Older event pages may sit at the site root (e.g. `dreamforce-2026.html`). Leave them where they are - their links are already shared.

## 5. Writing rules

- Lead with when and where. People skim event pages for logistics.
- Only list people who have confirmed they're going.
- Don't use the event organizer's logo or name in a way that implies sponsorship we don't have.
- Webinars: give the time with time zone ("11:00 AM CT").

## 6. Check and publish

- [ ] Dates, city and links double-checked against the official event page
- [ ] No `[BRACKETS]` left; canonical URL matches the folder name
- [ ] Card in the right list on `webinars.html`
- [ ] `python scripts/check_site.py` shows 0 errors
- [ ] Open a pull request; merge when the check is green
- [ ] Calendar reminder to move the card to Past events after the event
