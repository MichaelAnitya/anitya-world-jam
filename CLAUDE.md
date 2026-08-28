# Anitya World Jam site - working instructions

Read this before editing anything. It exists because several plausible-sounding sentences about
this product are false, and putting one on this page costs us credibility with the exact audience
we are recruiting.

## What this repo is

One hand-written file, `index.html`, about 770 lines. HTML, CSS and JavaScript all inline. No
build step, no framework, no CMS.

GitHub Pages serves it straight off the `main` branch. **Anything committed to `main` is live in
about two minutes with no review.** There is no staging.

Live: https://michaelanitya.github.io/anitya-world-jam/
Full spec, including everything still undecided: "Anitya World Jam - Full Spec v1" in Google Drive.

## Preview before you commit

Serve the folder and open it. Do not judge changes by reading the diff.

```
python -m http.server 8621
```

Then check http://localhost:8621, and check the browser console for errors. The countdowns run on
a one second interval, so a JavaScript error kills them silently and the page still looks fine.

## Safe to edit, and not

**Safe:** text inside `<p>`, `<h1>`, `<h2>`, `<h3>`, `<li>` and `<summary>` tags. Copy changes,
FAQ wording, list items.

**Careful:** anything inside `<style>` at the top or `<script>` at the bottom. The script drives
both countdowns and the hero flip on 1 September.

**Do not touch casually:** `data-target` attributes. They are ISO datetimes that drive the
countdown clocks, and they must agree with the human-readable dates elsewhere on the page.

## Dates live in many places

If a date changes, it changes in all of these or the page contradicts itself:

- the `<meta name="description">` tag
- the `<title>` tag if it mentions dates
- `data-target` on `#cd-hero`, `#cd-reg` and `#cd-main`
- the `const open = new Date(...)` line in the script, and the `startsWith` check next to it, and
  the target it flips to
- the timeline `.tl-date` blocks
- the Main Jam `.cat-meta` strip, "Closes" and "Announced"
- "Opens 1 September" appears on the status tag, the button, and the Side Quest line
- the footer `.note`

Search the whole file for the old date string and confirm zero results before committing.

## Current facts, as published

- Theme: **a world you can't stop playing**. Strapline: *Just one more minute.*
- Headline: **Create a world. Make them stay.**
- Four weeks. Opens Tuesday 1 September 2026. Closes Tuesday 29 September 2026, 23:59 UTC.
  Winners announced 6 October 2026.
- Prize pool 2,000 USD. Main Jam 1,800 across five places: 700 / 500 / 300 / 200 / 100.
  Side Quests 200 total, two winners per quest. **The Side Quest breakdown is deliberately not
  published**, and the quest themes are sealed until each unlocks.
- Judging: Fun, Hold, Interactivity, Sense of place, Completeness. Imported asset quality is
  explicitly not judged.
- Free to enter. 18+ to receive a cash prize.
- Submissions happen in the **World Jam submissions** forum channel in the Anitya Discord.
  There is no submission form and there must not be one.
- One prize figure, stated identically everywhere it appears.

## NEVER put these on the page

All of these are false or unverified. They have been removed once already.

- **Multiplayer.** Unconfirmed. Never claim it.
- **Mobile or VR creation.** Creation is desktop only. Playing works well on mobile and VR, so
  "play on mobile and VR" is the accurate phrasing.
- **"AI game engine".** We are a no-code platform for creating 3D Worlds.
- **A launch date for Anitya.** There is not one. Anitya is live now, open beta, improving weekly.
- **Email-based ownership verification.** Superseded. Ownership is checked for winners only, by
  confirming the Anitya account that created the world belongs to the person who submitted it.
- **Any social proof a newcomer can disprove in ten seconds.** No world counts, no user counts.

## Language rules

- Say **Worlds**. Never "3D websites", never "metaverse".
- Say **create**. "Build" was retired product-wide.
- Prefer verbs over identity nouns at activation moments. "Create a world", not "become a creator".
- Plain constructions over elided ones. "You need a free account to publish. Your visitors never
  need one."
- No unfalsifiable claims about what nobody has found yet. Inviting people to find the limits is
  fine. Asserting nobody has is not.
- Roughness is the pitch, not a caveat. Anitya is in open beta and the jam exists because we
  shipped more than we can test alone. Do not bury that at the bottom or soften it.

## Known open items - do not invent answers

If a change touches one of these, ask rather than writing something plausible.

1. Whether under 18s can enter for recognition when cash is 18+.
2. Country eligibility. Not decided, and not stated anywhere.
3. Team entries. Allowed or not, and how a prize would split.
4. Who is on the judging panel.
5. The Founding Creator badge is promised in several places and is still unconfirmed with the
   engineering team.
6. The registration form currently stores nothing. It has no backend. Do not write copy that
   promises a registered creator will receive anything by email.
