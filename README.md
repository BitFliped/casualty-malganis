# Casualty — Mal'Ganis (US)

Guild site for **Casualty**, a Horde Heroic raiding and Mythic+ guild on Mal'Ganis (US).
Recruitment pitch and member information in one page.

Live at: https://bitfliped.github.io/casualty-malganis/

## What's here

`index.html` is the whole site — one self-contained file. No build step, no
dependencies, no framework. Fonts come from Google Fonts; everything else is
inline.

## Editing

Open `index.html` and edit the markup directly. The parts that go stale:

| What | Where to look |
| --- | --- |
| Boss progression | the `<table>` in `#progress` — `kill yes` / `kill now` / `kill no` |
| Raid roster | `.comp-row` blocks in `#roster` — each name carries its class colour in `--cc` |
| Recruitment needs | `.cls` cards in `#recruiting` — status classes are `s-high`, `s-open`, `s-exc`, `s-closed` |
| Raid times | `data-day` / `data-hour` / `data-minute` on `.night`, plus `ZONE` in the schedule script |

Raid times are stored once as Eastern and converted to each visitor's own
timezone in the browser, including the DST changeover. Changing a time means
editing the `data-` attributes, not the displayed text.

Class colours are the canonical WoW values, which is why the roster and
recruitment panels stay dark in both light and dark mode — Priest is `#FFFFFF`
and needs a dark ground to be legible.

## Deploying

GitHub Pages serves `main` from the repository root. Push to `main` and the
change is live within a minute.

---

Not affiliated with or endorsed by Blizzard Entertainment. World of Warcraft and
all related marks are property of Blizzard Entertainment, Inc.
