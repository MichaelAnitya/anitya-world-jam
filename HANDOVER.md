# Handover: Anitya World Jam site

From Michael to Taina, 2026-08-28. The jam opens **Tuesday 1 September**, four days out.

`CLAUDE.md` in this folder is the working manual: safe-to-edit zones, the date checklist, the
never-claim list, language rules. Read that before touching `index.html`. This file is what you
are inheriting and what is still unfinished.

## What you are getting

One self-contained repo. `index.html` is about 770 lines with the CSS and JavaScript inline.
`assets/` holds the brand fonts (Realce Black, Codec Pro bold and light), the logo, and four real
world screenshots. Nothing is referenced that is not in the repo, so it runs offline.

No build step. GitHub Pages serves `main` directly, so **a commit is live in about two minutes
with no review stage.** There is no staging environment.

Preview locally before committing:

```
python -m http.server 8621
```

Check the browser console too. The countdowns run on a one second interval, so a JavaScript error
stops them silently while the page still looks fine.

## State of the page, as handed over

Live: https://michaelanitya.github.io/anitya-world-jam/

Done and verified:

- Four week format. Opens 1 September, closes 29 September 23:59 UTC, winners 6 October.
- Theme in the hero: a world you can't stop playing. Headline: Create a world. Make them stay.
- Prizes: 2,000 total, Main Jam 1,800 across five places. Side Quest breakdown deliberately
  unpublished, themes sealed.
- Judging criteria: Fun, Hold, Interactivity, Sense of place, Completeness. Imported asset quality
  explicitly not judged.
- Submissions route to the World Jam submissions forum channel in Discord. Both old submission
  forms were removed because they were wired to an empty endpoint and silently discarded entries.
- Ownership verification rewritten to the winners-only account check.
- 12 FAQs including the extension clause and what winners get beyond cash.

## What is NOT done

**1. The registration form stores nothing.** It is the only form left on the page. `ENDPOINT` in
the script is an empty string, so it alerts and discards. Someone registering on 1 September gets
"You're in" and vanishes. This also blocks the Founding Creator badge, which is a 90 day cohort
and needs a list we own. The two previous hackathon lists were lost exactly this way, one in Luma
and one in Superteam Earn, so neither cohort could be re-contacted.

Either wire it to a sheet, or remove it and let Discord membership be the list. Do not leave it
as it is.

**2. The URL is a personal GitHub account.** Fine for showing the team, wrong for any ad or any
outreach to a community owner. See the transfer section below.

**3. The statics still say the old headline.** Four files in
`claude-projects/worldjam-creatives/`, still carrying "CREATE A WORLD, WIN CASH". `build_static.py`
and the fonts travel with them so they re-render in place. They also still need the dates and the
single prize figure.

**4. Dead CSS.** Rules for `.locked`, `.quest-strip`, `.seg` and `.formpane` remain after the
sealed Side Quest cards and the forms were removed. Harmless, just untidy.

## Decisions that are not yours to make, and are still open

These are with Pedro or engineering. They block copy on this page, so track them rather than
guessing an answer.

1. Can under 18s enter for recognition, given cash is 18+. Goes in the published rules.
2. Country eligibility. Not decided, not stated anywhere.
3. Team entries, and how a prize would split.
4. Who is on the judging panel.
5. The Founding Creator badge is promised in several places and engineering has not confirmed it
   is being built.
6. Discord Connect has not shipped. Manual fallback for winner verification: give each winner a
   code to put in their world description for an hour, which only the account owner can do. About
   fifteen checks at the end of the jam.
7. jam.anitya.space or stay on the GitHub URL.
8. Works versus rough split on the August update, from Conrado or Gabriel. The page now names
   physics, gamification, teleports and JSON custom code in the judging criteria, and the jam
   invites people to find what is broken. The list has to be honest.

## Where the rest of the context lives

- **Full spec:** "Anitya World Jam - Full Spec v1" in Google Drive. Theme, dates, prizes, judging,
  rules, and all eleven open decisions with reasoning.
- **CLAUDE.md:** in this repo. The editing manual.
- **Brand kit:** `claude-projects/_brand-kit/` on Michael's machine, not in this repo. Real fonts,
  the real background treatment, button and hero CSS lifted from the live site. Needed only if you
  restyle rather than rewrite.
- **Community outreach:** "World Jam - Community Outreach" sheet in Drive. 33 target Discord
  servers, three message variants, operating rules, and finished first-contact drafts.

## The one thing that will bite you

Dates appear in about eight places, including `data-target` attributes that drive the countdown
clocks and a hardcoded date in the script that flips the hero countdown on 1 September. Change one
and the page contradicts itself, or a clock counts to the wrong day. `CLAUDE.md` has the full
checklist. Search the file for the old date string and confirm zero results before committing.
