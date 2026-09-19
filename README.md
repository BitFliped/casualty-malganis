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

## Keeping it accurate

The recruitment grid is *derived* from the roster — it is not an independent
list. Every class in the game gets a card, so a missing class reads as an
oversight rather than a decision. When the roster changes, re-derive:

- **High need** — the class can heal, but nobody on the roster heals on it.
- **Open** — nobody on the roster plays that class at that role.
- **Closed** — somebody already covers it. The intro paragraph tells good
  applicants to apply anyway, which is what keeps "Closed" honest.

`data-roles` controls which filter buttons show a card, so a class that can
heal belongs under `healer` even when its status is Closed — otherwise a
healer filtering the grid sees the class missing and reads it as unwanted.
Tanking is handled by the single `Tanks` card rather than per class.

The intro paragraph names specific gaps ("no Priest, one Shaman, one Monk and
one Evoker who all play damage"). It goes stale the moment one of them is
filled, so read it whenever you touch a card.

Getting a class colour wrong silently changes a player's class, so check
against the canonical list rather than copying a neighbouring row.

## Deploying

GitHub Pages serves `main` from the repository root. Push to `main` and the
change is live within a minute.

---

Not affiliated with or endorsed by Blizzard Entertainment. World of Warcraft and
all related marks are property of Blizzard Entertainment, Inc.
